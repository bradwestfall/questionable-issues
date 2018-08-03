# Question Authoring Guidelines

The following is a list of guidelines which we ask all Questionable Marketplace Authors to follow while writing test and question content. These guidelines are meant to keep question writing more consistent among authors and to keep the quality of question writing at a high level.

For the purposes of this guide, all examples will be demonstrated in the Web languages: HTML, CSS, and JavaScript.

## Terms

- **Marketplace Author:** The person writing tests for the purpose of publishing them into the Marketplace for sale (presumably you).
- **Test Admin:** The administrator of a test. In once sense, the Marketplace Author is technically the Test Admin of their tests, but for the purpose of this document, the person buying your test to administer it to others is also the Test Admin (of the copy of the test they bought).
- **Test Taker:** The end-user taking the test with the oversight of the Test Admin.

## Tags

When a user buys a test (and therefore its questions) from the marketplace, each question's tags will also be copied down to the buyer's account. The tags that the buyer gets from your questions will be mixed with all the tags they have also written and that they have received from other Marketplace test questions from other Authors. For this reason, there needs to be a high degree of consistency when it comes to writing tags for the marketplace.

Tags are meant to categorize the question in ways that will be meaningful for reports and searching. Specifically, there is a "Gap Analysis" report which takes a test takers responses and groups them by tag name to show the Test Admin which tags the test taker did well on. This grouping is a case-sensitive string based grouping. This report and other significant features are big selling points for Questionable so this is why it is very important that **all questions** be tagged with at least one tag, but more are preferred (2-4 can be considered an average).

Unless there's a good reason to do otherwise, tags should be written as titles (with the first letter of each word capitalized), such as `Arrow Functions`, not `arrow functions`. Common acronyms like `HTML` can be written in all-caps.

### Tagging Strategy

Tags should describe the makeup of the main parts of the question **that are being tested**. For example consider this question:

_What will the value of `finalResult` be?_

```js
const primary = { name: 'Dave', age: 56, job: 'driver' }
const secondary = { name: 'Sarah', age: 34 }
const finalResult = { primary, ...secondary }
```

The tags for this question would be `JavaScript`, `ES6`, `Objects`, `Spread Operator`.


## Writing Good Questions

Writing multiple choice questions is somewhat of an art-form. You'll get better at it over time if you work on it and see the feedback firsthand from test takers
