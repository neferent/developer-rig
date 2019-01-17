# A New Direction for the Twitch Developer Rig
Today (January 17, 2019), we’re announcing the steps we’re taking to improve the way we build and deliver the Developer Rig.  Our mission is to help developers build the best Extensions possible, and we believe we can better serve our customers by taking development fully in-house and moving the Developer Rig to a closed source model.  The immediate outcome of this strategic decision is the [native Developer Rig](https://discuss.dev.twitch.tv/t/announcing-the-native-developer-rig-beta/19126), which is currently in beta.  The native Rig combines a number of technical, UI, and usability improvements, delivering a faster start-up and an improved user experience.

We put a lot of thought into these changes  and we believe they will help developers in the following ways:
* We can create a more seamless experience between the Developer Rig and the devsite by enabling API calls throughout the Extension lifecycle.
* We can ship usability improvements by pinpointing UX issues in the Rig faster.
* We can better support different different versions of the Rig.  We will support a beta version that is the latest and greatest, along with a stable release build when we fully release to general availability.
* We can improve the security of the Developer Rig.

You can download the native Rig beta build for [Mac](https://s3-us-west-2.amazonaws.com/developer-rig-install-update-development/Twitch+Developer+Rig-0.9.3.dmg) and for [Windows](https://s3-us-west-2.amazonaws.com/developer-rig-install-update-development/Twitch+Developer+Rig+Setup+0.9.3.exe).  We are targeting early February to provide a Linux build as well.  We would love to get your feedback and you can do so in the following places: the #native-dev-rig-beta channel on the [TwitchDev Discord](https://link.twitch.tv/devchat), on the [Twitch Developer Forums](https://discuss.dev.twitch.tv/c/extensions), or in the following user [survey](https://goo.gl/forms/Cm4QvBDP2MHM70263).

This repository will move to “Read Only” today and will remain available in that state.    

We greatly appreciate the contributions the community has made to the Developer Rig to date. We want to give a special shout out to the following developers in the community whose contributions have been shipped in the Developer Rig. 
[mzmiric5](https://github.com/mzmiric5)
[BarryCarlyon](https://github.com/BarryCarlyon)
[thedist](https://github.com/thedist)
[boingy](https://github.com/boingy)
[talk2MeGooseman](https://github.com/talk2MeGooseman)
[nixxquality](https://github.com/nixxquality)
[Bentleycook](https://github.com/Bentleycook)
[VitruxPT](https://github.com/VitruxPT)
[justinryder](https://github.com/justinryder)
[robin7331](https://github.com/robin7331)
[joshribakoff](https://github.com/joshribakoff)
[ryancharlesking](https://github.com/ryancharlesking)
[hyandell](https://github.com/hyandell)
[arnaudmanaranche](https://github.com/arnaudmanaranche)

Thank you all and see you on Twitch!

# Twitch Extensions Developer Rig
[![Build Status](https://travis-ci.org/twitchdev/developer-rig.svg?branch=master)](https://travis-ci.org/twitchdev/developer-rig) [![Coverage Status](https://coveralls.io/repos/github/twitchdev/developer-rig/badge.svg)](https://coveralls.io/github/twitchdev/developer-rig)

## Quickstart to Running the Developer Rig
Take these steps to get the Rig running:

1.  If you already have [Git](https://git-scm.com/download) installed, clone the Rig.  Otherwise, [download and extract the Zip file](https://github.com/twitchdev/developer-rig/archive/master.zip).
2.  Open the `scripts` folder in the `developer-rig` folder.
3.  Double-click the `configure` file on Mac, `configure.cmd` file on Windows.  The first time you run the script it will take a while since it will install and configure all of the dependencies.
4. Double-click the `run` file on Mac, `run.cmd` file on Windows.  Alternatively, open a terminal, navigate to the root folder of the Developer Rig on your machine, and enter `yarn start`.

Once in the Rig, sign in with your Twitch credentials and create your first Extension Project.  Learn more [here](https://dev.twitch.tv/docs/extensions/rig/).


## Troubleshooting

#### I’m sure my Developer Rig configuration is correct, but my extension doesn’t work
Clear your browser cache and local storage and restart the Developer Rig.

To delete the Rig's local storage open the javascript console in your browser on a tab with the Rig open and enter `localStorage.clear()` then refresh.

Ensure you've included the Twitch Extensions Helper in your front-end files.

#### When setting up the Rig on Windows 10, my system settings do not allow me to run scripts downloaded from the internet
Make sure to adjust your security settings to “Developer Mode” in the “For Developers” section of your System Settings.

#### I get an error when trying to run yarn test
Sometimes deleting the `node_modules` directory and running `yarn` fixes this issue.

On macOS, you may need to explicitly install Watchman via `brew install watchman`.

#### yarn install fails in libssh2
See [issue #48](https://github.com/twitchdev/developer-rig/issues/48). Be sure `libssh` and its dependencies are installed.

#### I get an error when pulling in the example project
Ensure that Git is in your PATH variables by trying to run git at your command line. If that works, also ensure that the local folder does not currently exist.

#### I created my extension manifest on the Twitch dev site but can’t find my front-end files
If you created your extension manifest on the Twitch dev site, you must specify your Base Testing URI as https://localhost.rig.twitch.tv:8080. This field is discussed under Asset Hosting, in Releasing & Maintaining an Extension.
