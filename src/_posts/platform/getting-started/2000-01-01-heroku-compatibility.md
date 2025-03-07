---
title: Heroku Compatibility
modified_at: 2022-03-11 00:00:00
tags: heroku twelve-factor
index: 10
---

Our aim for Scalingo is to be fully compatible with Heroku.
If your app works on Heroku, it will work on Scalingo.
We have added several compatibility layers for that matter.

## Procfile

If a **Procfile** is available in the source code of your app, it will be used.
See the [dedicated Procfile page]({% post_url platform/app/2000-01-01-procfile %})
for more informations.

The Procfile `release` entry does not exist on Scalingo thus it won't be executed.

The [postdeploy hook]({% post_url platform/app/2000-01-01-postdeploy-hook %})
exists with similar functionality.
The difference is that the `postdeploy` hook is only getting executed at the
end of a successful deployment, not at each change of variable/addon
modification (creating a release).

## Buildpacks

Most buildpacks and their functionalities work exactly the same as on Heroku.
Some buildpacks are written and maintained by our own.

It's open source. Check our
[GitHub account](https://github.com/Scalingo/?q=buildpack) to see the
whole list.

## App.json

Heroku uses the file `app.json` for describing your application.
The file on Scalingo is named `scalingo.json` and its format is fully
compatible with the format used by Heroku.

The Scalingo manifest file has a few specifics.
You can find out more about it
[here]({% post_url platform/app/2000-01-01-app-manifest %}).

## Environment Variables

Because we'd like to conform as much as possible to the
[12-factor](https://12factor.net) principle, you can configure your app through
[environment variables]({% post_url platform/app/2000-01-01-environment %})
which are injected into the context of your application.

## Realtime Deployment

Based on a Git hook. Just git push your code!

## Open API and Command Line Client

* [Open API](https://developers.scalingo.com)
* [Command Line Interface client](https://cli.scalingo.com)
