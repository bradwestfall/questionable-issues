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

A knowledge unit question is meant to test a specific piece of knowledge. As you review your Subject Lists, you might have a subject called "Objects" and perhaps you want to assess whether the test taker knows how to use `instanceof`. Then, "Does the test taker know how to use `instanceOf`?" becomes your knowledge unit.

Now let's consider the two main ways that a knowledge unit question is usually written:

1. The knowledge unit is in the question, **or**
2. The knowledge unit is in the answers.

Here's what a question might look like with the knowledge unit in the question:

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

By contrast, we could have tested for the same knowledge unit by flipping things around and having the question be more ambiguous and the knowledge unit be among the answers:

_Assuming you have a `dave` variable and you need to ensure that it is an instance of a `User` object, which of these is the best choice?_

1. _`dave instanceof User`_
2. _`typeof dave === 'Object' && dave.is(User)`_
3. _`dave.type === User`_
4. _`typeof dave === User`_

Having the knowledge unit be apart of the question typically alerts to them that the knowledge unit exists and we need to see if they know how it works. If the user didn't know that `instanceof` existed before, they do now. The answer options are then trying to determine if the user knows "how it works".

With the knowledge unit as apart of the answers, the question becomes more about _solving some problem_ and they have to now figure out which options solves that problem.

#### How are they different?

Neither way is inherently better, but each of these ways has "characteristics" you should be aware of.

Consider that often times the first approach leads to more code -- which means that you'll probably be introducing other concepts besides the knowledge unit that the test taker must know in order to fully understand the question. In this example, we uses classes and inheritance -- which is there for context.

As a general rule, it might be best to limit the context code to be as simple or more simple than the knowledge unit itself. From a reporting standpoint, imagine if the test taker is getting this question wrong but it's not because they didn't understand `instanceof`, it's because they didn't understand something in context code.

A characteristic of the second way of writing questions (with the knowledge unit in the answers) is that you'll have to make up "fake things" sometimes. In other words, if you have a correct option like `dave instanceof User`, you'll need some distractor options that seem like they _could_ be correct but aren't quite correct. For example, JavaScript has no `.is` method built into objects to have `dave.is(User)` as a possibility, but it seems plausible to a beginner that this could be the right answer.


### Comprehensive Questions

Sometimes we end up with too much context code in our knowledge unit questions, or we simply want to test the user on a variety of things at once. For these situations, we call these questions comprehensive and we need to be tagged `Comprehesive`.


## Quality Guidelines

- [Prefer Concepts over Terminology](#prefer-concepts-over-terminology)
- [Avoid Process-of-Elimination](#avoid-process-of-elimination)
- [Avoid Trick Questions](#avoid-trick-questions)
- [Use The "Common" Way](#use-the-common-way)
- [Patterns and Architecture](#patterns-and-architecture)

#### Prefer Concepts over Terminology

One of the things that makes Questionable a great tool is its code-enabled questions. This uniquely means that we can test for coding concepts over coding jargon. Keep in mind that many talented coders might know how a concept works but not necessarily the correct terminology for that concept. Questions are higher quality when they assess someone's real coding knowledge instead of their knowledge of the correct terms. On Questionable, we want to limit the number of terminology questions to under 10% per test. Please also tag them with `Terminology`.

We do think you should be creative though in assessing whether or not the test taker knows a term without ever having to mention that term. For example, in JavaScript if we want to assess whether someone knows what "closure" is, we can do so without ever mentioning the term closure in the question or the answers. Here's an example question that does just that:

_What will the `console.log()` produce with this code example?_

```js
function addFive() {
  const five = 5
  const adder = n => {
    return n + five
  }
  return adder
}
const myAdder = addFive()
console.log(myAdder(4))
```

In order to get the correct answer, one would have to know how closures work -- even though they might not know what closures are. This is a perfect example of testing someone through concept instead of terminology. And also, this question could be tagged for `Closures` since it's the knowledge unit.

There is a gray area. Sometimes you'll have to use terms to explain your question. Just consider the audience and the complexity of the term. If it's a Beginner JavaScript test, they might not know what an arrow function's implicit return is. For a beginner test (if you think that's a beginner topic) it might be test to test the concept without mentioning the term like we did with closure. But for an Advanced JavaScript test, we can probably assume the test taker knows the basic terms -- just don't write "SAT" style questions like "What is the definition of...". Prefer code questions.


#### Avoid Process-of-Elimination

We've all taken tests where we were able to figure out the correct answer because of poorly conceived distractor options. If a test taker can do well on your test because they're good at eliminating the distractor options, then it's not a very good test. Keep in mind that writing good distractor options is sometimes the difference between a really good question and an average one.

One idea might be to have a coder friend take the test -- someone who does code but not necessarily in the language that you write the test for. They should do very poorly if they don't know the language. Ask them to identify which questions were easier to guess at.


#### Avoid Trick Questions

Sometimes it can seem like a thin line between "Avoid Process-of-Elimination" and yet "Avoid Trick Questions". To help with this, just try to write basic strait forward questions with one distinctly correct answer and several distinctly incorrect ones.

For the `instanceof` question we used in previous examples, there were four options to choose from:

1. _`dave instanceof User`_
2. _`typeof dave === 'Object' && dave.is(User)`_
3. _`dave.type === User`_
4. _`typeof dave === User`_

Sometimes you'll have to get creative in writing the distractor answers because you'll have to "make up" coding concepts that don't exist. In this case, I made up `dave.is()` and `dave.type` which don't exist in JavaScript. The fourth answer uses `typeof` which does exist but is used completely incorrectly. There is only one answer which could possibly be correct which is #1.

Sometimes having the "made up" answers that seem plausible is the best way to ensure that one of your distractor answers can't be construed as the correct answer, and therefore becoming an unintentional trick question.


#### Use The "Common" Way

Sometimes languages provide a lot of freedom when writing code with various styles. Just try to be cognizant that _your_ preferred way of writing code might not be the common way of writing it, and try to prefer the common way for the questions.


#### Patterns and Architecture

Try to avoid testing on specific patterns or architectural decisions which can be viewed as highly subjective or opinionated and presenting them as fact. For example, if there is a pattern that you'd like to ask about, it might not be wise to phrase the question to suggest the pattern is "better than" or "worse than" other options -- especially if these concepts are at all debated in the respective field. An example might be the BEM pattern in CSS. It would not be okay to ask "Which of the following patterns is best suited for this situation". It would be okay though to ask "In the BEM naming pattern, what is a 'modifier' -- the M in BEM". This is much less subjective and has basis in fact.
