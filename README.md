# modsmoke

I am going to see if I can use AppVeyor and Travis CI environments to install a list of cpan modules under various perls, and automatically send the results to cpantesters.

Eventually, I'll want to figure out a way to keep track of which versions of a given module have been tested under a given perl, so that I don't keep re-doing the same tests... but for now, I'm just going to work on proof of concept.

App::cpanminus::reporter installed on AppVeyor; going to try on Travis.

If that works, then I will want to work on encrypting my CPANTESTERS credentials for both frameworks