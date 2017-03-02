# gulp-jsdoc3

[![NPM version][npm-image]][npm-url]

> [jsdoc](https://github.com/jsdoc3/jsdoc) plugin for [gulp](https://github.com/gulpjs/gulp)

## Installation

Install `gulp-jsdoc` as a development dependency:

```shell
npm install --save-dev @sugarcrm/gulp-jsdoc3
```

## Usage

```javascript
var jsdoc = require('gulp-jsdoc3');

gulp.task('doc', function (cb) {
    gulp.src(['README.md', './src/**/*.js'], {read: false})
        .pipe(jsdoc(cb));
});
```

You can also pass in your own config to override the defaults. All CLI options can be specified here.

```javascript
var jsdoc = require('gulp-jsdoc3');

gulp.task('doc', function (cb) {
    var config = require('./jsdoc.json');
    gulp.src(['README.md', './src/**/*.js'], {read: false})
        .pipe(jsdoc(config, cb));
});
```

Another good example is in this project's [gulpfile](https://github.com/mlucool/gulp-jsdoc3/blob/master/gulpfile.js)!

## Overriding the default layout

[ink-docstrap](https://github.com/docstrap/docstrap) is used as the default layout but you can easily override it in your config like this:

```
{
    "templates": {
        "default": {
            // Set my own layout file
            "layoutFile": "./layout.tmpl"
        }
    }
}
```

## Debugging
Set env variable: ```DEBUG=gulp-jsdoc3```  

## Notes
This is a reasonable attempt to wrap jsdoc using gulp as thinly as possible. All files are added after the cli.
i.e. `jsdoc -c config -t node_modules/ink-docstrap/template gulpFile1 gulpFile2`  
[jsdoc](https://github.com/jsdoc3/jsdoc) does not allow for piped input, so this attempt may be considered a gulp
anti-pattern. It also does not pass on output to be piped elsewhere.


I would like to thank Mangled Deutz @ [gulp-jsdoc](https://github.com/jsBoot/gulp-jsdoc) for the original implementation.

License
-------------
[Apache-2.0 License](http://www.apache.org/licenses/LICENSE-2.0)

[npm-url]: https://npmjs.org/package/@sugarcrm/gulp-jsdoc3
[npm-image]: https://badge.fury.io/js/gulp-jsdoc3.png


