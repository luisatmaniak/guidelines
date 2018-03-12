# Global Development Guidelines

## Goals

* Follow established best practices
* Leave the house cleaner than when you found it
* Work concurrently with multiple devs on the same codebase at the same time in the same way
* Produce code that is less prone to bugs and regressions

## Contributing

This should be considered a living document, open a pull request if you feel like it.

## Performance

Page load times (both real and perceived) are a key consideration for users of all browsers and device types.

There are some general things we can do in front-end development:

- Send fewest bytes possible down the wire

- Avoid unnecessary use of `display: none;`

- Keep CSS selectors concise (be wary of SASS nesting)

- Minimise HTTP requests

- Minimise blocking – content should be readable before client-side processing

- Lazy load 'supplementary' content (especially images)

- For an in-depth guide on the topic, see [PageSpeed Insights Rules](https://developers.google.com/speed/docs/insights/rules)

## Testing and QA should find no problems

- Code is a craft - make it your responsibility to ensure it is the best it can be; that it's tested, bug-free, and adheres to these guidelines. Testing and QA folks aren't responsible for quality - developers are.

- Don't use testers as bug catchers - testers should find no problems after you have committed your code.  When testers find bugs, tickets need to be opened, developers assigned and scheduled in to fix the problem.  This lengthens the time it takes from identifying to resolving a bug.

- Make sure, as much as possible, you have tested your code on a reasonable number of devices so you can catch problems before you commit to the repo.

## You are producing source code

Most projects undertaken by Maniak have some sort of build system, some considerations need to be taken because of this:

- Don't check generated files into the repo, e.g. CSS files when using SASS (unless the project maintainers say so)

- Don't check dependencies in the repo (e.g. node_modules shall be ignored)

- When including CSS and JS reference the non-minified versions

## Don't Repeat Yourself (DRY)

If you repeat anything that has already been defined in code a couple times, refactor it so that it has less representation in the codebase.

If you stick to this principle, you will ensure that you need to change fewer implementations of a feature without worrying about needing to change any other part of the code.


## Separation of concerns

Separate *concerns* not *technologies* (but only if you know what you are doing).

- Keep components (i.e. logical units of CSS/HTML/JS) co-located in the file system

- Avoid writing inline CSS or Javascript in HTML

- Avoid HTML in Javascript

- Don't choose HTML elements to imply style

- Prefer using CSS rather than Javascript for animations and transitions

## Write code to be read

> Debugging is twice as hard as writing the code in the first place.  Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it. - Brian Kernighan.

Follow the principles of ['Keep It Simple, Stupid'](http://en.wikipedia.org/wiki/KISS_principle) (KISS); hard to read or obfuscated code is difficult to maintain and debug.  Don't be too clever; write code to be read.

## Commenting

Explain design or architectural decisions that cannot be conveyed in code alone by adding comments to your code.

Be sure that in conjunction with writing code that adheres to these guidelines, someone can pick up your code and immediately understand it.

Be verbose with your comments but ensure:

- Your comments add something to the code, they don't just repeat what is there

- They are kept up to date, if you change something that has been commented, ensure you update the comment as well

- If code needs extensive commenting, can it be refactored to make it less complex / easier to understand?

- You focus on *why* rather than *how* - unless your code is too complex, it should be self-documenting

Don't leave commented out chunks of code in the codebase. It makes the code look unfinished, and can be confusing for other developers.

## File naming

- Don't use whitespaces in file names - they can lead to problems including text escaping and are harder to read when encoded in URLs

- Use hyphens for word separators

## Identify technical debt

Use code comment annotations to mark parts of your code that require further work. This will allow the measurement and management of technical debt.

Tag | Use
---: | --- | ---
`// TODO` |  document tasks to be completed
`// FIXME` | rises a problem in the codebase for everyone to notice
