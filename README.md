DOES NOT CURRENTLY FUNCTION
As it is this will flood the server with activities every time you do something. I don't have the time to fix it right now.

WakaTime for Azure Data Studio
===============================

Metrics, insights, and time tracking automatically generated from your programming activity.


#### To install, go to the [Releases](https://github.com/Vaelek/vscode-wakatime/releases/latest) tab and download the latest `vsix` file. Install via the File menu in ADS.

This is a fork of the WakaTime VSCode plugin for use with `Azure Data Studio`. Tested (so far) only on Windows.
I made this for myself, but from all the posts I saw in my quest to make the VSCode version work in ADS, I am not alone, so I make this publicly available to anyone that would like it.

The VS Code extension does function in ADS, but not with unsaved files, which is a very common, if not majority way to use it.

If you are editing a saved query, the filename will be reflected, assuming you have not disabled filenames. If you are editing an unsaved query, then the filename will be passed as `General.sql`

In my opinion, the most common use of ADS is ad-hoc queries, not `projects`.. As such, a new command has been added

![type project](./images/type-project.png)

If not set, the project will be reported as `Generic SQL`

In the original project, the WakaTime cli is silently downloaded on first run, and checked against the latest version on every subsequent launch. Due to a combination of issues during development, and a general distaste for the security implications of remote scripts, the Wakatime cli is bundled in this extension, and the remote fetching has been disabled.

Original project notes follow
=============================

Installation
------------

  1. Press `F1` or `CMD + Shift + P` and type `install`. Pick `Extensions: Install Extension`.

  ![type install](./images/type-install.png)

  2. Type `wakatime` and hit `enter`.

  ![type wakatime](./images/type-wakatime.png)

  3. Restart Visual Studio Code.

  4. Enter your [api key](https://wakatime.com/settings?apikey=true), then press `enter`.

    (If you’re not prompted, press `F1` or `CMD + Shift + P` then type `WakaTime API Key`.)

  5. Use VSCode and your coding activity will be displayed on your [WakaTime dashboard](https://wakatime.com).


Usage
-----

Visit https://wakatime.com to see your coding activity.

![Project Overview](./images/Screen-Shot-2016-03-21.png)


Configuring
-----------
> `$WAKATIME_HOME` defaults to `$HOME`

Some settings are available from CMD+SHIFT+p, then typing `wakatime`.

Settings are stored in the INI file at `$WAKATIME_HOME/.ads.wakatime.cfg`.

More information can be found from [wakatime core](https://github.com/wakatime/wakatime#configuring).


Troubleshooting
---------------

First, turn on debug mode:

1. Press CMD+SHIFT+p
2. Type `wakatime.debug`, and press `Enter`.
3. Select `true`, then press `Enter`.

Next, open your Developer Console to view logs and errors:

`Help → Toggle Developer Tools`

Errors outside the scope of vscode-wakatime go to `$WAKATIME_HOME/.ads.wakatime.log` from [wakatime-cli][wakatime-cli-help].

The [How to Debug Plugins][how to debug] guide shows how to check when coding activity was last received from your editor using the [Plugins Status Page][plugins status page].

For more general troubleshooting info, see the [wakatime-cli Troubleshooting Section][wakatime-cli-help].


[wakatime-cli-help]: https://github.com/wakatime/wakatime#troubleshooting
[how to debug]: https://wakatime.com/faq#debug-plugins
[plugins status page]: https://wakatime.com/plugin-status
