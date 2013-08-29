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

## Our Resident Presenters

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

## Scope and namespacing

D

---

## __A__synchronous __M__odule __D__efinition

D

---

## RequireJS

D

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

## Mimosa: Unit Testing

* Testem module has quite a few features.
* Karma test runner support is available through a module.
* jasmine-node module exists, and it will unit test the server side code.

## Mimosa: Web Packaging

* Use the *web-package* module to create a server that can be deployed to *heroku*.
* add 'web-package' to the modules list.
* run 'make pack' or 'mimosa build -p'

---

## Next Month

### SEO & i18n
