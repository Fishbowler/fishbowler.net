---
title: "Between 11 and 15 Steps to a Hugo Site, hosted for free"
date: 2019-06-16
tags : ["hugo"]
categories : ["technology"]
layout: post
draft: false
---

I've just rebuilt my blog using Hugo, and wanted to share my steps. This isn't really my work - I was given all of this knowledge gratis from [Pete](https://github.com/pete-woods), who definitely knows - he's got his [own site](https://pete-woods.com/).

### Step 1: Lay the groundwork

Install hugo using [brew](https://brew.sh/) or one of the [other methods](https://gohugo.io/getting-started/installing/). Create a new folder and make it an empty git repo.

{{< highlight bash >}}
brew install hugo
cd ~/projects
mkdir website
cd website
git init
{{< /highlight >}}

### Step 2: Pick a theme and add it to your folder

Go to the [Hugo Themes](https://themes.gohugo.io/) page. Find one you like. Follow the Homepage or look instructions to get the GitHub Clone URL for the theme, then add it within a "themes" folder as a submodule to your empty repo.

{{< highlight bash >}}
git submodule add git@github.com:spf13/hyde.git themes/hyde
{{< /highlight >}}

#### OMG, the caveats

This _seems_ like such an easy step. It isn't. A Hugo theme looks beautiful, and it's perfect for what you want. Then you try to use it. Hugo moved on, but the theme wasn't maintained, and now it doesn't work at all. It's the same problem WordPress suffers from. For my own blog, the 4th theme was the one that worked. I eventually found one problem with it, so I forked the theme and made the one-line change required to fix it (and offered a PR upstream because I'm a good guy).


### Step 3: Pinch the example site (optional)

If you want to accelerate your site development, almost all themes have an exampleSite included in the theme. You can grab it and use it as a starting point.

{{< highlight bash >}}
cp -r themes/hyde/exampleSite/* .
{{< /highlight >}}

### Step 4: Fix up the config.toml

Hugo has a few different config file formats, but toml is the default and the most common. It's named config.toml, and lives in the root of the folder. If you copied the exampleSite, you can amend the config.toml that will have been copied along with it, but even if you're amending rather than writing from scratch, you'll still want the theme's readme to see all of the avialable options.

{{< highlight toml >}}
baseURL = "http://example.org/"
theme = "hyde"
title = "My Hugo Site"

[params]
googleAnalytics = "UA-123456789-1"
author = "J Bloggs"
description = "My site for learning Hugo"

[params.social]
twitter = "jbloggs"
github = "jbloggs"
stackoverflow = "123456"
{{< /highlight >}}

### Step 5: Test

You can test the site live at any time using hugo's inbuilt webserver. Run the server, then visit [http://localhost:1313](http://localhost:1313).

{{< highlight bash >}}
hugo server
{{< /highlight >}}


### Step 6: Add new content

Blog posts tend to go in /content/posts, and are always in markdown, with some extra post metadata at the top. Some is defined by Hugo, but themes can expand on this.

{{< highlight markdown >}}
+++
title: "My first post"
date: 2019-06-16
+++
{{< /highlight >}}

Images go in /static, but you can arrange this as you like, e.g. /static/img, then reference them in a post as 

{{< highlight markdown >}}
![](/img/funny_cat.gif)
{{< /highlight >}}

### Step 7: Test again.

Whilst writing posts, you can keep the hugo server running, keep saving, and watching your post get updated live.

### Step 8: Build

Once you're happy that your content is good, you can generate the site "for real". Just run hugo with no parameters.

{{< highlight bash >}}
hugo
{{< /highlight >}}

### Step 9: Test some more

Is your markdown good? Is it generating some good HTML? What about your theme? Have you put in any dead links?
You can check all of this using htmlproofer.

I've done this with Docker (hattip to Pete's repo for getting me started with this), but you _could_ use htmlproofer or a similar tool separately.

{{< highlight bash >}}
docker run -v $PWD/public/:/root/public cibuilds/hugo htmlproofer /root/public --allow-hash-href --check-html --internal-domains='yourdomain.com' --empty-alt-ignore  --http-status-ignore=999
{{< /highlight >}}

Lets break that up a bit and explain what it's doing:

| fragment                            | description                                                                                                 |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------|
| docker run                          | runs a command inside a docker container                                                                    |
| $PWD/public/:/root/public           | mounts your public folder (which hugo generated) as /root/public inside the container                       |
| cibuilds/hugo                       | the container we'll run - I'm using CircleCI's image because I'll probably move this to building there soon |
| htmlproofer /root/public            | run htmlproofer on the /root/public folder                                                                  |
| --allow-hash-href                   | permits <a href='#'>                                                                                        |
| --check-html                        | validates the HTML formatting and structure                                                                 |
| --internal-domains='yourdomain.com' | sets the domain that this site will live in - swap it for the URL in config.toml (used when checking links) |
| --empty-alt-ignore                  | suppresses errors on empty alt tags for images                                                              |
| --http-status-ignore=999            | because LinkedIn doesn't like the scraper and returns HTTP/999                                              |

### Step 10: Use NPM packaging to wrap up the commands

Building is simple, but that testing command is pretty weighty. Let's wrap all of this in a package.json so we don't need to remember it all.

Create a package.json in root of your folder that looks like this:

{{< highlight json >}}
{
  "name": "My Website",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "build": "hugo",
    "test": "docker run -v $PWD/public/:/root/public cibuilds/hugo htmlproofer /root/public --allow-hash-href --check-html --internal-domains='yourdomain.com' --empty-alt-ignore --http-status-ignore=999"
  },
  "author": "My Name"
}
{{< /highlight >}}

Now you can simply `npm test` to run all of that testing, find out whether you've got posts linking to dead sites (found that), whether you've mistyped your StackOverflow username (did that), or whether your chosen theme is slightly broken (this is how I found the one bug in my theme - HTML errors are one of the most likely to cause problems for people not using your particular browser).

### Step 11: Import old content (optional)

I had old posts on Blogger that I didn't want to lose. As it turns out, I didn't have to copy and paste every post and convert it to markdown. There's a bunch of friendly folk out there who have been through this journey before and build some great tools to import posts from old sites.

If this is something that interests you, take a look at [this post](https://gohugo.io/tools/migrations/) in Hugo's docs.

### Step 11a: Test again

If you imported old content, build and test. I found out that my old site had been linking to long-dead PDFs - oops!

### Step 12: Put it on Firebase

I was recommended Firebase as a static blog site host as it's free for the sorts of volumes an average blog is likely to get.

Setup:

* Go to [firebase.google.com](https://firebase.google.com/)
* Login with Google
* Go to the [Console](https://console.firebase.google.com/)
* Create a project, setting your Firestore to somewhere close to home
* Click to add an App (Web, not iOS/Android), and
* Tick to set up Firebase Hosting
* Click the drop-down below Firebase Hosting (it'll have a pregenerated name based on the project name) and choose Create A New Site
* Pick a name for your site - if you don't choose to buy and add your own domain later, your site will live on `https://your-choice.web.app`
* Hit Register App
* Skip the Add Firebase SDK step - we don't need this - just hit Next
* For Firebase CLI, don't accept their suggestion and instead add it to your own package instead using `npm install --save-dev firebase-tools` - this will be much easier when you switch computer, or switch to using

Configure:

* Run `$(npm bin)/firebase login` (those are round brackets). You'll be bounced to the browser for Google authentication and approval.
* Run `$(npm bin)/firebase init`
* Create a `firebase.json` in the root folder of your site (alongside the config.toml) that looks something like this:
{{< highlight json >}}
{
  "hosting": {
    "public": "public",
    "site": "your-domain-choice",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ]
  }
}
{{< /highlight >}}

Deploy:

* One step. Run `$(npm bin)/firebase deploy` and the last version of the site you built by running `hugo` will be live.

### Step 13: Wrap firebase in NPM too

When you installed `firebase-tools`, it was added to your `package.json` file. You can add an additional script to wrap up the firebase deploy step, keeping everything in one place, and nothing to remember.

Add the deploy command to the scripts section:

{{< highlight json >}}
{
  "scripts": {
    "build": "hugo",
    "test": "docker run -v $PWD/public/:/root/public cibuilds/hugo htmlproofer /root/public --allow-hash-href --check-html --internal-domains='yourdomain.com' --empty-alt-ignore --http-status-ignore=999",
    "deploy": "firebase deploy --token=$FIREBASE_DEPLOY_TOKEN"
  }
}
{{< /highlight >}}

The deploy token doesn't need to be set locally - you can use `firebase login` for that - but you'll want it if you ever move your builds into a cloud provider.

### Step 14: Put your site on GitHub (optional)

I hear it's the done thing nowadays, to have the source of your personal website on GitHub for all to see. I've put mine [here](https://github.com/Fishbowler/fishbowler.net).

You've already got a git repository locally, so we need to pop all of our files in, and publish it.

* Create a file called `.gitignore` in the root directory (no extension)
* Add this to the file:
{{< highlight bash >}}
public
resources
node_modules
{{< /highlight >}}
* Run `git add -A`
* Run `git commit -am "Initial commit of website"`
* Get a [GitHub account](https://github.com/join) if you haven't already
* [Create](https://github.com/new) a repository - DO NOT tick "Initialize this repository with a README"
* Back in the terminal, run `git remote add origin https://github.com/YourAccount/YourRepositoryName.git` (or, better, if you've set up your [SSH key](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), `git remote add origin git@github.com:YourAccount/YourRepositoryName.git`)
* Finally, run `git push` to populate your GitHub repository with everything you've got locally.

### Step 15: Add your own domain (optional)

You might not want your blog on your-domain.web.app (which is also accessible on )

* Go to the [Firebase Console](https://console.firebase.google.com/)
* Click your project
* Click Hosting
* Click Connect Domain and follow the on-screen instructions