# Style Guide

## Table of Contents

- [Google developer documentation style guide](#google-developer-documentation-style-guide)
- [Terminology](#terminology)
- [Types of repositories](#types-of-repositories)
- [File structures](#file-structures)
- [Resource templates](#resource-templates)
- [Formatting](#formatting)
- [JavaScript formatting](#javascript-formatting)

## Google developer documentation style guide

In general, Pursuit curriculum should follow the rules set out in [Google's developer documentation style guide](https://developers.google.com/style). If you are writing curriculum for Pursuit, please take the time to read through this documentation.

The style requirements detailed below either explicitly call out the rules set by the Google style guide or are rules particular to our curriculum. When in doubt, refer back to the Google style guide.

## Terminology

For more information about relevant terminology, see the [Terminology document](./terminology.md).

## Types of repositories

The following describes what types of repositories should generally appear within this organization.

### Units

Each unit will have its own repository. This repository name should refer to the content in the unit, not a specific number or order, and should be prefixed with the word `unit`.

For example, the following is an acceptable name for the Full Stack unit.

```
unit-full-stack
```

These repositories should be set to _Private_.

### Starters

Code that should be used as a starting point for a reading, classroom activity, or project should be its own separate repository. Each starter repository should be prefixed with the word `starter` and be described as generically as possible. Assume that starters could be used for multiple projects.

For example, the following is an acceptable name for starter code that includes a basic Express server.

```
starter-express-server
```

These repositories should be set to _Private_.

### Labs

Each lab should be its own repository. The name of the lab should match the name of the lesson folder that it is associated with. Each lab repository should also be prefixed with the word `lab`.

For example, the lab for the lesson with a folder name of `higher-order-functions` should be as follows.

```
lab-higher-order-function
```

## File structures

### Unit and lessons

Each unit repository should be designed to utilize the [Jekyll](https://jekyllrb.com/) framework.

Each lesson should be within a `_lessons` folder. Each lesson folder should have a name that matches the lesson title. Every word in the title should be included within the folder name with the following exceptions:

- `introduction` can be shortened to `intro`.
- Articles and other very short words such as _and_, _of_, and _the_ may be removed.

The following are examples of acceptable folder names.

- _Seeds and migrations_ could become either `seeds-and-migrations` or `seeds-migrations`.
- _Introduction to Express_ could become either `intro-to-express` or `intro-express`.

Each lesson folder should have the following files within each.

```
./_lessons/lesson-name/.
├── assignments.md
├── guiding-questions.md
├── instructor-guide.md
├── learning-objectives.md
└── reading.md
```

### Full-stack projects

Full-stack projects should include both a `back-end/` and `front-end/` directory. Both of these folders should be able to run their respective parts of the application on their own. Additionally, commands should be set up in the root folder so that the project can run completely.

## Resource templates

Templates for specific resources can be found in the [Templates](./templates/) directory. Each template will describe how to use itself.

## Formatting

### Titles

The first title of a page, represented by an `h1` heading, should use title casing. Every heading afterwards should use sentence casing. 

### Emphasis

If you need to add emphasis to a sentence, use italics only -- not bold.

```md
Every request that comes in will first go through these lines of code _unless_ an error occurs or the server sends a response.
```

### Technical packages and services

Whenever referring to a technical package, such as [Express](https://expressjs.com/), use the name as described on the official page for the package. Do not use any particular abbreviation unless that abbreviation is explicitly referenced on the main page.

For example:

- JavaScript as opposed to JS.
- PostgreSQL as opposed to PSQL.

Only use the package name in backticks if referring explicitly to code or to a related tool. For example:

- Nodemon instead of `nodemon`, unless you are asking students to run `nodemon node.js`.
- Knex.js instead of `knex`, unless you are asking students to run the `knex` command-line tool.

### Tips or notices

If you want to add a helpful hint, keep it short and use a block quote.

```md
> **Tip:** If you do not notice any change, try restarting your server.
```

The same format should be used for other types of notices.

```md
> **Note:** If you forget to use the `return` keyword, nothing will happen when you run `npm start`. 
```

### Inline Code

If you ever reference syntax or a file, use the back ticks to identify that this is code.

```
To use Nodemon, create a script. Add the following script to your `"scripts"` object in your `package.json` file.
```

If you are referring to a function, include the `()` symbols when discussing it.

```
Try changing the text in your `listener()` function in your `server.js` file. You should see the new message almost immediately show up in your terminal.
```

### Code blocks

If you're writing a block of code, make sure to use proper formatting techniques. After the three back ticks, type the word JavaScript.

```md
    ```javascript
    console.log(some message);
    const h1 = document.querySelector('h1');
    h1.innerText = "Hello, world!";
    ```
```

This will result in the following.

```javascript
console.log(some message);
const h1 = document.querySelector('h1');
h1.innerText = "Hello, world!";
```

If you need to label the block of code as if it were in a file, add a comment at the very top with the file name.

```javascript
// main.js
console.log(some message);
const h1 = document.querySelector('h1');
h1.innerText = "Hello, world!";
```

### Keyboard shortcuts

When referring to specific keys, use the `kbd` element.

```
<kbd>Command</kbd>+<kbd>C</kbd>
```

### Reference Links

If we are linking to a part of an external website, put the name of the website, followed by a colon, and then the title of the website.

```md
- [MDN: Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
```

## JavaScript formatting

In general, follow good conventions and the PrettierJS formatting.

- [PrettierJS](https://prettier.io/)

In general, this means the following:

- Include semicolons
- Use `const` wherever possible
- Use arrow functions instead of function declarations
- Use double quotations (e.g. `"my text"`)

You can run PrettierJS on your files before committing by running the following command from your local machine.

```
npx prettier --write library/<your-folder>/*
```

Replace `<your-folder>` with the folder you are working on.
