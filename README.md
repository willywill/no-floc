# No FLoC
🚫 No FLoC - Say no to Googles' Federated Learning of Cohorts (FLoC). A list of ways to opt-out

## Table of Contents

 - [Netlify](#netlify)
 - [Nginx](#nginx)

### [Netlify](#netlify)

Add a plaintext file in the [publish directory](https://docs.netlify.com/configure-builds/get-started/#basic-build-settings) of your website called `_headers`

Add the following content in the newly created plaintext file: 

```
/*
  Permissions-Policy: interest-cohort=()
```

(The example above uses the `/*` pattern to match _all_ pages. Configure this as you wish.)

### [Nginx](#nginx)

TBD
