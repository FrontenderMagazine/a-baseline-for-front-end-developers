# A Baseline for Front-End Developers

I wrote a README the other day for a project that I’m hoping other developers
will look at and learn from, and as I was writing it, I realized that it was the
sort of thing that might have intimidated the hell out of me a couple of years
ago, what with its casual mentions of Node, npm, Homebrew, git, tests, and
development and production builds.

Once upon a time, editing files, testing them locally (as best as we could,
anyway), and then FTPing them to the server was the essential workflow of a
front-end dev. We measured our mettle based on our ability to wrangle IE6 into
submission or achieve pixel perfection across browsers. Many members of the
community – myself included – lacked traditional programming experience. HTML,
CSS, and JavaScript – usually in the form of jQuery – were self-taught skills.

Something has changed in the last couple of years. Maybe it’s the result of
people starting to take front-end dev seriously, maybe it’s browser vendors
mostly getting their shit together, or maybe it’s front-end devs – again, myself
included – coming to see some well-established light about the process of
software development.

Whatever it is, I think we’re seeing the emphasis shift from valuing trivia to
valuing tools. There’s a new set of baseline skills required in order to be
successful as a front-end developer, and developers who don’t meet this baseline
are going to start feeling more and more left behind as those who are sharing
their knowledge start to assume that certain things go without saying.

Here are a few things that I want to start expecting people to be familiar with,
along with some resources you can use if you feel like you need to get up to
speed. (Thanks to Paul Irish, Mike Taylor, Angus Croll, and Vlad Filippov for
their contributions.)

## JavaScript

This might go without saying, but simply knowing a JavaScript library isn’t
sufficient any more. I’m not saying you need to know how to implement all the
features of a library in plain JavaScript, but you should know when a library is
actually required, and be capable of working with plain old JavaScript when it’s
not.

That means that you’ve read [JavaScript: The Good Parts][1] – hopefully more
than once. You understand data structures like objects and arrays; functions,
including how and why you would `call` and `apply` them; working with prototypal
inheritance; and managing the asynchronicity of it all.

If your plain JS fu is weak, here are some resources to help you out:

* [Eloquent Javascript][2]: A wonderful book (also available in print) that 
takes you back to JavaScript basics
* [A Test-Driven JS Assessment][3]: A set of failing tests that cover various 
JavaScript topics; can you write code to make the tests pass?
* [10 things I learned from the jQuery Source][4] is an oldie but goodie from 
Paul Irish that shows what you can learn by reading other people’s code.

## Git (and a Github account)

If you’re not on Github, you’re essentially unable to participate in the rich
open-source community that has arisen around front-end development technologies.
Cloning a repo to try it out should be second-nature to you, and you should
understand how to [use branches on collaborative projects][5].

Need to boost your git skills?

* [help.github.com][6]
* [Github git cheat sheet][7]
* [More cheat sheet][8]
* [More git links][9]

## Modularity, dependency management, and production builds

The days of managing dependencies by throwing one more script or style tag on
the page are long gone. Even if you haven’t been able to incorporate great tools
like [RequireJS][10] into your workflow at work, you should find time to
investigate them in a personal project or in a project like [Backbone
Boilerplate][11], because the benefits they convey are huge. RequireJS in
particular lets you develop with small, modular JS and CSS files, and then
concatenates and minifies them via its optimization tool for production use.

Skeptical of AMD? That’s no excuse to be doing nothing. At the very least, you
should be aware of tools like [UglifyJS][12] or [Closure Compiler][13] that will
intelligently minify your code, and then concatenate those minified files prior
to production.

If you’re writing plain CSS – that is, if you’re not using a preprocessor like
Sass or Stylus – RequireJS can help you keep your CSS files modular, too. Use
`@import` statements in a base file to load dependencies for development, and
then run the RequireJS [optimizer][14] on the base file to create a file built
for production.

## In-Browser Developer Tools

Browser-based development tools have improved tremendously over the last couple
of years, and they can dramatically improve your development experience if you
know how to use them. (Hint: if you’re still using `alert` to debug your code,
you’re wasting a lot of time.)

You should probably find one browser whose developer tools you primarily use –
I’m partial to [Google Chrome’s Developer Tools][15] these days – but don’t
dismiss the tools in other browsers out of hand, because they are constantly
adding useful features based on developer feedback. Opera’s [Dragonfly][16] in
particular has some features that make its developer tools stand out, such as an
(experimental) CSS profiler, customizable keyboard shortcuts, remote debugging
without requiring a USB connection, and the ability to save and use custom color
palettes.

If your understanding of browser dev tools is limited, [Fixing these jQuery][17]
is a great (and not particularly jQuery-centric) overview of debugging,
including how to do [step debugging][18] – a life-altering thing to learn if you
don’t already know it.

## The command line

Speaking of the command line, being comfortable with it is no longer optional –
you’re missing out on way too much if you’re not ready to head over to a
terminal window and get your hands dirty. I’m not saying you have to do
*everything* in the terminal – I won’t take your git GUI away from you even
though I think you’ll be better off without it eventually – but you should
absolutely have a terminal window open for whatever project you’re working on.
There are a few command line tasks you should be able to do without thinking:

* `ssh` to log in to another machine or server
* `scp` to copy files to another machine or server
* `awk` or `grep` to find files in a project that contain a string or pattern
* `find` to locate files whose names match a given pattern
* `git` to do at least basic things like `add`, `commit`, `status`, and `pull`
* `brew` to use Homebrew to install packages
* `npm` to install Node packages
* `gem` to install Ruby packages

If there are commands you use frequently, edit your `.bashrc` or `.profile` or
`.zshrc` or whatever, and create an [alias][19] so you don’t have to type as
much. You can also add aliases to your `~/.gitconfig` file. Gianni Chiappetta’s
[dotfiles][20] are an excellent inspiration for what’s possible.

*Note: If you’re on Windows, I don’t begin to know how to help you, aside from 
suggesting [Cygwin][21]. Right or wrong, participating in the open-source 
front-end developer community is materially more difficult on a Windows machine. 
On the bright side, MacBook Airs are cheap, powerful, and ridiculously portable, 
and there’s always Ubuntu or another *nix.*

## Client-side templating

It wasn’t so long ago that it was entirely typical for servers to respond to
XHRs with a snippet of HTML, but sometime in the last 12 to 18 months, the
front-end dev community saw the light and started demanding pure data from the
server instead. Turning that data into HTML ready to be inserted in the DOM can
be a messy and unmaintainable process if it’s done directly in your code. That’s
where [client-side templating libraries][22] come in: they let you maintain
templates that, when mixed with some data, turn into a string of HTML. Need help
picking a templating tool? Garann Means’ [template chooser][23] can point you in
the right direction.

## CSS preprocessors

Paul Irish [noted][24] the other day that we’re starting to see front-end devs
write code that’s very different from what ends up in production, and code
written with CSS preprocessors is a shining example of this. There’s still a
vocal crowd that feels that pure CSS is the only way to go, but they’re
[starting to come around][25]. These tools give you features that arguably
should be in CSS proper by now – variables, math, logic, mixins – and they can
also help smooth over the CSS property prefix mess.

## Testing

One of the joys of writing modular, loosely coupled code is that your code
becomes vastly easier to test, and with tools like [Grunt][26], setting up a
project to include tests has never been easier. Grunt comes with QUnit
integration, but there are a host of testing frameworks that you can choose from
– [Jasmine][27] and [Mocha][28] are a couple of my current favorites – depending
on your preferred style and the makeup of the rest of your stack.

While testing is a joy when your code is modular and loosely coupled, testing
code that’s not well organized can be somewhere between difficult and
impossible. On the other hand, forcing yourself to write tests – perhaps before
you even write the code – will help you organize your thinking and your code. It
will also let you refactor your code with greater confidence down the line.

* A short [screencast][29] I recorded about testing your jQuery with Jasmine.
* An example of [unit tests][30] on the jquery-bbq plugin.

## Process automation (rake/make/grunt/etc.)

Grunt’s ability to set up a project with built-in support for unit tests is one
example of process automation. The reality of front-end development is that
there’s a whole lot of repetitive stuff we have to do, but as a friend once told
me, a good developer is a lazy developer: as a rule of thumb, if you find
yourself doing the same thing three times, it’s time to automate it.

Tools like `make` have been around for a long time to help us with this, but
there’s also `rake`, `grunt`, and others. Learning a language other than
JavaScript can be extremely helpful if you want to automate tasks that deal with
the filesystem, as Node’s async nature can become a real burden when you’re just
manipulating files. There are lots of task-specific automation tools, too –
tools for deployment, build generation, code quality assurance, and more.

## Code quality

If you’ve ever been bitten by a missing semicolon or an extra comma, you know
how much time can be lost to subtle flaws in your code. That’s why you’re
running your code through a tool like [JSHint][31], right? It’s
[configurable][32] and has lots of ways to integrate it into your [editor or
build process][33].

## The fine manual

Alas, there is no manual for front-end development, but [MDN][34] comes pretty
close. Good front-end devs know to prefix any search engine query with `mdn` –
for example, `mdn javascript arrays` – in order to avoid the for-profit plague
that is w3schools.

## The End

As with anything, reading about these things won’t make you an expert, or even
moderately skilled – the only surefire way to get better at a thing is to [do
that thing][35]. Good luck.

[1]: http://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742
[2]: http://eloquentjavascript.net/
[3]: https://github.com/rmurphey/js-assessment
[4]: http://paulirish.com/2010/10-things-i-learned-from-the-jquery-source/
[5]: http://nvie.com/posts/a-successful-git-branching-model/
[6]: http://help.github.com/
[7]: http://help.github.com/git-cheat-sheets/
[8]: http://cheat.errtheblog.com/s/git
[9]: http://pinboard.in/u:rmurphey/t:git/
[10]: http://requirejs.org/
[11]: https://github.com/tbranyen/backbone-boilerplate
[12]: https://github.com/mishoo/UglifyJS
[13]: https://developers.google.com/closure/compiler/
[14]: http://requirejs.org/docs/optimization.html#onecss
[15]: https://developers.google.com/chrome-developer-tools/
[16]: http://my.opera.com/dragonfly/blog/
[17]: http://fixingthesejquery.com/#slide1
[18]: https://developers.google.com/chrome-developer-tools/docs/scripts-breakpoints
[19]: http://tldp.org/LDP/abs/html/aliases.html
[20]: https://github.com/gf3/dotfiles
[21]: http://www.cygwin.com/
[22]: http://www.slideshare.net/garann/using-templates-to-achieve-awesomer-architecture
[23]: http://garann.github.com/template-chooser/
[24]: https://twitter.com/#!/paul_irish/status/188329390822801409
[25]: http://www.stuffandnonsense.co.uk/blog/about/less
[26]: https://github.com/cowboy/grunt
[27]: https://github.com/pivotal/jasmine/wiki
[28]: http://visionmedia.github.com/mocha/
[29]: http://vimeo.com/20457625
[30]: https://github.com/cowboy/jquery-bbq/blob/master/unit/unit.js
[31]: http://www.jshint.com/
[32]: http://www.jshint.com/options/
[33]: http://www.jshint.com/platforms/
[34]: https://developer.mozilla.org/en-US/
[35]: http://rmurphey.com/blog/2011/05/20/getting-better-at-javascript/
