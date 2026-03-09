# I Got Suspended from GitHub for 10 Days

On February 24, 2026, I tried to log into GitHub and the login failed. The page refreshed on a failed redirect to what was apparently a "suspended" page. There was no email or notification of any kind. I figured out what happened by checking my profile from another browser and seeing 404s on all my repos.

I filled in GitHub's support form, which asks you to describe the issue and provide your account details. They auto-responded asking me to resubmit essentially the same information I'd already provided. Then silence. I had no access to my repositories, no indication of what rule I'd supposedly broken, and no timeline for when I might hear back. I just had to wait.

While I was locked out, I noticed that my Homebrew taps were broken, which makes sense - the repos backing them were 404ing along with everything else. But the error message Homebrew showed to *end users* trying to install from my tap said something like "Your GitHub account is suspended." That "Your" is doing some wrong work there. That's the installing user's session, not mine. They haven't been suspended; they're just trying to install a package. It's a small bug, but a weird one to encounter from the other side of it. Beyond the taps, my GitHub Pages site was also down. Anything I distributed through GitHub was just gone, with no way for me to redirect users or communicate what was happening.

## Resolution

On March 6, ten days after the suspension, my account was re-enabled. The full explanation from GitHub support:

> Sometimes our abuse detecting systems highlight accounts that need to be manually reviewed. We've cleared the restrictions from your account, so you have full access to GitHub again.

That was it. No detail on what triggered the review, what their systems flagged, or what I should do differently.

Ten days is actually not bad, relatively speaking. I've seen Reddit posts from people who waited 90+ days with no response, and some who never got their accounts back at all. So I got lucky with the timeline. But ten days of total radio silence, followed by a one-sentence resolution, still doesn't feel like a functioning process.

## What caused it?

I genuinely don't know. GitHub didn't say, and I haven't been able to narrow it down with any confidence.

My best guess is the email domain. I use an `.xyz` email address for my GitHub account, and separately, I got instantly banned trying to sign up for Claude with that same address a while back. I didn't fight that one since it was a fresh account and I could just use a different email, but two unrelated platforms flagging the same domain is hard to ignore. `.xyz` is cheap and popular with spammers, so it's plausible that some platforms treat it as a low-trust TLD. I'm considering moving to a different domain, which is annoying since I like the one I have, but practicality wins.

I also wondered whether Bambu Lab filed some kind of automated takedown against my [bambutop](https://github.com/rhoopr/bambutop) repo, which interfaces with their printers' local APIs. But there are plenty of public repos doing similar things, and I haven't heard of Bambu going after any of them. This one seems unlikely.

The other possibility is fingerprinting. I use AdGuard DNS and privacy-focused browser extensions, so my fingerprint probably looks different across sessions. I don't know how aggressive GitHub's abuse detection is on that front, but it's in the realm of things that could trip an automated flag.

## What I took from this

The whole experience left a bad taste, and most of it comes down to communication. The suspension itself I can understand - automated systems make mistakes, and at GitHub's scale you're going to get false positives. But there was no notification when it happened, a canned auto-response when I reached out, nothing for ten days, and then a vague one-liner when it was over. At no point did I have any sense of whether my account would be restored in a day, a month, or never.

If you distribute anything through GitHub - Homebrew taps, Pages sites, release binaries - all of it can go offline without warning because an automated system flagged your account. There's no grace period, no way to set up redirects, and no notification to your users. My stuff just vanished, and anyone who depended on it had no idea why.

One of the projects I'm working on right now is [icloudpd-rs](https://github.com/rhoopr/icloudpd-rs), a tool for downloading your iCloud photos to local storage. The whole premise is that you shouldn't be fully reliant on someone else's infrastructure for your own data. This suspension was a good reminder of why. There is no cloud, it's just other people's computers. Have good backups.
