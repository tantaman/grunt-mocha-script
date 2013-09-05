# grunt-mocha-script

> Compiles Mocha-Script sources javascript

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-mocha-script --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-mocha-script');
```

## The "mocha_script" task

Example Gruntfile:

```javascript
module.exports = function(grunt) {
  grunt.loadNpmTasks('grunt-mocha-script');

  grunt.initConfig({
    mocha_script: {
      compile: {
        options: {},
        files: {
          "compiled.js": ["source.mocha"]
        }
      }
    }
  });

  grunt.registerTask('default', [
    'mocha_script'
  ]);
};
```