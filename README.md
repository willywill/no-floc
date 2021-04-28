# No FLoC
🚫 No FLoC - Say no to Googles' Federated Learning of Cohorts (FLoC). A list of ways to opt-out

## Table of Contents
 - As a user
   - Chrome Configuration
   - Anti-FLoC Browsers
 - As a provider
   - [Netlify](#netlify)
   - [Nginx](#nginx)

---

### [Netlify](#netlify)

1. Add a plaintext file in the [publish directory](https://docs.netlify.com/configure-builds/get-started/#basic-build-settings) of your website called `_headers`

2. Add the following content in the newly created plaintext file: 

```
/*
  Permissions-Policy: interest-cohort=()
```

3. Publish the changes. (probably by pushing to a repository linked)

(The example above uses the `/*` pattern to match _all_ pages. Configure this as you wish.)

---

### [Nginx](#nginx)

1. In your `sites-available` file, add the following response header to always be set inside of the location directive:

```
location / {
        ...
        add_header Permissions-Policy interest-cohort=() always;
    }
```

2. As always, test that the configuration is valid:

```
nginx -t
```

3. Restart the nginx service
