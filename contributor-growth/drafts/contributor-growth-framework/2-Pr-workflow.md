# 2. A successful PR workflow  

The PR workflow is at the core of code contributions. Make sure it's a smooth experience and try to get contributors to contribute something else once they've succeeded. 

Here's a typical PR workflow: 
   1. User opens an issue (bug, feature request, vulnerability)  
As maintainers, you will first troubleshoot the bug or review the feature request. Reach out to the submitter to thank them for the issue and assess if they want to be involved. If they are, ask them to continue the conversation on your contributor channel. 

   2. Pick conversation up on contributor channel  
Smaller projects should assign new contributors to a mentor or point of contact who can follow up making sure they remain motivated and follow through. [Community CRMs such as Orbit](https://orbit.love/) will help you keep track of contributor activity. If you don't see any activity from your prospective contributor, check-in to see if they are still interested. A gentle reminder may revive their motivation and show them you really care about their contribution. 

   3. Submit one PR 
Once they submitted their PR, suggest another contribution or, if they have been contributing for a while, ask them if they'd like to take the next step and move up the contributor ladder.  

This is really key. If you want people to engage more or take on more responsibility, you have to encourage them to do so. It's a little bit like a career coach (don't forget to take notes in your community CRM about their preferences, time restrictions, etc. Having that info at hand will prove useful during future conversations). While guiding people is a lot of work and you may think you don't have time to do so, it will save you a lot of time down the line. 

## Manage Expectations 

Contributors, especially seasoned ones, can get really impatient after submitting their PR. Generally, you should try to turn around reviews quickly, especially if it's their first issue. But volume can be an issue. So, if it will take some time, setting clear expectations will help avoid frustrations on both sides.   

What should you communicate prior to a PR:  

  ***Average response time***, especially for small teams that don't have the bandwidth to respond quickly. When wait time is particularly long, explain why. Don't wait for them to make assumptions about why things aren't moving forward. Also remind them that open source work is often done during free time outside of regular working hours.  

  ***Clearly describe flow and action items***, whether a design doc or follow-up questions are part of the submission process, set the expectations for what all the steps are and how long it will take.  

What should you communicate after opening a PR:  
   
   ***Expectation about code and documentation quality***. To avoid unnecessary back and forth dialog as well as lengthy discussions, leverage automated PR checks. This will help you avoid a lot of headaches and also declaratively defines expectations for PRs.  

   ***Capture PR follow-up ideas***. During the process, you may identify something that isn't necessarily related to the current PR. Add a comment, like "I see you hardcoded this here and would love to see it configurable by environment variables. Could you submit an issue so we remember to work on it and merge it with this PR?" This is also a great way of building trust and goodwill with a potential long-term contributor or maintainer.  

Where do you communicate it: GitHub issue templates.  
Loop contributors into issues when you know that they are interested in that particular area, this is powerful for introducing community members. If you use a community CRM, create tags so you can quickly search for relevant contributors. This will show them that you value their input and opinion. 

## Providing Sufficient Contributor Tools

To incentivize contributions, you need more than just a contributor guide; you need a toolkit. But don't overdo it. If you have too many resources, you may overwhelm them. Here are a few examples. Identify what makes most sense for your project and what you'll be able to maintain (and retire old material not to confuse them). 

   * Comprehensive docs 
   * PR checklist  
   * Templates  
   * Hello World 
   * Code walkthroughs (videos, docs, etc.)
   * Contributor ladder/"a day in the life of a maintainer" description 

***On demand videos:*** Contributing 101, guideline videos. These can be served through [automated bots](https://github.com/hoodiehq/first-timers-bot) (e.g.  "hey, I see you are a first-time contributor. Check out this video on how to successfully submit a PR").  

***New contributor workshops:*** This also makes maintainers more comfortable with them contributing  

## Automate as much as you can  

Automation is great and you should use it wherever possible. The Kubernetes project leverages a lot of bots. From ensuring issues are properly labeled to guiding contributors towards a successful PR. But beware, if you use too many bots people will start ignoring them no matter how useful the info they provide. A balanced, strategic approach is key. Also, don't forget that automation is a great way for people to be involved with the project by helping to build or document the infrastructure that makes your project work.  

The Kubernetes project uses [prow](https://github.com/kubernetes/test-infra/tree/master/prow), a CI/CD tool written for Kubernetes handling a lot of the configuration of the workflow bots. It does have quite a bit of maintenance overhead and there are certainly more lightweight solutions such as GitHub apps and [GitHub Actions](https://github.com/actions). [Derek](https://github.com/alexellis/derek) handles labeling issues as well as closing issues or assigning them to other people.  

## Single GitHub repo vs org-level GitHub boards  

If you're maintaining one repo, having a single GitHub project works well. For projects with multiple subprojects, org level boards are great. It allows you to pull things with a common thread into the same board. However, you do lose some of the automation. Automated workflows, for instance, won't automatically add issues or PRs  to those workflows. A maintainer will have to do it manually, but once it's on in the workflow it will move through.   

The benefit is that it allows you to create GitHub teams and assign teams specific permissions within the board. This is also an opportunity for contributors. GitHub recently created triage and maintainer roles for repos. 

While in a repo level board users can get direct permissions to the repo, with an org-level board you can add users to a GitHub team and assign permissions to various repositories in the organization at a granular level, which provides more flexibility.  

You should also leverage GitHub's automated workflows. Here's how the Kubernetes project uses Kanban workflows:  
    Each time an issue is created, it will drop it into a "to do" column. PRs that are in flight will be moved to the "progress" column, etc. They rename the  "to do" column to backlog to avoid assumptions that what's in that column is up next. Then they create a non-automated "to do" column where maintainers can manually move issues they want to tackle next. 

Explore other workflows if Kanban isn't a great fit for your project -- there is something for everyone. 
  
Tool | What it does
---|---  
First timer bot |   
GitHub Actions | Automated PR check, Sign commits, Style checkers   
First interaction |    
First issue greeter |  
Test-infra |    
Derek bot | Modeled as a stripped down version of being able to use slash commands. Serverless take on prow.   
Code owners | Automating the "I need to look at it" the bot will help you to do that. To manage your own queue  
Fejta bot| Like probot but for prow. May be difficult to manage.   
Hubot >> hubot stale |    
Probot stale | Set inactivity levels (wait 90 days to mark something as stale) and the bot will drop a comment are you still interested? After another 30 days it will replace stale with rotten. Another 30 days it gets closed. 







