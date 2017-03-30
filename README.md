# dotfiles

A collection of my dotfiles and other configuration information for getting a new machine up and running.

Inspired by https://github.com/nateirwin/dotfiles.

## Applications

### App Store

- 1Password
- Alfred
- Evernote
- Monosnap
- OmniGraffle
- Slack
- Tweetdeck
- Xcode

### Download

- Atom
- [Base](http://menial.co.uk/base/)
- [Dash](https://kapeli.com/dash)
- Dropbox
- Firefox
- Garmin Express
- [GIMP](https://www.gimp.org/downloads/)
- [Google Earth Pro](https://www.google.com/earth/explore/products/desktop.html)
- [HyperTerm](https://hyper.is/)
- [Inkscape](https://inkscape.org/)
- [JOSM](https://josm.openstreetmap.de/)
- [Kap](https://getkap.co/)
- [Microsoft Office](http://www.acns.colostate.edu/software-downloads/)
- [pgAdmin 4](https://www.pgadmin.org/)
- [Postgres](http://postgresapp.com/)
- [Plug](https://www.plugformac.com/)
- [QGIS](http://www.kyngchaos.com/software/qgis)
- [Screenhero](https://screenhero.com)
- [SizeUp](http://www.irradiatedsoftware.com/sizeup/)
- Skype
- Spotify
- [Sublime Text 3](http://www.sublimetext.com/)
- [Transmission](http://transmissionbt.com/)
- [VLC](https://www.videolan.org/vlc/)

## System configuration

- Install Homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
  - Add to `.bash_profile`: `export PATH=/usr/local/bin:$PATH`
  - Reference: https://changelog.com/posts/install-node-js-with-homebrew-on-os-x
- Install Git: `brew install git`, then:
  - `git config --global user.name "Chad Lawlis"`
  - `git config --global user.email "cwlawlis802@gmail.com"`
  - `git config --global credential.helper osxkeychain`
  - References: https://help.github.com/articles/setting-your-username-in-git/, https://help.github.com/articles/caching-your-github-password-in-git/
- Install Node: `brew install node`, then:
  - Install [Grunt](https://www.npmjs.com/package/grunt): `npm install grunt-cli -g`
  - Install [Gulp](https://www.npmjs.com/package/gulp): `npm install gulp-cli -g`
  - Install [HTTP Server](https://www.npmjs.com/package/http-server): `npm install http-server -g`
- Install Ruby gems:
  - *Note: using the default MacOS Ruby install can require you to use `sudo` when installing gems*
  - [Jekyll](http://jekyllrb.com/docs/installation/): `sudo gem install jekyll`
  - [Bundler](http://bundler.io/): `sudo gem install bundler`

## App configuration

To do after downloading and installing each app.

#### Alfred

Set up sync:
- Preferences > Advanced > Syncing > Set sync folder > iCloud Drive > `alfred`

#### Atom

Set up shell commands:
- `ln -s /Applications/Atom.app/Contents/Resources/app/atom.sh /usr/local/bin/atom`, or:
- Atom > Install Shell Commands

Install packages:
- atom-beautify
- atom-css-comb
- linter
- linter-csslint
- linter-js-standard (set Style to "semi-standard" in package settings)
- linter-tidy
- tabs-to-spaces
- sublime-style-column-selection

Add to `.bash_profile` to use Atom as the default editor: `export EDITOR='atom'`

#### Sublime Text

Version 3 at the time of writing.

Install command line tool:
- `ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl`
- Reference: https://www.sublimetext.com/docs/3/osx_command_line.html

Set word wrap as default:
- Open settings via "command + ,"
- Add `"word_wrap": true`

#### HyperTerm

Add to plugins:
- [hypercwd](https://www.npmjs.com/package/hypercwd)
- [hyperterm-atom-dark](https://www.npmjs.com/package/hyperterm-atom-dark)
- [hyperterm-mactabs](https://www.npmjs.com/package/hyperterm-mactabs)

Set `bell: false` to deactivate bell sound.

See here for `.hyper.js` settings file: https://gist.github.com/cwlawlis802/0eee3fef19ee8cf24d5d314fad960a84

Consider automating in the future via https://github.com/nateirwin/dotfiles#hyperterm

#### Postgres

Add to `.bash_profile` to enable command line tools: `export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/latest/bin`

The "Postgres.app" includes PostgreSQL, PostGIS, and GDAL out of the box.
The "GDAL Complete" package must still be installed for QGIS - see below.

#### PgAdmin

Version 4 at the time of writing.

To connect to the "Postgres.app" locally:
1. Dashboard > Add New Server
1. General > Name: "Postgres.app" (this is free form and can be anything)
1. Connection > Host/name address: "localhost"
1. Keep all other fields default:
 - Port: 5432
 - Maintenance database: postgres
 - User name: postgres (may want to change this to machine's user name)
1. Double click "Servers" in sidebar to connect once complete

#### Python

MacOs Sierra comes with 2.7 out of the box, so no need to install.

If interested in Python 3:
- `brew install python3`

Use `python --version` to check version installed.

#### QGIS

Version 2.18 at the time of writing.

Will need to install 3 packages before installing the QGIS package (all of which are included in the KyngChaos download):
- GDAL Complete
- NumPy
- matplotlib

Install plugins:
- OpenLayers Plugin
- QuickOSM
- Table Manager

(Note to self: look into configuring keyboard shortcuts and menu/display preferences and how best to migrate this across machines)

#### JOSM

Install `josm.jnlp` and move to "Applications" folder.

Java must be installed in order to use this. See: https://www.java.com/en/download/mac_download.jsp.

Install plugins:
- OpenData
- GeoTools should be installed out of the box; if not, install it
- Reverter
- Todo

App shortcut will appear in "Desktop" by default - this can be configured in the `josm.jnlp` file.
