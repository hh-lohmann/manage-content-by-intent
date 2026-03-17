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

A content stored in a file system should inform about itself by a `package.json`, even if it is not a Node / npm package.

A key `intent` should give a [token name](#types-and-tokens) depicting a [category (type)](#overview), e.g.

```json
  {
    "name": "manage-content-by-intent",
    "description": "Restricted set for categories of intent to manage contents to work with.",
    "intent": "concept"
  }
```


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
