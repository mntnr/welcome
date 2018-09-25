---
title = "OSS Maintenance as a Service: Helping maintainers maintain their code"
date ="April 11, 2017"
---

Open source code is awesome, glorious, and lots of fun. We're told again and again in hackathons, meetups, coffee chats, [NodeSchools](https://nodeschool.io), Hacker News posts, and Twitter threads that we should all contribute to open source, as much as we can. So, we start a GitHub account. We begin putting code on it. [We code every day](https://medium.com/@richlitt/100-days-of-code-5e9a4dc6d56b). We work on projects on the weekends, over lunch, when our partners are in bed. 

And we're also told that burn out is totally normal, that it happens to everyone. That you should take breaks. That maintaining a project is hard work. 
But what happens when your project gets 1000 stars? When you start having issues every day? When you're tasked with maintaining an open source codebase from someone who left your company?

In one of the best articles describing the situation, [Nolan Lawson](https://twitter.com/nolanlawson) wrote in "[What it feels like to be an open-source maintainer](https://medium.com/r/?url=https%3A%2F%2Fnolanlawson.com%2F2017%2F03%2F05%2Fwhat-it-feels-like-to-be-an-open-source-maintainer%2F)”:

> [Issue templates](https://medium.com/r/?url=https%3A%2F%2Fgithub.com%2Fblog%2F2111-issue-and-pull-request-templates), [GreenKeeper](https://medium.com/r/?url=https%3A%2F%2Fgreenkeeper.io%2F), [Travis](https://medium.com/r/?url=https%3A%2F%2Ftravis-ci.org%2F), [travis_retry](https://medium.com/r/?url=https%3A%2F%2Fdocs.travis-ci.com%2Fuser%2Fcommon-build-problems%2F%23travis_retry), [Coveralls](https://medium.com/r/?url=http%3A%2F%2Fcoveralls.io%2F), [Sauce Labs](https://medium.com/r/?url=http%3A%2F%2Fsaucelabs.com%2F)… there are so many technical solutions to the problems of open-source maintenance, and I’m grateful to all of them. There’s no way I’d be able to keep my head on straight if I didn’t have these automated tools. But at some point you run up against issues that are more social problems than technical problems. One human being just doesn’t scale. I’m not even in the [top 100 npm maintainers](https://medium.com/r/?url=https%3A%2F%2Fgist.github.com%2Fbcoe%2Fdcc961b869bbf6685002) and I’m already feeling the squeeze; I can’t imagine how those hundred people must feel.
> …
> If there’s one thing I’ve learned in open source, it’s this: the more work you do, the more work gets asked of you. There is no solution to that problem that I’m aware of.

There's a disconnect between the messaging, here. They don't tell you this at the beginning: **Open Source is hard**. 

---

I'm aware of this problem, too. I am nowhere near the top 100 npm maintainers. But I have too many issues on GitHub to ever resolve. I maintain several repos with thousands of stars — [lukasz-madon/awesome-remote-job](https://medium.com/r/?url=https%3A%2F%2Fgithub.com%2Flukasz-madon%2Fawesome-remote-job), [k88hudson/git-flight-rules](https://github.com/k88hudson/git-flight-rules), [btford/write-good](https://github.com/btford/write-good). I also have my own repos, some of which are popular themselves: [awesome-conferences](https://github.com/RichardLitt/awesome-conferences), [standard-readme](https://github.com/RichardLitt/standard-readme), [endangered-languages](https://github.com/RichardLitt/endangered-languages).

This past year, I was the community manager and generic dev for [IPFS](https://ipfs.io). [IPFS](https://github.com/ipfs) has hundreds of repos, if you take into account the ipfs, [multiformats](https://github.com/multiformats), [libp2p](https://github.com/), [orbitdb](https://github.com/orbitdb), and [ipld](https://github.com/ipld) organizations. That meant as well as my own 600~ GitHub repositories, I had hundreds of others to maintain. This meant triaging issues, standardizing READMEs to look good, checking that links didn't break, adding labels, improving user flow across the organization, merging small PRs to the documentation. 

So, I started figuring out ways to automate what I was doing. I made [name-your-contributors](https://github.com/RichardLitt/name-your-contributors) to start praising people who comment in pull requests, review code, and open issues just as much as those whose commits get merged. I created the [Standard Readme specification](https://github.com/RichardLitt/standard-readme) to make it easier to write and edit hundreds of READMEs. I also made [a generator](https://github.com/RichardLitt/generator-standard-readme) and [a linter](https://github.com/RichardLitt/standard-readme-linter-regex) for it. I talked about it in [Boston, Washington, and Tokyo](https://github.com/RichardLitt/talks). I worked on [project-repos](https://github.com/ipfs/project-repos) as a dashboard to judge the documentation health of an organization overall. By the end, it was pretty easy for me to come in and make a GitHub repository look good, or to set up an organization to start getting regularly contributing users.

Looking at GitHub organizations and projects, it's easy to see that not everyone has done this work. There are many GitHub repos with no READMEs, at all — or no LICENSE files, or CONTRIBUTING.md, or issue or pull request templates. Many repositories are out of date, and won't be updated any time soon, but the issues pile up. And a lot of maintainers have issues finding other maintainers to help them out. For companies, this was especially rife — often, a company has many open source projects, but half of them aren't actively maintained because the team has moved on. This doesn't look good for the company, at all. Sure, they've open sourced material, but it's dead in the water. 

I figured I could help.


---

Today, I'm launching [Maintainer.io](https://maintainer.io). It is aimed at both single developers working on their popular pet projects, and organizations with many projects to maintain.

We offer two main services. First, we can do [one-off audits of repositories or organizations](https://plasso.com/s/KHnLKOSeK1). We have an internal checklist that we'll run through — is the README standardized, is there a Contributing doc, a License, and so on. We'll check if these are all internally coherent. We will take a look at the issues, labels used, and suggest an issue and pull request template. We'll suggest labels for the repository itself, as well as linking to the GitHub Pages website — if there isn't one, wecan make one of those. Anyone can do these things — but a lot of people don't have time to research best practices, and we're happy to help out here. 

For organizations, we check that the flow of information is good across repositories, that there is a question repository or a support email linked, that deprecated repositories are marked as deprecated. If there are any errors, we can pull request most of them. All of this without needing security authorization or push access to the repo.

[Our other service is a retainer](https://plasso.com/s/RMPMGYmBER). We'll do the audit above, but also stick around to help out with actively maintaining the repository. We don't need push access here, either; we won't be merging PRs (unless you want us to merge doc fixes, which we could do). Instead, we'd help with triaging and sorting issues, with updating your issue templates, and with providing human responses to people who may have questions or who may be angry with the maintainer because of a bug (it happens). This should save some developers hours of work — by not having to worry about responding in a timely fashion to users asking questions, they can get some sleep, and deal with issues later when they're ready. 

Maintainers don't normally want to say: "Thanks for opening this issue. This is an open source project — take a look at the documentation here, here, and here, and your question may be answered. We'll get to you when we have time." But we can do that. Maintainers may not also want to say: "I'm on vacation for three weeks, hiking in the Alps." But we can do that, just saying "We'll get to this in X time, based on our current timeline." 


---

We think that providing a simple service like this could be extremely helpful. First off, building an open source community is hard work. I know; I've done it. It takes a lot of time to make sure that the documentation looks good, and it's hard to internally vet your own docs when you've been living with them for years. By bringing in helpers, you can get a second set of eyes on your code, and on your onboarding process. By having better onboarded contributors, you're less likely to get less-than-great pull requests, or issues which don't make sense. This saves time, again. For developers, that time could be better spent enjoying life, taking time off, sleeping. 

For organizations, this extra could be better spent elsewhere, building the code needed for the company, instead of having every dev be a community manager. As well, new users who know the product better are much more likely to stay on as contributors. These contributors become an excellent talent pool to hire from. Why spend money on recruiters, when a well-managed community would lead to developers who know your product, work on your code, and talk to your team already?

Will this solve everything? No. But we're not aiming to do that. We're aiming to take two hours off of a busy developer's week; to save ten hours for a team of five developers working at a medium size company. 

If you're interested in that, send us a line: [info@maintainer.io](mailto:info@maintainer.io). We're listening. 

And, of course, PRs accepted.
