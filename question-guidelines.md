# Question Authoring Guidelines

The following is a list of guidelines which we ask all Questionable Marketplace Authors to follow while writing test and question content. These guidelines are meant to keep question writing more consistent among authors and to keep the quality of question writing at a high level.

For the purposes of this guide, all examples will be demonstrated in the Web languages: HTML, CSS, and JavaScript.

## Terms

- **Marketplace Author:** The person writing tests for the purpose of publishing them into the Marketplace for sale (presumably you).
- **Test Admin:** The administrator of a test. In once sense, the Marketplace Author is technically the Test Admin of their tests, but for the purpose of this document, the person buying your test to administer it to others is also the Test Admin (of the copy of the test they bought).
- **Test Taker:** The end-user taking the test with the oversight of the Test Admin.
- **Distractor Options:** This is an academic term for "the wrong answers" in a multiple choice question.
- **Difficulty Level:** All questions are marked for their difficulty on a 1-3 scale.

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



## Difficulty




## Before you Start

### 1. Difficulty

Before anything, you need to know what difficulty level you're aiming for with the overall test. Each question has a difficulty attribute which you'll chose so it's important to know what what the test's difficulty should end up at. However, not every question's difficulty level has to perfectly match the test's difficulty. For example, lets say there are two JavaScript tests in the marketplace for "Beginner JavaScript" and "Advanced JavaScript". Since the difficulty attribute of questions is on a 1-3 scale (1 being the easiest and 3 being the hardest) the "Beginner JavaScript" test should have mostly 1's and maybe a few 2's. The "Advanced JavaScript" might have mostly 3's and a few 2's.

The main point here is to know what your test first so you can focus making Subject Groups for the test:

### 2. Make "Subject Groups"

The purpose of the subject groups is to brainstorm and mentally prepare for the types of questions you're going to write. Don't underestimate this step. Based on the difficulty you're writing for in Step 1, this list of groups will help you stay focused on what questions to write for.

If the test is "Beginner JavaScript", your subject groups might be:
- Basic Arrays and Objects
- Loops and Conditionals
- Data Types
- _etc..._

If the test is more advanced, you can probably imagine the groups are more advanced.


## Start Writing Questions

Now that you have your subject groups, start writing a few questions in group. Perhaps one of your groups was "Objects" and you want to write a question to see if the test taker knows how to use `instanceof`.

Be deliberate on deciding what subject matter the question is testing. In this case it's "Does the test taker know how to use `instanceof`". Then consider the "ways" that you can write this question. Generally speaking, if you have a specific subject matter you want to test, there are two fundamental ways the question can be written:

1. The subject matter is in the question, or
2. The subject matter is in the answers.

Here's an example. You could write the question like this:

_What is the following code going to output?_

```js
class Model {}
class User extends Model {}
const dave = new User()
console.log(dave instanceof Model, dave instanceof User)
```

1. `true, true`
2. `false, true`
3. `true, false`
4. It will get an error

This is an example of the subject matter (`instanceof`) being in the question. By contrast, we could have tested for the same subject matter by flipping things around and having the question be more ambiguous and the subject matter be in the answers:

_Assuming you have a `myUser` variable and you need to ensure that it is an instance of a `User` object, which of these is the best choice?_

1. _`myUser instanceof User`_
2. _`typeof myUser === 'Object' && myUser.is(User)`_
3. _`myUser.type === User`_
4. _`typeof myUser === User`_

The first way, with the subject matter in the question, it alerts the test taker that `instanceof` exists and we're asking them to figure out some nuances about how it works. The second way, with it in the answers, the user doesn't know that `instanceof` necessarily exists, they just know that a problem exists and they have to choose `instanceof` as the correct solution.

Neither way is inherently better than the other. Just keep this tip in mind when you're thinking about how to write questions.
