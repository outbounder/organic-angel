# Angel #
Single cell and command line application for doing handy of helpful things for everyday routines.

## Features ##

* can populate local or remote directory using a template source
* supports file based & git based template sources

## Command line usage ##

  $ angel populate <targetDir> <templateSource>

Will fill up `targetDir` with the contents of `templateSource` by replacing any occurances of `%name%` within file names or file contents. `%name%` is a variable holding the directory name of `targetDir`.

  $ angel remote populate <user@host> <targetDir> <templateSource>

The same as local populate method, but end result is uploaded to `user@host` using scp.

## API usage ##

  var Angel = require("Angel");
  var instance = new Angel();
  instance.populateLocal(target, templateSource, data, callback);
  instance.populateRemote(remote, target, templateSource, data, callback);

## Examples, tips & tricks ##

### use angel to start quickly a project ###

1. Create git repo with a bootstrap/skeleton code & structure. For example: https://github.com/outbounder/php5boilerplate
2. run `$ angel populate ~/projects/myAweasomeProject https://github.com/outbounder/php5boilerplate.git`

### use angel to install application remotely ###

1. work on your app and commit it, for example: https://github.com/outbounder/camplight.net
2. run `$ angel populate node@myStagingServer git@github.com:outbounder/camplight.net.git`