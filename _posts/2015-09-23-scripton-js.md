---
title: <span></span>
---

`scripton` is a simple command-line tool for quickly compiling code from other programming languages into **ready-to-go** JavaScript.

*:construction: note: currently this is just a proof-of-concept*

# Motivation

It seems like the majority of [to-JavaScript utilities](https://github.com/jashkenas/coffeescript/wiki/List-of-languages-that-compile-to-JS) were crafted by gurus with other gurus in mind -- demonstrating cleverness and novelty, but also a significant lack of common-ground practicality.

I speak from experience here -- since the [open source to-JavaScript utility](https://github.com/humbletim/ljs) that I worked on still suffers from the same conceptual bottlenecks (ie: it's underdocumented and provides zero turn-key starting points, regrettably).  Since gurus seem to do a decent job at the actual engineering aspect and then fumble the delivery, we can't really blame them or high-five them.

Which is why `scripton` is conceived very differently than your "typical" to-JavaScript utility -- and as much as possible from the standpoint of a developer-user.

Put differently, `scripton` is imagined to be operated by *regular coding folk* who just want to *get stuff done*.

Having some experience in *at least one* of the two languages involved will go a long way, but even that becomes optional in the proposed model (ie: an *integration expert* can emerge at the project management level, coordinating between the two languages without necessarily having deep knowledge of either).

# Accessibility is a Virtue 

Personally I now think that most to-JavaScript utilities should have been made to function like `scripton` in the first place (at least, if I could go back and redo the transpilers I crafted, this is how I would redo them; and also this is how I tend to actually use transpilers in practice).

To me an accessible to-JavaScript utility is one that:

:white_check_mark: **Works out-of-the-box** &mdash; *with at least one turn-key example as a starting point*.

:white_check_mark: **Standardizes around an intuitive integration model** &mdash; *that a variety of to-JavaScript utilities can all fit into*.

:white_check_mark: **Pivots around a consistent command-line interface** &mdash; *ideally something proven and mature, like that of GCC/CLANG*.

:white_check_mark: **Quickly gets out of your way** &mdash; *once integrated and on the success path*.

:white_check_mark: **Can be systematically "uninstalled" or "deintegrated"** &mdash; *since sometimes "transpiling" proves inconsistent with expectations*.

:white_check_mark: **Encourages unit testing on both sides of the fence** &mdash; *or at least doesn't discourage or preclude it*.

The current proof-of-concept demonstrates how "passive standardization" can be used to teach some existing tools how to play nicely in such a common ground notion of reality -- and emerge ready-to-go executable JavaScript files as a result.

Next will be a proof-of-concept demonstrating how the same sort of thing can be done to emerge ready-to-go JavaScript modules.

# Quick Example

**Ruby snippet**:

```ruby
puts "hello from ruby #{RUBY_VERSION}"
```

**/usr/bin/ruby interpreter**:

```sh
$ ruby helloworld.rb
hello from ruby 1.9.3
```

**scripton | /usr/bin/node**:

```sh
# currently delegates to https://github.com/opal/opal
$ ./scripton helloworld.rb -o - | node
hello from ruby 2.1.5
```

# Status

:construction: I am currently planning the road map out in terms of "languages," which will then be implemented in terms of one or more utilities each.

In the meantime, if interested in tinkering with the proof-of-concept (which is just a node script), it's available in the repo along with some simple examples:

```sh
$ git clone https://github.com/humbletim/scripton-js
$ cd scripton-js
$ ./scripton --help
$ make test
```

(note: you will need a recent version of Node.js installed; currently tested on Linux and OSX; Windows support coming soon)

##### Get in Touch!

Over the years I've attempted to reach out to other transpiler authors and have been met rather entirely with, to put it politely, significant disinterest.  Basically anything having to do with the words "standardization" or "common ground" seems to be a no-no to mention to transpiler authors.

Nonetheless, it would be much appreciated if any transpiler authors would like to participate in making their tools compatible with the common man.  I am already proposing to do the heavy lifting so really any help from authors is icing on the cake.

Also if anybody in general has a need or experiment in mind for a particular language please send me a PM and I'll try to prioritize it.

<a id=languages></a>
# Programming Languages <span>( with to-JavaScript compilers )</span>
(partial list; in alphabetical order by internal id)
<div style='clear:both'></div>

<script>document.write("<div class=float>");</script>

|                                              | id       | Language      | Notes      | Imagined Roadmap |
|----------------------------------------------|----------|---------------|------------|------------------|
| <img src='images/langs/c-logo.png'        /> | c        | ANSI C        | :question: | ~1.6.0  |
| <img src='images/langs/coffee-logo.png'   /> | coffee   | CoffeeScript  | :eyes:     | ~0.0.0  |       
| <img src='images/langs/cpp-logo.png'      /> | cpp      | C++           | :question: | ~1.7.0  |
| <img src='images/langs/cs-logo.png'       /> | cs       | C#            | :question: | ~1.7.0  |
| <img src='images/langs/dart-logo.png'     /> | dart     | Dart          | :question: | ~0.3.0  |
| <img src='images/langs/doge-logo.png'     /> | doge     | Doge          | :question: | ~2.0.0  |
| <img src='images/langs/js-logo.png'       /> | es5      | ECMAScript5   | :question: | ~2.0.0  |
| <img src='images/langs/es6-logo.png'      /> | es6      | ECMAScript6   | :eyes:     | ~0.1.3  |
| <img src='images/langs/go-logo.png'       /> | go       | Go            | :question: | ~1.6.0  |
| <img src='images/langs/haskell-logo.png'  /> | haskell  | Haskell       | :question: | ~1.6.0  |

<script>document.write("</div>");</script>
<script>document.write("<div class=float>");</script>
|                                              | id       | Language      | Notes      | Imagined Roadmap |
|----------------------------------------------|----------|---------------|------------|------------------|
| <img src='images/langs/java-logo.png'     /> | java     | Java          | :question: | ~1.5.0  |
| <img src='images/langs/lua-logo.png'      /> | lua51    | Lua 5.1       | :eyes:     | ~0.1.1  |
| <img src='images/langs/lua-logo.png'      /> | lua52    | Lua 5.2       | :eyes:     | ~0.1.2  |
| <img src='images/langs/lisp-logo.png'     /> | lisp     | Lisp          | :question: | ~1.0.0  |
| <img src='images/langs/perl-logo.png'     /> | perl     | Perl          | :question: | ~1.4.0  |
| <img src='images/langs/php-logo.png'      /> | php      | PHP           | :eyes:     | ~1.4.0  |
| <img src='images/langs/python-logo.png'   /> | py2x     | Python 2.x    | :question: | ~1.4.0  |
| <img src='images/langs/ruby-logo.png'     /> | rb       | Ruby          | :eyes:     | ~0.1.0  |
| <img src='images/langs/scala-logo.png'    /> | scala    | Scala         | :question: | ~1.3.0  |
| <img src='images/langs/smalltalk-logo.png'/> | st       | Smalltalk     | :question: | ~1.3.0  |

<script>document.write("</div>");</script>


<script>document.write("<div class=float style=clear:both>");</script>
# Linker Targets

( potential polyfill / bootstrapping sets )

|                                                          | id    | Platform     | Notes    | Imagined Roadmap |
|----------------------------------------------------------|-------|--------------|----------|------------------|
| <img src='images/langs/no-logo.png#browser-logo.png'  /> | bom   | Web Browser  | :eyes: | ~0.1.0
| <img src='images/langs/no-logo.png#node-logo.png'     /> | ie6   | Legacy ES3   | :question: | ~0.4.0
| <img src='images/langs/no-logo.png#node-logo.png'     /> | node  | Node.js      | :eyes: | ~0.1.0
| <img src='images/langs/no-logo.png#rhino-logo.png'    /> | rhino | Java Rhino   | :question: | ~0.2.0
| <img src='images/langs/no-logo.png#mozilla-logo.png'  /> | smjs  | SpiderMonkey | :eyes: | ~0.1.0
| <img src='images/langs/no-logo.png#vr-logo.png'       /> | vr    | VR Scripting | :question: | ~0.2.0
| <img src='images/langs/no-logo.png#wsh-logo.png'      /> | wsh   | Windows Scripting Host | :question: | ~0.3.0

<script>document.write("</div>");</script>
<div style='clear:both'></div>

-----------

# Module Examples

:construction: *note: module support is not yet pushed and still requires diving a little deeper into each disparate utility to sort out, but below is how the interfaces will work in the simple, turn-key case.*

<hr class=black />
<img class='hlogo' src='images/langs/lua-logo.png' />
## Quick Lua module used with a web page:

###### Code:

```lua
-- mod.lua
return {
    version="0.0.1",
    calc=function(a,b) return a+b end
}
```

###### Build:

```sh
$ ./scripton mod.lua -o mod.module.js
```

###### Use:

```html
<!-- test.html -->
<script src='mod.module.js'></script>
<script>
  alert(mod.calc(2,2));
</script>
```

*note: current "back-end vendor" for Lua is [mherkender/lua.js](https://github.com/mherkender/lua.js)*

<hr class=black />
<img class='hlogo' src='images/langs/ruby-logo.png' />
## Quick Ruby module used on Node.js:

###### Code:

```ruby
# Mod.rb
module Mod
  version = "0.0.1"
  def Mod.calc(a,b) return a+b end
end
```

###### Build:

```sh
$ ./scripton mod.rb -o mod.module.js
```

###### Use:

```javascript
//#!/usr/bin/env node
console.warn(require('./mod.module.js').calc(2,2));
```

*note: current "back-end vendor" for Ruby is [opal/opal](https://github.com/opal/opal)*

<hr class=black />
<img class='hlogo' src='images/langs/coffee-logo.png' />
## Quick CoffeeScript command-line utility:

###### Code:

```coffee
# program.coffee
main = (argv) ->
    console.warn 'arguments: ', argv
```

###### Build:

```sh
$ ./scripton program.coffee -o program.exe.js
```

###### Use:

```sh
$ ./program.exe.js arg1 arg2
```

*note: current "back-end vendor" for CoffeeScript is [jashkenas/coffeescript](https://github.com/jashkenas/coffeescript)*

<hr class=black />

#...
