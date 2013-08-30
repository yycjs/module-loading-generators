# Module loading and Generators

---

## Our Presenters

## Sean Goresht

* GitHub: [github.com/srsgores](https://github.com/srsgores), Twitter: [@SGoresht](https://twitter.com/SGoresht)

## Neal Sanche

* GitHub: [github.com/thorinside](https://github.com/thorinside), Twitter: [@thorinside](http://twitter.com/thorinside)

## Olivier Wietrich

* GitHub: [github.com/bredele](https://github.com/bredele), Twitter: [@bredeleca](http://twitter.com/bredeleca)

---

## Our Residents

## David Luecke

* GitHub: [daffl.github.com](http://daffl.github.com), Twitter: [@daffl](http://twitter.com/daffl)

## Eric Kryski

* GitHub: [ekryski.github.com](http://ekryski.github.com), Twitter: [@ekryski](http://twitter.com/ekryski)

---


## Our Sponsors

## Assembly Co-working Space

![Assembly](images/sponsors/assembly_logo.png)

## PetroFeed

![PetroFeed](images/sponsors/pf-logo.png)

---

## Our Sponsors

## Village Brewery

![Village Brewery](images/sponsors/village_brewery_logo_inverted.png)

---

## Last Month - [All about the tests](https://github.com/yycjs/javascript-testing)

- Some definitions
- Writing testable code
- TDD/BDD
- Testing frameworks
    - Mocha
    - Jasmine
    - QUnit
- Integrating our tests into the build system
- Continuous Integration with Travis CI
- FuncUnit

---

# JavaScript modules

---

## Scope in JavaScript

__Global vs local__

    !javascript
    function test() {
      var local = 42;
      global = 'global';
    }

    test();

__JavaScript only knows function and global scope__

    !javascript
    for(var i = 0; i < 10; i++) {
      var x = 'testing';

      (function(arg) {
        var y = arg + 1;
      })(i);

      y // -> undefined
    }

---

## Namespacing

    !javascript
    var App = {
      init : function() {
        /* ... */
      },
      Dummy : {
        sayHi : function(name) {
          return 'Hi ' + name;
        }
      }
    }

    App.Blog = {
      getPosts : function() { /* ... */ }
    }

    console.log(App.Dummy.sayHi('David'));

---

## Modules

	!javascript
	var APP = (function() {
		// Do stuff
		var privateVariable = 'Hello ',
			sayHi = function(name) {
				return privateVariable + name;
			};
		// Return API
		return {
			init : function() { /* ... */ },
			hi : sayHi
		}
	})();

	console.log(APP.sayHi('David'));

---

## __A__synchronous __M__odule __D__efinition

__AMD__: Specification for
[asynchronously loading dependencies](https://github.com/amdjs/amdjs-api/wiki/AMD).

	!javascript
	// say_hi.js
	define(function() {
		var privateVariable = 'Hello ';
		return {
			sayHi : function(name) {
                return privateVariable + name;
            }
		}
	});

	// module.js
	define(['./say_hi'], function(hisayer) {
		return {
			result : hisayer.sayHi('David'),
			sayHi : hisayer
		}
	});

	// app.js
	var module = require('./module', function(module) {
		module.sayHi('You'); // Hello You
		module.result; // -> Hello David
	});

---

## [RequireJS](http://requirejs.org/)

A JavaScript AMD module loader.

    !html
    <!DOCTYPE html>
    <html>
        <head>
            <title>My Sample Project</title>
            <script data-main="scripts/main" src="scripts/require.js"></script>
        </head>
        <body>
            <h1>My Sample Project</h1>
        </body>
    </html>

Modules:

    !javascript
    // scripts/main.js
    require(["helper/util"], function(util) {
      util.test // -> I am a util
    });

    // scripts/helper/util.js
    define(function() {
      return { test: 'I am a util' };
    });

---

## CommonJS modules

[CommonJS specification](http://wiki.commonjs.org/wiki/Modules/1.1) for loading modules in JavaScript.
Used by NodeJS. Provides `module`, `exports` and `require`.

    !javascript
    // say_hi.js
    var privateVariable = 'Hello ';

    module.exports = {
      sayHi : function(name) {
        return privateVariable + name;
      }
    }

    // module.js
    var hisayer = require('say_hi');

    exports.result = hisayer.sayHi('David');
    exports.sayHi = hisayer

    // app.js
    var mod = require('./module');

    module.sayHi('You'); // Hello You
    module.result; // -> Hello David

---

## Browserify

### `require('modules')` in the browser.

Lets you write NodeJS style modules for the browser.

    npm install gamma
    browserify main.js -o bundle.js

![Browserify Logo](images/browserify.png)

---

## ECMAScript 6 modules

The next version of [ECMAScript](http://wiki.ecmascript.org/doku.php?id=harmony:modules) (Specification for JavaScript)
will support loading modules:

    !javascript
    // say_hi.js
    var privateVariable = 'Hello ';

    export function sayHi(name) {
      return privateVariable + name;
    }

    // module.js
    import { sayHi } from './say_hi';

    sayHi('David');

This is still under heavy discussion.

---

# Generators

---

## [Yeoman](http://yeoman.io/)

### Modern workflows for modern web app

![Yeoman Logo](images/yeoman-logo.png)

[learningyeoman-8881.onmodulus.net](learningyeoman-8881.onmodulus.net)

Brought to you by [Sean Goresht](http://seangoresht.com/)


### What is Mimosa? 

- a surprisingly complete web application generator written for Node by [dbashford.github.com](https://dbashford.github.com) over the last nine months or so.
- Good documentation to get started with at [mimosa.io](http://mimosa.io).
- powerful and modular.
- hides many of the details of web application development so you can get started quickly.
- can hide a bit too much to do more complicated things easily.
- easy to configure.
- does not include any scaffolding, but does provide a facility to begin with pre-written skeletons.

---

## Mimosa: Features

- many JavaScript Meta-languages. 
- many template Meta-languages.
- source maps for wicked debugging sessions.
- modules for unit testing, and packaging.
- Live reload support using SocketIO.
- Optimization, minification, and dependency checking.
- Bower support.

---

## Mimosa: Meta-languages

Mimosa supports a good selection of JavaScript meta-languages that you can use within your applications.

1. Coco - https://github.com/satyr/coco
1. CoffeeScript - http://coffeescript.org/
1. Iced CoffeeScript - http://maxtaco.github.com/coffee-script/
1. LiveScript - http://gkz.github.com/LiveScript/
1. None (Raw JavaScript)
1. TypeScript - http://www.typescriptlang.org

---

## Mimosa: CSS Meta-languages

Mimosa supports a few CSS meta-languages:

1. LESS - http://lesscss.org/
1. None (Raw CSS)
1. SASS - http://sass-lang.com/
1. Stylus - http://learnboost.github.com/stylus/

---

## Mimosa: Micro-templating

Mimosa supports quite a few micro-templating libraries:

1. Dust - https://github.com/linkedin/dustjs/
1. Embedded CoffeeScript Templates (ECO) - https://github.com/sstephenson/eco
1. Embedded JavaScript Templates (EJS) - https://github.com/visionmedia/ejs
1. Emblem - http://emblemjs.com/
1. Handlebars - http://handlebarsjs.com/
1. Hogan - http://twitter.github.com/hogan.js/
1. HTML - Just Plain HTML Snippets, no compiling
1. Jade - http://jade-lang.com/
1. LoDash - http://lodash.com/docs#template
1. None (No Templating)
1. Ractive - http://www.ractivejs.org/
1. Underscore - http://underscorejs.org/#template

Some of these are also supported for the server side as well.

---

## Mimosa: Usage

Installing Mimosa is done through *npm*:

	!console
	$ sudo npm install -g mimosa

Now you can make a new web app using the *mimosa* command-line tool:

	!console
	$ mkdir mimosa-demo
	$ cd mimosa-demo
	$ mimosa new

Answer the questions, and an application will be scafolded for you.

Write your code.

---

## Mimosa: Unit Testing

* Testem module has quite a few features.
* Karma test runner support is available through a module.
* jasmine-node module exists, and it will unit test the server side code.

---

## Mimosa: Web Packaging

* Use the *web-package* module to create a server that can be deployed to *heroku*.
* add 'web-package' to the modules list.
* run 'make pack' or 'mimosa build -p'

---

## [Mimosa](http://mimosa.io/)

### A modern browser development toolkit

![Mimosa Logo](images/mimosa-hat.png)

Brought to you by [Neal Sanche](https://github.com/thorinside)

---

## [Next Month](http://www.meetup.com/YYC-js/events/131079442/)

- SEO
    - What is it?
    - Protips & tools
    - Tricks to improve SEO
    - SEO techniques for JS apps
- i18n
    - Why is it called i18n, why does it matter?
    - Libs & tools you can use
    - Client side vs. server side localization
    - Crowd sourcing i18n
