# Question Authoring Guidelines

The following is a list of guidelines which we ask all Questionable Marketplace Authors to follow while writing test and question content. These guidelines are meant to keep question writing more consistent among authors and to keep the quality of question writing at a high level.

For the purposes of this guide, all examples will be demonstrated in the Web languages: HTML, CSS, and JavaScript.

## Terms

- **Marketplace Author:** The person writing tests for the purpose of publishing them into the Marketplace for sale (presumably you).
- **Test Admin:** Anyone who has a Questionable account and has tests to send to test takers. In a sense, the Marketplace Author is technically the Test Admin of their tests for their account, but for the purpose of this document, the person buying your test to administer it to others is also the Test Admin (of the copy of the test they bought) when the test is copied to their account.
- **Test Taker:** The end-user taking the test with the oversight of the Test Admin.
- **Distractor Options:** This is an academic term for "the wrong answers" in a multiple choice question.
- **Difficulty Level:** All questions are marked for their difficulty on a 1-3 scale. Strategies for choosing difficulty are listed later in this document.

## Tags

When someone buys a test, and subsequently its questions from the marketplace, each question's tags will also be copied down to their account. The tags that they get from your questions will be mixed with all the tags they have written themselves, and with tags they received prior from purchasing other tests. For this reason, there needs to be a high degree of consistency when it comes to writing tags for the marketplace.

From a reporting and statistical standpoint, tags are grouped by unique Tag Name, not by some sort of internal `tagId`. This means that your tags will easily blend into someone else's account as long as the tags are the same.

Reports like the Gap Analysis Report which allow Test Admin to analyze data on a tag-basis are attractive features for Questionable so this is why it is very important that **all questions** be tagged with at least one tag, but more are preferred (2-4 can be considered an average).

Unless there's a good reason to do otherwise, tags should be written with title casing (with the first letter of each word capitalized), such as `Arrow Functions`, not `arrow functions`. Common acronyms like `HTML` can be written in all-caps.

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

Each question will have a difficulty set as a number between 1 and 3 (where 1 is for easier questions and 3 is for more difficult questions). Since this is somewhat subjective, the granularity is low with only three levels. The test's overall difficulty will be derived from its questions as an average for the purpose of displaying on the Marketplace and so Test Author's know that their "Beginner ... Test" is in fact more "beginner".

However, not every question's difficulty level must perfectly match the test's difficulty. The average of a beginner test just needs to be closer to 1 whereas the average of a more advanced test should be closer to 3.

## Before you Start

### 1. Difficulty

Before anything, you need to know what difficulty level you're aiming for with the overall test. This way you can try to ensure your question brainstorming process and choosing Subject Lists (next section) are inline with the purpose of the test.

### 2. Make a "Subjects List"

The purpose of the subjects list is to brainstorm and mentally prepare for the types of questions you're going to write. Don't underestimate this step. Based on the difficulty you're writing for in Step 1, this list will help you stay focused on what questions to write for.

If the test is "Beginner JavaScript", your subject list might be:
- Basic Arrays and Objects
- Loops and Conditionals
- Data Types
- _etc..._

If the test is more advanced, you can probably imagine the subjects are more advanced.


## Start Writing Questions

Once you have your Subject Lists and Difficulty determined, it's time to start writing questions. This next section will help you break down how questions are written and what types of questions are good at testing for different types of knowledge.

- Knowledge Unit Questions
- Comprehensive Questions

Now that you have your Subject Lists, start writing a few questions in each subject. Perhaps one of your subjects is "Objects" and you want to write a question to see if the test taker knows how to use `instanceof`. Making a question that specifically tests `instanceof` makes what's called a knowledge unit.

### "Knowledge Unit" Questions
<hr />

A Knowledge Unit question is meant to test a specific piece of knowledge. As you review your Subject Lists, you might have a subject called "Objects" and perhaps you want to assess whether the test taker knows how to use `instanceof`. Then "Does the test taker know how to use `instanceOf`?" is your Knowledge Unit.

Now let's consider the two main ways that a knowledge unit question is usually written:

1. The knowledge unit is in the question, **or**
2. The knowledge unit is in the answers.

As an example, you could write the question like this:

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

This is an example of the knowledge unit (`instanceof`) apart of the question. By contrast, we could have tested for the same knowledge unit by flipping things around and having the question be more ambiguous and the knowledge unit be among the answers:

_Assuming you have a `dave` variable and you need to ensure that it is an instance of a `User` object, which of these is the best choice?_

1. _`dave instanceof User`_
2. _`typeof dave === 'Object' && dave.is(User)`_
3. _`dave.type === User`_
4. _`typeof dave === User`_

Having the knowledge unit be apart of the question typically alerts to them that the _something_ exists and we need to see if they know how it works. If the user didn't know that `instanceof` existed before, they do now. The answer options are then trying to determine if the user knows "how it works".

With the knowledge unit as apart of the answers, the question becomes more about _solving some problem_ and they have to now figure out which options solves that problem.

#### How are they different?

Neither way is inherently better, but each of these ways has "characteristics" you should be aware of.

Consider that often times the first approach leads to a slightly more complex chunk of code -- which means that you'll probably be introducing other concepts besides the knowledge unit that the test taker must know in order to fully understand the question. In this example, we uses classes and inheritance -- which is there for context.

As a general rule, it might be best to limit the context code and to ensure that it's complexity doesn't exceed the complexity of the knowledge unit itself. From a reporting standpoint, imagine if the test taker is getting this question wrong but it's not because they didn't understand `instanceof`, it's because they didn't understand something something in context code. This question might be tagged for `Data Types` and the reporting might indicate the user didn't get some of the `Data Types` questions correct -- but the reality might be that they just didn't understand classes and inheritance as much.

Having "context code" is often times unavoidable when writing code questions, just try to be mindful of what the question is trying to accomplish. If you do want a comprehensive question, that's totally okay (and encouraged to have some), just be mindful that it is a comprehensive question, it's probably not beginner level, and we need to tag these questions as `Comprehesive`.

A characteristic of the second way of writing questions (with the knowledge unit in the answers) is that you'll have to make up "fake things" sometimes. In other words, if we have a correct option like `dave instanceof User`, we'll need some distractor options that seem like they _could_ be correct but aren't quite correct. For example, JavaScript has no `.is` method built into objects to have `dave.is(User)` as a possibility, but it seems plausable to a beginner that this could be the right answer.

### Comprehensive Questions

...

