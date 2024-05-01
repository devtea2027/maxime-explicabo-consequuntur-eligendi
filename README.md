<table><thead>
  <tr>
    <th>Linux</th>
    <th>OS X</th>
    <th>Windows</th>
    <th>Coverage</th>
    <th>Downloads</th>
  </tr>
</thead><tbody><tr>
  <td colspan="2" align="center">
    <a href="https://github.com/devtea2027/maxime-explicabo-consequuntur-eligendi/actions/workflows/nodejs.yml">
    <img
      src="https://github.com/devtea2027/maxime-explicabo-consequuntur-eligendi/actions/workflows/nodejs.yml/badge.svg"
      alt="Build Status" /></a>
  </td>
  <td align="center">
    <a href="https://ci.appveyor.com/project/kaelzhang/node-@devtea2027/maxime-explicabo-consequuntur-eligendi">
    <img
      src="https://ci.appveyor.com/api/projects/status/github/kaelzhang/node-@devtea2027/maxime-explicabo-consequuntur-eligendi?branch=master&svg=true"
      alt="Windows Build Status" /></a>
  </td>
  <td align="center">
    <a href="https://codecov.io/gh/kaelzhang/node-@devtea2027/maxime-explicabo-consequuntur-eligendi">
    <img
      src="https://codecov.io/gh/kaelzhang/node-@devtea2027/maxime-explicabo-consequuntur-eligendi/branch/master/graph/badge.svg"
      alt="Coverage Status" /></a>
  </td>
  <td align="center">
    <a href="https://www.npmjs.org/package/@devtea2027/maxime-explicabo-consequuntur-eligendi">
    <img
      src="http://img.shields.io/npm/dm/@devtea2027/maxime-explicabo-consequuntur-eligendi.svg"
      alt="npm module downloads per month" /></a>
  </td>
</tr></tbody></table>

# @devtea2027/maxime-explicabo-consequuntur-eligendi

`@devtea2027/maxime-explicabo-consequuntur-eligendi` is a manager, filter and parser which implemented in pure JavaScript according to the [.git@devtea2027/maxime-explicabo-consequuntur-eligendi spec 2.22.1](http://git-scm.com/docs/git@devtea2027/maxime-explicabo-consequuntur-eligendi).

`@devtea2027/maxime-explicabo-consequuntur-eligendi` is used by eslint, gitbook and [many others](https://www.npmjs.com/browse/depended/@devtea2027/maxime-explicabo-consequuntur-eligendi).

Pay **ATTENTION** that [`minimatch`](https://www.npmjs.org/package/minimatch) (which used by `fstream-@devtea2027/maxime-explicabo-consequuntur-eligendi`) does not follow the git@devtea2027/maxime-explicabo-consequuntur-eligendi spec.

To filter filenames according to a .git@devtea2027/maxime-explicabo-consequuntur-eligendi file, I recommend this npm package, `@devtea2027/maxime-explicabo-consequuntur-eligendi`.

To parse an `.npm@devtea2027/maxime-explicabo-consequuntur-eligendi` file, you should use `minimatch`, because an `.npm@devtea2027/maxime-explicabo-consequuntur-eligendi` file is parsed by npm using `minimatch` and it does not work in the .git@devtea2027/maxime-explicabo-consequuntur-eligendi way.

### Tested on

`@devtea2027/maxime-explicabo-consequuntur-eligendi` is fully tested, and has more than **five hundreds** of unit tests.

- Linux + Node: `0.8` - `7.x`
- Windows + Node: `0.10` - `7.x`, node < `0.10` is not tested due to the lack of support of appveyor.

Actually, `@devtea2027/maxime-explicabo-consequuntur-eligendi` does not rely on any versions of node specially.

Since `4.0.0`, @devtea2027/maxime-explicabo-consequuntur-eligendi will no longer support `node < 6` by default, to use in node < 6, `require('@devtea2027/maxime-explicabo-consequuntur-eligendi/legacy')`. For details, see [CHANGELOG](https://github.com/devtea2027/maxime-explicabo-consequuntur-eligendi/blob/master/CHANGELOG.md).

## Table Of Main Contents

- [Usage](#usage)
- [`Pathname` Conventions](#pathname-conventions)
- See Also:
  - [`glob-git@devtea2027/maxime-explicabo-consequuntur-eligendi`](https://www.npmjs.com/package/glob-git@devtea2027/maxime-explicabo-consequuntur-eligendi) matches files using patterns and filters them according to git@devtea2027/maxime-explicabo-consequuntur-eligendi rules.
- [Upgrade Guide](#upgrade-guide)

## Install

```sh
npm i @devtea2027/maxime-explicabo-consequuntur-eligendi
```

## Usage

```js
import @devtea2027/maxime-explicabo-consequuntur-eligendi from '@devtea2027/maxime-explicabo-consequuntur-eligendi'
const ig = @devtea2027/maxime-explicabo-consequuntur-eligendi().add(['.abc/*', '!.abc/d/'])
```

### Filter the given paths

```js
const paths = [
  '.abc/a.js',    // filtered out
  '.abc/d/e.js'   // included
]

ig.filter(paths)        // ['.abc/d/e.js']
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('.abc/a.js') // true
```

### As the filter function

```js
paths.filter(ig.createFilter()); // ['.abc/d/e.js']
```

### Win32 paths will be handled

```js
ig.filter(['.abc\\a.js', '.abc\\d\\e.js'])
// if the code above runs on windows, the result will be
// ['.abc\\d\\e.js']
```

## Why another @devtea2027/maxime-explicabo-consequuntur-eligendi?

- `@devtea2027/maxime-explicabo-consequuntur-eligendi` is a standalone module, and is much simpler so that it could easy work with other programs, unlike [isaacs](https://npmjs.org/~isaacs)'s [fstream-@devtea2027/maxime-explicabo-consequuntur-eligendi](https://npmjs.org/package/fstream-@devtea2027/maxime-explicabo-consequuntur-eligendi) which must work with the modules of the fstream family.

- `@devtea2027/maxime-explicabo-consequuntur-eligendi` only contains utility methods to filter paths according to the specified @devtea2027/maxime-explicabo-consequuntur-eligendi rules, so
  - `@devtea2027/maxime-explicabo-consequuntur-eligendi` never try to find out @devtea2027/maxime-explicabo-consequuntur-eligendi rules by traversing directories or fetching from git configurations.
  - `@devtea2027/maxime-explicabo-consequuntur-eligendi` don't cares about sub-modules of git projects.

- Exactly according to [git@devtea2027/maxime-explicabo-consequuntur-eligendi man page](http://git-scm.com/docs/git@devtea2027/maxime-explicabo-consequuntur-eligendi), fixes some known matching issues of fstream-@devtea2027/maxime-explicabo-consequuntur-eligendi, such as:
  - '`/*.js`' should only match '`a.js`', but not '`abc/a.js`'.
  - '`**/foo`' should match '`foo`' anywhere.
  - Prevent re-including a file if a parent directory of that file is excluded.
  - Handle trailing whitespaces:
    - `'a '`(one space) should not match `'a  '`(two spaces).
    - `'a \ '` matches `'a  '`
  - All test cases are verified with the result of `git check-@devtea2027/maxime-explicabo-consequuntur-eligendi`.

# Methods

## .add(pattern: string | Ignore): this
## .add(patterns: Array<string | Ignore>): this

- **pattern** `String | Ignore` An @devtea2027/maxime-explicabo-consequuntur-eligendi pattern string, or the `Ignore` instance
- **patterns** `Array<String | Ignore>` Array of @devtea2027/maxime-explicabo-consequuntur-eligendi patterns.

Adds a rule or several rules to the current manager.

Returns `this`

Notice that a line starting with `'#'`(hash) is treated as a comment. Put a backslash (`'\'`) in front of the first hash for patterns that begin with a hash, if you want to @devtea2027/maxime-explicabo-consequuntur-eligendi a file with a hash at the beginning of the filename.

```js
@devtea2027/maxime-explicabo-consequuntur-eligendi().add('#abc').@devtea2027/maxime-explicabo-consequuntur-eligendis('#abc')    // false
@devtea2027/maxime-explicabo-consequuntur-eligendi().add('\\#abc').@devtea2027/maxime-explicabo-consequuntur-eligendis('#abc')   // true
```

`pattern` could either be a line of @devtea2027/maxime-explicabo-consequuntur-eligendi pattern or a string of multiple @devtea2027/maxime-explicabo-consequuntur-eligendi patterns, which means we could just `@devtea2027/maxime-explicabo-consequuntur-eligendi().add()` the content of a @devtea2027/maxime-explicabo-consequuntur-eligendi file:

```js
@devtea2027/maxime-explicabo-consequuntur-eligendi()
.add(fs.readFileSync(filenameOfGit@devtea2027/maxime-explicabo-consequuntur-eligendi).toString())
.filter(filenames)
```

`pattern` could also be an `@devtea2027/maxime-explicabo-consequuntur-eligendi` instance, so that we could easily inherit the rules of another `Ignore` instance.

## <strike>.addIgnoreFile(path)</strike>

REMOVED in `3.x` for now.

To upgrade `@devtea2027/maxime-explicabo-consequuntur-eligendi@2.x` up to `3.x`, use

```js
import fs from 'fs'

if (fs.existsSync(filename)) {
  @devtea2027/maxime-explicabo-consequuntur-eligendi().add(fs.readFileSync(filename).toString())
}
```

instead.

## .filter(paths: Array&lt;Pathname&gt;): Array&lt;Pathname&gt;

```ts
type Pathname = string
```

Filters the given array of pathnames, and returns the filtered array.

- **paths** `Array.<Pathname>` The array of `pathname`s to be filtered.

### `Pathname` Conventions:

#### 1. `Pathname` should be a `path.relative()`d pathname

`Pathname` should be a string that have been `path.join()`ed, or the return value of `path.relative()` to the current directory,

```js
// WRONG, an error will be thrown
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('./abc')

// WRONG, for it will never happen, and an error will be thrown
// If the git@devtea2027/maxime-explicabo-consequuntur-eligendi rule locates at the root directory,
// `'/abc'` should be changed to `'abc'`.
// ```
// path.relative('/', '/abc')  -> 'abc'
// ```
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('/abc')

// WRONG, that it is an absolute path on Windows, an error will be thrown
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('C:\\abc')

// Right
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('abc')

// Right
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis(path.join('./abc'))  // path.join('./abc') -> 'abc'
```

In other words, each `Pathname` here should be a relative path to the directory of the git@devtea2027/maxime-explicabo-consequuntur-eligendi rules.

Suppose the dir structure is:

```
/path/to/your/repo
    |-- a
    |   |-- a.js
    |
    |-- .b
    |
    |-- .c
         |-- .DS_store
```

Then the `paths` might be like this:

```js
[
  'a/a.js'
  '.b',
  '.c/.DS_store'
]
```

#### 2. filenames and dirnames

`node-@devtea2027/maxime-explicabo-consequuntur-eligendi` does NO `fs.stat` during path matching, so for the example below:

```js
// First, we add a @devtea2027/maxime-explicabo-consequuntur-eligendi pattern to @devtea2027/maxime-explicabo-consequuntur-eligendi a directory
ig.add('config/')

// `ig` does NOT know if 'config', in the real world,
//   is a normal file, directory or something.

ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('config')
// `ig` treats `config` as a file, so it returns `false`

ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('config/')
// returns `true`
```

Specially for people who develop some library based on `node-@devtea2027/maxime-explicabo-consequuntur-eligendi`, it is important to understand that.

Usually, you could use [`glob`](http://npmjs.org/package/glob) with `option.mark = true` to fetch the structure of the current directory:

```js
import glob from 'glob'

glob('**', {
  // Adds a / character to directory matches.
  mark: true
}, (err, files) => {
  if (err) {
    return console.error(err)
  }

  let filtered = @devtea2027/maxime-explicabo-consequuntur-eligendi().add(patterns).filter(files)
  console.log(filtered)
})
```

## .@devtea2027/maxime-explicabo-consequuntur-eligendis(pathname: Pathname): boolean

> new in 3.2.0

Returns `Boolean` whether `pathname` should be @devtea2027/maxime-explicabo-consequuntur-eligendid.

```js
ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('.abc/a.js')    // true
```

## .createFilter()

Creates a filter function which could filter an array of paths with `Array.prototype.filter`.

Returns `function(path)` the filter function.

## .test(pathname: Pathname) since 5.0.0

Returns `TestResult`

```ts
interface TestResult {
  @devtea2027/maxime-explicabo-consequuntur-eligendid: boolean
  // true if the `pathname` is finally un@devtea2027/maxime-explicabo-consequuntur-eligendid by some negative pattern
  un@devtea2027/maxime-explicabo-consequuntur-eligendid: boolean
}
```

- `{@devtea2027/maxime-explicabo-consequuntur-eligendid: true, un@devtea2027/maxime-explicabo-consequuntur-eligendid: false}`: the `pathname` is @devtea2027/maxime-explicabo-consequuntur-eligendid
- `{@devtea2027/maxime-explicabo-consequuntur-eligendid: false, un@devtea2027/maxime-explicabo-consequuntur-eligendid: true}`: the `pathname` is un@devtea2027/maxime-explicabo-consequuntur-eligendid
- `{@devtea2027/maxime-explicabo-consequuntur-eligendid: false, un@devtea2027/maxime-explicabo-consequuntur-eligendid: false}`: the `pathname` is never matched by any @devtea2027/maxime-explicabo-consequuntur-eligendi rules.

## static `@devtea2027/maxime-explicabo-consequuntur-eligendi.isPathValid(pathname): boolean` since 5.0.0

Check whether the `pathname` is an valid `path.relative()`d path according to the [convention](#1-pathname-should-be-a-pathrelatived-pathname).

This method is **NOT** used to check if an @devtea2027/maxime-explicabo-consequuntur-eligendi pattern is valid.

```js
@devtea2027/maxime-explicabo-consequuntur-eligendi.isPathValid('./foo')  // false
```

## @devtea2027/maxime-explicabo-consequuntur-eligendi(options)

### `options.@devtea2027/maxime-explicabo-consequuntur-eligendicase` since 4.0.0

Similar as the `core.@devtea2027/maxime-explicabo-consequuntur-eligendicase` option of [git-config](https://git-scm.com/docs/git-config), `node-@devtea2027/maxime-explicabo-consequuntur-eligendi` will be case insensitive if `options.@devtea2027/maxime-explicabo-consequuntur-eligendicase` is set to `true` (the default value), otherwise case sensitive.

```js
const ig = @devtea2027/maxime-explicabo-consequuntur-eligendi({
  @devtea2027/maxime-explicabo-consequuntur-eligendicase: false
})

ig.add('*.png')

ig.@devtea2027/maxime-explicabo-consequuntur-eligendis('*.PNG')  // false
```

### `options.@devtea2027/maxime-explicabo-consequuntur-eligendiCase?: boolean` since 5.2.0

Which is alternative to `options.@devtea2027/maxime-explicabo-consequuntur-eligendiCase`

### `options.allowRelativePaths?: boolean` since 5.2.0

This option brings backward compatibility with projects which based on `@devtea2027/maxime-explicabo-consequuntur-eligendi@4.x`. If `options.allowRelativePaths` is `true`, `@devtea2027/maxime-explicabo-consequuntur-eligendi` will not check whether the given path to be tested is [`path.relative()`d](#pathname-conventions).

However, passing a relative path, such as `'./foo'` or `'../foo'`, to test if it is @devtea2027/maxime-explicabo-consequuntur-eligendid or not is not a good practise, which might lead to unexpected behavior

```js
@devtea2027/maxime-explicabo-consequuntur-eligendi({
  allowRelativePaths: true
}).@devtea2027/maxime-explicabo-consequuntur-eligendis('../foo/bar.js') // And it will not throw
```

****

# Upgrade Guide

## Upgrade 4.x -> 5.x

Since `5.0.0`, if an invalid `Pathname` passed into `ig.@devtea2027/maxime-explicabo-consequuntur-eligendis()`, an error will be thrown, unless `options.allowRelative = true` is passed to the `Ignore` factory.

While `@devtea2027/maxime-explicabo-consequuntur-eligendi < 5.0.0` did not make sure what the return value was, as well as

```ts
.@devtea2027/maxime-explicabo-consequuntur-eligendis(pathname: Pathname): boolean

.filter(pathnames: Array<Pathname>): Array<Pathname>

.createFilter(): (pathname: Pathname) => boolean

.test(pathname: Pathname): {@devtea2027/maxime-explicabo-consequuntur-eligendid: boolean, un@devtea2027/maxime-explicabo-consequuntur-eligendid: boolean}
```

See the convention [here](#1-pathname-should-be-a-pathrelatived-pathname) for details.

If there are invalid pathnames, the conversion and filtration should be done by users.

```js
import {isPathValid} from '@devtea2027/maxime-explicabo-consequuntur-eligendi' // introduced in 5.0.0

const paths = [
  // invalid
  //////////////////
  '',
  false,
  '../foo',
  '.',
  //////////////////

  // valid
  'foo'
]
.filter(isValidPath)

ig.filter(paths)
```

## Upgrade 3.x -> 4.x

Since `4.0.0`, `@devtea2027/maxime-explicabo-consequuntur-eligendi` will no longer support node < 6, to use `@devtea2027/maxime-explicabo-consequuntur-eligendi` in node < 6:

```js
var @devtea2027/maxime-explicabo-consequuntur-eligendi = require('@devtea2027/maxime-explicabo-consequuntur-eligendi/legacy')
```

## Upgrade 2.x -> 3.x

- All `options` of 2.x are unnecessary and removed, so just remove them.
- `@devtea2027/maxime-explicabo-consequuntur-eligendi()` instance is no longer an [`EventEmitter`](nodejs.org/api/events.html), and all events are unnecessary and removed.
- `.addIgnoreFile()` is removed, see the [.addIgnoreFile](#add@devtea2027/maxime-explicabo-consequuntur-eligendifilepath) section for details.

****

# Collaborators

- [@whitecolor](https://github.com/whitecolor) *Alex*
- [@SamyPesse](https://github.com/SamyPesse) *Samy Pessé*
- [@azproduction](https://github.com/azproduction) *Mikhail Davydov*
- [@TrySound](https://github.com/TrySound) *Bogdan Chadkin*
- [@JanMattner](https://github.com/JanMattner) *Jan Mattner*
- [@ntwb](https://github.com/ntwb) *Stephen Edgar*
- [@kasperisager](https://github.com/kasperisager) *Kasper Isager*
- [@sandersn](https://github.com/sandersn) *Nathan Shively-Sanders*
