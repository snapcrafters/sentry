<h1 align="center">
  <img src="https://sentry-brand.storage.googleapis.com/sentry-glyph-black.png" alt="Sentry">
  <br />
  Sentry
</h1>

<p align="center"><b>This is the snap for <a href="https://sentry.io">Sentry</a>.</b> It works on Ubuntu, Fedora, Debian, and other major Linux
distributions.</p>

<!-- Uncomment and modify this when you are provided a build status badge
<p align="center">
<a href="https://build.snapcraft.io/user/snapcrafters/fork-and-rename-me"><img src="https://build.snapcraft.io/badge/snapcrafters/fork-and-rename-me.svg" alt="Snap Status"></a>
</p>
-->

## Install

Before installing, make sure you have the following availiable:

* Postgres database.
* Redis database.

Once you have these running, install Sentry with:
`sudo snap install sentry`

This will install 4 things:

* A `sentry` command to allow you to configure Sentry.
* 3 daemons, consisting of web, worker and cron.

The daemons can be accessed via `systemctl`, there names being:

* `snap.sentry.web`
* `snap.sentry.worker`
* `snap.sentry.cron`

At this point, we can initialise Sentry:

`sudo sentry init`

Note `sudo`.  This is because the daemons will be running as root (although confined by snapd).  If you run this without `sudo`, the running Sentry daemons won't be able to find the configuration files.

At this point, you can go and edit Sentry's config files to point them at your Postgres and Redis databases.  You can find the location of these files with:

`sudo sentry config discover`

Once edited, you need to run all pending migrations and setup a superuser with:

`sudo sentry upgrade`

Afterwards, restart the daemons with:

`sudo systemctl restart "snap.sentry.*"`

Now, you should be able to browse to http://localhost:9000[http://localhost:9000]

([Don't have snapd installed?](https://snapcraft.io/docs/core/install))

<p align="center">Published for <img src="http://anything.codes/slack-emoji-for-techies/emoji/tux.png" align="top" width="24" /> with :gift_heart: by Snapcrafters</p>

## Remaining tasks

Snapcrafters ([join us]()) are working to land snap install documentation and
the [snapcraft.yaml](https://github.com/joedborg/snap-pycharm-professional/blob/master/snap/snapcraft.yaml)
upstream so Sentry can authoritatively publish future releases.

  - [x] Fork the [Snapcrafters template](https://github.com/snapcrafters/fork-and-rename-me) repository to your own GitHub account
  - [x] Rename the forked Snapcrafters template repository
  - [x] Update logos and references to `[Project]` and `[my-snap-name]`
  - [x] Create a snap that runs in `devmode`
  - [x] Register the snap in the store, **using the preferred upstream name**
  - [ ] Add a screenshot to this `README.md`
  - [x] Publish the `devmode` snap in the Snap store edge channel
  - [x] Add install instructions to this `README.md`
  - [x] Update snap store metadata, icons and screenshots
  - [x] Convert the snap to `strict` confinement, or `classic` confinement if it qualifies
  - [x] Publish the confined snap in the Snap store beta channel
  - [x] Update the install instructions in this `README.md`
  - [x] Post a call for testing on the [Snapcraft Forum](https://forum.snapcraft.io) - [link]()
  - [x] Request your GitHub repository is forked to the Snapcrafters organisation and configured for automated builds
  - [ ] Add the provided Snapcraft build badge to this `README.md`
  - [x] Publish the snap in the Snap store stable channel
  - [x] Update the install instructions in this `README.md`
  - [x] Post an announcement in the [Snapcraft Forum](https://forum.snapcraft.io) - [link]()
  - [x] Submit a pull request or patch upstream that adds snap install documentation - [link]()
  - [x] Submit a pull request or patch upstream that adds the `snapcraft.yaml` and any required assets/launchers - [link]()
  - [ ] Add upstream contact information to the `README.md`  
  - If upstream accept the PR:
    - [ ] Request upstream create a Snap store account
    - [ ] Contact the Snap Advocacy team to request the snap be transferred to upstream
  - [ ] Ask the Snap Advocacy team to celebrate the snap - [link]()

If you have any questions, [post in the Snapcraft forum](https://forum.snapcraft.io).

## The Snapcrafters

| [![Joe Borg](https://en.gravatar.com/userimage/28566319/4e248ef2546c1efdc9ecf1c7688f53fb?size=128)](https://github.com/joedborg/) |
| :---: |
| [Joe Borg](https://github.com/joedborg/) |

<!-- Uncomment and modify this when you have upstream contacts
## Upstream

| [![Upstream Name](http://gravatar.com/avatar/bc0bced65e963eb5c3a16cab8b004431?s=128)](https://github.com/upstreamname) |
| :---: |
| [Upstream Name](https://github.com/upstreamname) |
-->
