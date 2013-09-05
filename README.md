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


Compile all .mocha files down src into `compiled.js`

```javascript
module.exports = function(grunt) {
  grunt.loadNpmTasks('grunt-mocha-script');

  grunt.initConfig({
    mocha_script: {
      compile: {
        options: {},
        files: {
          "compiled.js": ["src/{,*/}*.mocha"]
        }
      }
    }
  });

  grunt.registerTask('default', [
    'mocha_script'
  ]);
};
```

Compile all .mocha files in src and place them in a parallel layout in dist.
Also, watch for changes.

```javascript
module.exports = function(grunt) {
	grunt.loadNpmTasks('grunt-mocha-script');
	grunt.loadNpmTasks('grunt-contrib-watch');

	grunt.initConfig({
		mocha_script: {
			compile: {
				options: {},
				files: [{
                    expand: true,
                    cwd: 'src',
                    src: '{,*/}*.mocha',
                    dest: 'dist',
                    ext: '.js'
                }]
			}
		},

		watch: {
			scripts: {
				files: ["src/{,*/}*.mocha"],
				tasks: ["compile"]
			}
		}
	});

	grunt.registerTask('compile', ['mocha_script']);
	grunt.registerTask('default', ['compile', 'watch']);
};
```
