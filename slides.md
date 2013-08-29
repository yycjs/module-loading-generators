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
	define(['say_hi.js'], function(hisayer) {
		return {
			result : hisayer.sayHi('David'),
			sayHi : hisayer
		}
	});

	// app.js
	var module = require('module.js', function(module) {
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

*scripts/main.js*

    !javascript
    require(["helper/util"], function(util) {
      util.test // -> I am a util
    });

*scripts/helper/util.js*

    !javascript
    define(function() {
      return { test: 'I am a util' };
    });

---

## CommonJS modules

Used in Node

E

---

## Browserify

E

---

## Component

O

---

## ECMAScript 6 modules

E

---

# Generators

---

## Yeoman

---

## Mimosa

---

## Next Month

### SEO & i18n
