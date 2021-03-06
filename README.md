<img src="https://raw.githubusercontent.com/porelarte/asan-login-flutter/master/doc/assets/cover.png" width="100%" alt="logo" />

<h2 align="center">
ASAN Login for Flutter
</h2>

## Overview

A basic, production-ready, `community-driven` implementation for `ASAN Login`. The main responsibility of the package, as it is sufficient for mobile-side of the projects, is to extract `token` once the user is successfully logged in. The extracted `token`'s payload contains logged user's basic information. For advanced validation of user, please refer to `ASAN Login`'s documentation provided to your institution.

NOTE: Altough it does not mean it is unstable, but, nevertheless it's worthwhile to inform developers that are going to use it that, this package is not officially developed and maintained by `ASAN Login` itself, but rather by Flutter community.

---

## Usage

```dart
Widget build(BuildContext context) {
  return AsanLoginView(
    packageName: 'com.example.app',
    config: AsanLoginConfig(
      progressColor: Colors.indigo,
      clearCookies: true,
      environment: AsanLoginEnvironment.prod,
    ),
    onLogin: (String token) {
      // TODO: process token
    },
  );
}
```

### packageName

The `packageName` under which your project is registered on `ASAN Login` system. Make sure to use same String for your app's both `applicationId` on Android side and `CFBundleIdentifier` on iOS side to avoid any side effects.

### progressColor

Color which is used to indicate the load progress at the top of the `AsanLoginView`.

### clearCookies

When `clearCookies` is set to `true` user stays as logged in if previously logged. When set to `false` (which is recommended to use as a configuration for most of the use cases of `ASAN Login`) user gets redirected to the login page of `ASAN Login` everytime.

### environment

Defines environment for `ASAN Login`. For more info on `dev` and `prod` environments, please refer to `ASAN Login`'s documentation provided to your institution.

### onLogin

Called when user successfully logs in, with `token` (`String`); 

---

## Clearing cache

When user's session is terminated on the app (~logout), make sure to call clearAsanLoginCache() global method to make sure user's previous `ASAN Login` cache is cleared from app's cache.

---

## TODO

- [x] Retrieve token when logged in.
- [x] Switching between `dev` and `prod` environments.
- [x] Documentation for source code.
- [x] README.md.
- [ ] Integration tests.
- [ ] Better documentation of source codes.
- [x] Example app.
- [ ] Flutter Web support.
- [ ] Windows Support.
- [ ] MacOS support.
- [ ] Linux support.
- [ ] Document platform specific configurations if any.