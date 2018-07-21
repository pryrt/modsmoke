# modsmoke

Use AppVeyor and Travis CI environments to install a list of cpan modules under various perls, and automatically send the results to cpantesters.

The ModuleList contains all the arguments that will be sent to cpanm for installation.

<div>
    <a href="https://github.com/pryrt/modsmoke/releases"><img src="https://img.shields.io/github/release/pryrt/modsmoke.svg" alt="github release" title="github release"></a>
    <a href="https://github.com/pryrt/modsmoke/issues"><img src="https://img.shields.io/github/issues/pryrt/modsmoke.svg" alt="issues" title="issues"></a>
    <a href="https://ci.appveyor.com/project/pryrt/modsmoke"><img src="https://ci.appveyor.com/api/projects/status/1rqdroon682snre8?svg=true" alt="appveyor build status" title="appveyor build status"></a>
    <a href="https://travis-ci.org/pryrt/modsmoke"><img src="https://travis-ci.org/pryrt/modsmoke.svg?branch=master" alt="travis build status" title="travis build status"></a>
</div>

## TODO

Eventually, I'll want to figure out a way to keep track of which versions of a given module have been tested under a given perl, so that I don't keep re-doing the same tests... but for now, I'm just going to work on proof of concept.

## Development Notes

### .cpanreporter directory location
By running cpanm-reporter without a config, I got error messages
* travis-ci: file '/home/travis/.cpanreporter/config.ini' not found
* appveyor: file 'C:\Users\appveyor\.cpanreporter\config.ini' not found

So now I know where those go.

### Encrypting .cpanreporter configuration

https://docs.travis-ci.com/user/encrypting-files
* so, Travis requires Ruby to encrypt... unfortunately, I cannot get it on my NAS (requires gcc)... I've grabbed the windows Ruby installer... but I'll postpone that for now.

let's focus on appveyor, instead
https://www.appveyor.com/docs/how-to/secure-files/
* Grabbed the appveyor-tools via powershell
* %userprofile%\appveyor-tools\secure-file -encrypt metabase_id.json -secret MYSECRET1234
  (except use the real password)
