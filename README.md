# middleman-shadow-cljs
[Middleman](http://middlemanapp.com/) project template with [shadow-cljs](http://shadow-cljs.org/).

## Prerequisites
* [Middleman](https://middlemanapp.com/)
* [Yarn](https://yarnpkg.com)

## Usage
### Generating a new project
To generate a new project, use Middleman's `-T` option. There's no need to download the template separately. For example:

```bash
middleman init my_project -T bnadlerjr/middleman-shadow-cljs
```

After generating the project, Middleman will automatically run `yarn install` to install the Javascript dependencies.

### Development
Run `middleman server` as normal, ClojureScript compilation will take place automatically.

#### Rake
Several Rake tasks are provided for convienence:

`rake server`: starts the middleman server
`rake autotest`: starts Karma and automatically runs tests when files are changed
`rake ci`: runs Karma tests with Karma's `--single-run` option

### Production
Run `middleman build` as normal.

## License
(The MIT License)

Copyright (c) 2018 Bob Nadler, Jr.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
