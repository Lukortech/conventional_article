# Why so conventional? 

![alt text][whySoConventional]

## The reason behind the need to commit work in a better way

Imagine you're at a starting point in a company you just got hired by. 
All the people are nice to you and everything seems fine up until the point when you're introduced to a codebase from before js was a language and netscape was loading a page for what would seem an age.

The inheritance of code seems to be a massive issue when introducing new developers to a project and reading the code is one thing, but understanding how the application was developed is not quite the same. Oftentimes commits prove to be useful and give context to why these `console.logs` weren't caught by linter.

Let's start with why conventional commits are better if executed in a project than not standarized commit rules. 

If we hire new developers to a project in which most commits consist of messages along the lines of `that should work` or `Sleepy fix for footer ASAP` what pops up in your head? 

I'd say that red flags because:

- we don't know what exactly should work
- why did someone pushed something whilst being sleepy and potentially with errors
- was the fix rushed if there's ASAP annotation

Why conventional commits help you deal with that kind of problems? It's because you can have custom rules applied to when you commit your changes and not mentioning what the fix is about will automatically result in an error and information to name the commit in a better manner.
There's chance you'd be willing to setup a rule that doesn't allow for certain keywords so let's say `ASAP` is a no-go word. 

## Tooling

What is really helpful at the start of the project is to introduce everyone to how your dev team would like to see new devs to commit their changes and setup a tool that helps them to keep up with current rulesets. 
One of the tools I've had a chance to work with was [commitlint](https://commitlint.js.org/) and it made conventional commits my go-to practice when comming to new projects that don't have rules and the team is open to introduce them.

When dealing with the settings and spreading them across your team you can just simply create an npm package and just `mpn i -D` it in each project. That will surely help your developers to be on the same page at all times and if need be walk from project to project understanding what were the last changes about. 

## Friends with multiple benefits

So now after setting it all up and understanding why it might be a good idea to start using [CC](conventional_commits) the best part would be programming around the rules you've just applied! We are using standarized way of how we commit, we pay more attentionto what the commit really was about so why not set up hooks that allow you for quicktesting on staging when a flag is present? We don't want to overcumber services and cut the costs when needed and there are some reasons to test on production-like server instead of localhost. 

Let's assume you're working on PWA and SSL is needed for you to test out the full potential and you have an SSL on your testing platform. All you need now is just a good commit. Something along the lines of `feat(PWA): manifest icons workbox setup upload` would trigger whole machinery of testing and moving cogwheels around. We don't need that when just uploading some static data like `manifest.json` so we add a flag `[TEST_SKIP]` as a postfix to our commit. That enables our CI to just upload new assets to the testing environment and skip testing


```
----------------------------------WiP-------------------------------------
After getting the ground rules set up you can get full advantage of [CC](conventional_commits) and try hooking up your CI to what the commit says. 
--------------------------------------------------------------------------
```

[whySoConventional]: /whysoconventional.png "Why so conventional joker heading"