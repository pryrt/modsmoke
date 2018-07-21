# modsmoke

I am going to see if I can use AppVeyor and Travis CI environments to install a list of cpan modules under various perls, and automatically send the results to cpantesters.

Eventually, I'll want to figure out a way to keep track of which versions of a given module have been tested under a given perl, so that I don't keep re-doing the same tests... but for now, I'm just going to work on proof of concept.

App::cpanminus::reporter installed on AppVeyor; going to try on Travis.

If that works, then I will want to work on encrypting my CPANTESTERS credentials for both frameworks

By running cpanm-reporter without a config, I got error messages
- travis-ci: file '/home/travis/.cpanreporter/config.ini' not found
- appveyor: file 'C:\Users\appveyor\.cpanreporter\config.ini' not found

So that tells me where I need to go next.

Now I need to research the secure/encrypted files

--

https://docs.travis-ci.com/user/encrypting-files
so, Travis requires Ruby to encrypt... unfortunately, I cannot get it on my NAS (requires gcc)... I've grabbed the windows Ruby installer... but I'll postpone that for now.

let's focus on appveyor, instead
https://www.appveyor.com/docs/how-to/secure-files/
* Grabbed the appveyor-tools via powershell
* %userprofile%\appveyor-tools\secure-file -encrypt metabase_id.json -secret MYSECRET1234
  (except use the real password)
