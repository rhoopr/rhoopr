# GitHub Is a Single Point of Failure (I Got Auto-Suspended 🫠)

On February 24, 2026, I tried to log into GitHub and the login failed. The page refreshed on a failed redirect to what was apparently a "suspended" page. There was no email or notification of any kind. I figured out what happened by checking my profile from another browser and seeing 404s on all my repos.

I filled in GitHub's support form. They auto-responded asking me to resubmit essentially the same information I'd already provided. Then silence. No access to my repositories, no indication of what rule I'd supposedly broken, and no timeline for when I might hear back.

While I was locked out, I noticed that my Homebrew taps were broken, which makes sense - the repos backing them were 404ing along with everything else. But the error message Homebrew showed to *end users* trying to install from my tap said something like "Your GitHub account is suspended." That "Your" is doing some wrong work there. That's the installing user's session, not mine. Beyond the taps, my GitHub Pages site was also down. Anything I distributed through GitHub was just gone.

## Resolution

On March 6, ten days after the suspension, my account was re-enabled. The full explanation from GitHub support:

> Sometimes our abuse detecting systems highlight accounts that need to be manually reviewed. We've cleared the restrictions from your account, so you have full access to GitHub again.

That was it. No detail on what triggered the review or what I should do differently.

Ten days is actually not bad - I've seen Reddit posts from people who waited 90+ days, and some who never got their accounts back at all. But ten days of radio silence followed by a one-sentence resolution still doesn't feel like a functioning process.

## What caused it?

I genuinely don't know, and GitHub didn't say.

My best guess is the email domain. I use an `.xyz` email address for my GitHub account, and I also got instantly banned trying to sign up for Claude with that same address a while back. Two unrelated platforms flagging the same domain is hard to ignore. `.xyz` is cheap and popular with spammers, so it's plausible that some platforms treat it as a low-trust TLD. I'm considering moving to a different domain, which is annoying, but practicality wins.

I also wondered whether Bambu Lab filed some kind of automated takedown against my [bambutop](https://github.com/rhoopr/bambutop) repo, which interfaces with their printers' local APIs. But there are plenty of public repos doing similar things, so this seems unlikely.

The other possibility is fingerprinting. I use AdGuard DNS and privacy-focused browser extensions, so my fingerprint probably looks different across sessions. Could be enough to trip an automated flag.

## What I took from this

The whole experience left a bad taste. The suspension itself I can understand - automated systems make mistakes at scale. But there was no notification when it happened, a canned auto-response when I reached out, nothing for ten days, and then a vague one-liner when it was over. At no point did I have any sense of whether my account would come back in a day, a month, or never.

If you distribute anything through GitHub - Homebrew taps, Pages sites, release binaries - all of it can go offline without warning because an automated system flagged your account.

One of the projects I'm working on is [icloudpd-rs](https://github.com/rhoopr/icloudpd-rs), a tool for downloading your iCloud photos to local storage. This suspension was a good reminder of why. There is no cloud, it's just other people's computers. Have good backups.
