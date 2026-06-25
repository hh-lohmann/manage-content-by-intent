###### Concept

# Manage content by intent

Restricted set for categories of intent to manage contents to work with.


## Rationale

Categorizing content helps to decide about the tools and best practices for working with it.

Categoration becomes less helpful with too many possible categories.

The following tries to categorize by the intent for using a respective content, namely: who authors the content for which audience to do what.


## Considerations

### Manageable number of categorizing directories

Categorization leads to absurdity if the number of categories is not restricted. Following the well established Miller's Law, the maximum number of categories ideally is between 5 and 7.


### Categorize by intent

To decide in which category a certain content should be found or put in, an intentionally minimum number of properties or questions and answers about its intent is taken into account:

  * Who **authors** the content?
    * possible answers: others, self
  * Which **audience** is targeted by the content?
    * possible answers: others, self
  * What **usage** of the content is intended?
    * possible answers: apply, consult, execute, reconstruct, try-out

where the **possible answers** mean

  * **self**
    * The person working with the content
  * **others**
    * Not the person working with the content
  * **apply**
    * adaptive application of content, in contrast to "as-is" application with **execute**
  * **consult**
    * reasoning about content, maybe without applying it
  * **execute**
    * "as-is" application of content, in contrast to adaptive application with **apply**
  * **reconstruct**
    * compare former content
    * only defined for **self** as a special case of **consult**
  * **try-out**
    * experiment with content
    * only defined for **self** as a special case of **consult** 


## Categories by intent

### Overview

| Category        | Generalized resolution         |
| ----------------------- | ---------------------- |
| [concepts](#concepts)   | self - X - apply       |
| [logs](#logs)           | self - X - reconstruct |
| [memos](#memos)         | self - X - consult     |
| [releases](#releases)   | self - X - execute     |
| [resources](#resources) | others - X - X         |
| [try-outs](#try-outs)   | self - X - try-out     |


### Types and Tokens

Categories named with the plural form of their type name, e.g. "concepts", a single token of a category / type is named with the corresponding singular form, e.g. "concept".


### Naming of categories

Category names are rather alluding than defining, mainly representing a semantic field of similar concepts.

Actual categorization should not happen by category names, but by [operational categorization](#operational-categorization).


### Operational categorization

Resolution scheme: author/s - audience - usage

#### Explicit resolution paths

With similar paths (compare [Generalized paths](#generalized-resolution-paths)).


| Resolution path           | Category  |
| ------------------------- | --------- |
| others - self - apply     | resources |
| others - self - consult   | resources |
| others - self - execute   | resources |
| self - others - apply     | concepts  |
| self - others - consult   | memos     |
| self - others - execute   | releases  |
| self - self - apply       | concepts  |
| self - self - consult     | memos     |
| self - self - execute     | releases  |
| self - self - reconstruct | logs      |
| self - self - try-out     | try-outs  |


#### Generalized resolution paths

Collapsing similar paths with `X` for non-distinguishing part (compare [Full paths](#explicit-resolution-paths)).


| Resolution path        | Category  |
| ---------------------- | --------- |
| others - X - X         | resources |
| self - X - apply       | concepts  |
| self - X - consult     | memos     |
| self - X - execute     | releases  |
| self - X - reconstruct | logs      |
| self - X - try-out     | try-outs  |




### Details

#### concepts
  * author: self
  * audience: others, self
  * usage: apply

#### logs
  * author: self
  * audience: self
  * usage: reconstruct

#### memos
  * author: self
  * audience: others
  * usage: consult

#### releases
  * **! does not mean only released content, but also contents supplementary for creating releases**
  * author: self
  * audience: others, self
  * usage: execute
  * **Key for [package.json](#use-with-packagejson) and [README.md](#use-with-readmemd) to be set as the purpose of the release, e.g. "npm package", "PHP routine"**

#### resources
  * **! does not mean primarily copies of resources, but content about resources**
  * **special category: mainly references to be used by contents in other categories**
  * author: others
  * audience: self
  * usage: apply, consult, execute

#### try-outs
  * author: self
  * audience: self
  * usage: try-out


## Use with package.json

A content stored in a file system should inform about itself by a `package.json`, especially [if it is not an executable Node / npm package](#hh-lohmann-using-packagejson-without-javascript-exports).

If a [release](#releases) is not an executable npm package, a package.json key `intent` should give a [token name](#types-and-tokens) depicting a [category (type)](#overview), e.g.

```json
  {
    "name": "manage-content-by-intent",
    "description": "Restricted set for categories of intent to manage contents to work with.",
    "intent": "concept"
  }
```

For executable npm packages the intent must not be stated explicitly since it is intrinsic.


## Use with README.md

Good development and presentation utilizes a [README file](#wikipedia-readme-files) as an entry point or introduction or delivering content itself, in modern web context formatted with human readable Markdown as README.md.

Using a project's / content's intent as a category header improves quick acquaintance of what things are about. To mark it as a kind of heading, but a meta information that is not a part of the actual content, it should be formatted as a heading outside of the regular heading hierarchy by using the lowest possible heading level to be followed by the README's title formatted as the top level heading:

```
  ###### ...intent...

  # ...title...

  ...
```

For executable npm packages the intent must not be stated explicitly in the README.md that is published to the npm registry, but should be kept in a version provided as a GitHub repo and / or on GitHub Pages.



## Use for root level directories

The [described set of categories](#overview) qualify directly for equivalently named and intended directories if

  * all category directories are at the same level
  * no other directories are given at the same level
    * exceptions may be special directories marked by a leading `.` (dot), `_` (underscore) or numerical prefixes like `01_`
  * the directory level is a root level in the sense that
    * a possible parent level's properties are shared by all category directories
      * user rights, environments etc.
    * no parent level itself expresses one of the categories used here
  
A typical example for a root level in the sense here is a user / home directory.


## References

### hh lohmann: Using package.json without JavaScript exports
  * <https://hh-lohmann.github.io/package-json-no-js/>

### Wikipedia: README files
  * <https://en.wikipedia.org/wiki/README>


<!-- see https://hh-lohmann.github.io/html-endspacer -->
<p id="endspacer" data-version="0.2.0" title="Endspacer - helps to align scrolling and positioning link targets | Scroll up to content or click / touch to jump to page top" align="center"><a href="#top"><img alt="Endspacer: './markdown-assets/endspacer.png' missing - see https://hh-lohmann.github.io/html-endspacer" src="./markdown-assets/endspacer.png" height="1000" width="100%"><br>[top]</a></p>
