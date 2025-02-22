# CHANGELOG - throttle

# 2.1.0 - 2021-03-10
## Added
* Added support for config files. Use `--config config.json` to read configuration setup from a file.
# 2.0.2 - 2020-09-10
## Fixed
* Make the install as small as possible.

# 2.0.1 - 2020-08-22
## Fixed
* Removed the execa dependency to make sure we have minimal dependencies [#53](https://github.com/sitespeedio/throttle/pull/53).

# 2.0.0 - 2020-08-14
### Changed
* You can now set one of up/down/rtt if you like as introduced by [Iñaki Baz Castillo](https://github.com/ibc) - thank you! Implemented in [#46](https://github.com/sitespeedio/throttle/pull/46). This also remove the default profile meaning there's a change in behavior if you run throttle without any parameters. Before a default profile was used but now you get an error (you know need to set a profile or set up/down or rtt).

### Added
* You can use ```--log``` to log all networks commands [#45](https://github.com/sitespeedio/throttle/pull/45).
* Added support to add delay on for localhost on OS X. Use ```--rtt 100 --localhost``` [#51](https://github.com/sitespeedio/throttle/pull/51).

### Fixed
* Add missing await when removing the ingress if removing root fails for tc [#47](https://github.com/sitespeedio/throttle/pull/47).
* Better error handling in the CLI [#48](https://github.com/sitespeedio/throttle/pull/48). Make sure that the exit code is > 0 if setting the throttling fails.

### Tech
* Removed configuration file for pfctl to make it easier to set up dynamic dummynet [#49](https://github.com/sitespeedio/throttle/pull/49)

## 1.1.0 2020-07-29
### Fixed
* Updated execa to 4.0.3.
* Removed log message "using default profile"

### Added
* You can log all the commands that sets up the throttling by setting ```LOG_THROTTLE=true``` [#44](https://github.com/sitespeedio/throttle/pull/44).

## 1.0.3 2020-06-20
### Fixed
* Updated minimist

## 1.0.2 2020-03-09
### Fixed
* Fixed dependency tree and npm-shrinkwrap to only hold dependencies for production.

## 1.0.1 2020-02-03
### Fixed
* Another fix to 2g to get that right, thank you Matt! [#37](https://github.com/sitespeedio/throttle/pull/37).

## 1.0.0 2020-02-03
### Changed
* 2g speed was updated to become more usable and follow WPT [#36](https://github.com/sitespeedio/throttle/pull/36) - thank you [Matt Hobbs](https://github.com/Nooshu) for the PR.

### Added
* More pre-made profiles: dsl, 3gem, 4g, lte, edge, dial, fois [#36](https://github.com/sitespeedio/throttle/pull/36) - thank you [Matt Hobbs](https://github.com/Nooshu) for the PR.

## 0.5.4 2019-08-26
### Fixed
* Another execa fix, hopefully fixing the last thing + added more tests in Travis.

## 0.5.3 2019-08-26
### Fixed
* Over optimistic Execa upgraded caused Throttle to stop working [#32](https://github.com/sitespeedio/throttle/pull/32).

## 0.5.2 2019-08-26
### Fixed
* Updated dependencies [#31](https://github.com/sitespeedio/throttle/pull/31). 

## 0.5.1 2019-04-23
### Fixed
* Calling stop on Linux throwed error see [#20](https://github.com/sitespeedio/throttle/issues/20) and fixed by [Iñaki Baz Castillo](https://github.com/ibc), thank you!

## 0.5.0 2018-12-07
### Added
* Simplified profile/stop/help. You can now start with: ```throttle $profile``` and stop with ```throttle stop```

## 0.4.3 2018-09-01
### Fixed
* Upload throttling was wrong on Mac OS X, thank you [Paul](https://github.com/paulz) for the [PR](https://github.com/sitespeedio/throttle/pull/16).

## 0.4.2 2018-05-30
### Fixed
* Catching when ifb has already been setup.

## 0.4.1 2018-05-30
### Fixed
* Another go at trying to try/catch failing settings.

## 0.4.0 2018-05-30
### Added
* Rewrite to async/await from promises

## 0.3.0 2018-04-12

### Fixed
* Ensure setup has completed fully before returning when starting throttling with tc.
* Always return Promises from start() and stop(), even in case of errors.
* Typo in the CLI help
* Simpler way to set connectivity with tc

## 0.2.0 2017-10-31

### Added
* You can now see the version with --version
* You can now use pre defined profiles.

## 0.1.0 2017-10-13

### Fixed
* Always remove filters before we try to set them.
