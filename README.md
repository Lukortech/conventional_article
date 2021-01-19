# Why so conventional? 

![alt text][whySoConventional]

## The reason behind the need to commit work in a better way

Imagine you're at a starting point in a company you just got hired by. 
All the people are nice to you and everything seems fine up until the point when you're introduced to a codebase from before JavaScript was a language and Netscape was loading a page for what would seem like an age.

The inheritance of code seems to be a massive issue when introducing new developers to a project. Reading the code is one thing, but understanding how the application was developed is not quite the same. Oftentimes commits prove to be useful and give context to why these `console.logs` weren't caught by linter or why that nasty `// TODO` is there for children fo the developer that initially made the annotation.

Let's start with why conventional commits are better than unstandardized commit rules. 

If we hire new developers to a project in which most commits consist of messages along the lines of `that should work` or `Sleepy fix for footer ASAP` what pops up in your head? 

I'd say that red flags because:

- we don't know what exactly should work
- why did someone pushed something whilst being sleepy and potentially  erroneous
- was the fix rushed if we can see `ASAP` annotation?

Because your team can have custom rules applied to when one commits changes there's less room for error as your commit needs to be solid. It's no longer a way to just check-out. It's a signature that tells other people that you knew the contents of the commit. No need to mention that if the work you've done is not correctly signed it will most likely result in an error and prompt you with a message 

There's chance your team would like to setup a rule disallowing for certain keywords so `ASAP` or any swear words can be on the blacklist. 

## Tooling

What is really helpful at the start of the project is to introduce everyone to how your dev team would like to see new developers to commit their changes. Then setup a tool that helps them to keep up with what you all agreed on. 

One of the tools I've had a chance to work with was [commitlint](https://commitlint.js.org/) and it made conventional commits my go-to practice when comming to new projects that don't have rules and the team is open to the idea of introducing them.

When dealing with the settings and spreading them across your team you can just simply create an npm package and just `mpn i -D` it in each project. That will surely help everyone in the project to be on the same page at all times and if need be walk from project to project understanding what were the last changes about (and why were they made). 

## Friends with multiple benefits

So now after setting it all up and understanding why it might be a good idea to start using [CC](conventional_commits) the best part would be programming around the rules you've just applied! We are using standarized way of how we commit, we pay more attentionto what the commit really was about so why not set up hooks that allow you for quicktesting on staging when a flag is present? We don't want to overcumber services and cut the costs when needed and there are some reasons to test on production-like server instead of localhost. 

Let's assume you're working on PWA and SSL is needed for you to test out the full potential and you have an SSL on your testing platform. All you need now is just a good commit. Something along the lines of `feat(PWA): manifest icons workbox setup upload` would trigger whole machinery of testing and moving cogwheels around. We don't need that when just uploading some static data like `manifest.json` so we add a flag `[TEST_SKIP]` as a postfix to our commit. That enables our CI to just upload new assets to the testing environment and skip testing. You can read more on that [here](https://github.com/conventional-changelog/releaser-tools/tree/master/packages/conventional-github-releaser) 

After a while you'll be able to see other profits, such as ease of generating CHANGELOG and better versioning with [semantic versioning](https://semver.org/).
If that's not enough to convince you to change your ways of writing commit messages maybe getting your toes dipped into fresh cold water and trying to use them in your private repository for a while would change your mind. 

Happy conventional committing!

[whySoConventional]: /whysoconventional.png "Why so conventional joker heading"