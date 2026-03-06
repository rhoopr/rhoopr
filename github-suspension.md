# I Got Suspended from GitHub for 10 Days

On February 24, 2026, I tried to log into GitHub and the login failed. The page refreshed on a failed redirect to what was apparently a "suspended" page. There was no email or notification of any kind. I figured out what happened by checking my profile from another browser and seeing 404s on all my repos.

## Support

I filled in GitHub's support form. They auto-responded asking me to resubmit essentially the same information I'd already provided, and then went quiet. I had no access to my repositories and no indication of what went wrong.

## A bug along the way

While I was locked out, I noticed that my Homebrew taps were broken, which makes sense. But the error message Homebrew showed to *end users* trying to install from my tap said something like "Your GitHub account is suspended." The word "Your" is doing some wrong work there. That's the installing user's session, not mine. 🤷‍♂️.

## Resolution

On March 6, my account was re-enabled. The explanation:

> Sometimes our abuse detecting systems highlight accounts that need to be manually reviewed. We've cleared the restrictions from your account, so you have full access to GitHub again.

No detail on what triggered it.

## What caused it?

I don't know. A few theories:

**.xyz domain?** I use an `.xyz` email address for my GitHub account. Separately, I also got instantly banned trying to sign up for Claude with that same domain a while back. I didn't pursue that one since it was a fresh account, but two separate platforms flagging the same email is a pattern. Maybe `.xyz` is considered a low-trust TLD. I'm considering moving off of it.

**Automated takedown?** My [bambutop](https://github.com/rhoopr/bambutop) repo interfaces with Bambu Lab printers, and I wondered if Bambu Lab filed some kind of automated takedown. But there are plenty of public repos doing similar things with their local APIs, so this seems unlikely.

**Fingerprinting?** I use AdGuard DNS and privacy-focused browser extensions. Maybe GitHub's systems flagged the inconsistent fingerprints across my login sessions.

## Takeaways

The whole process was ambiguous and unexplained. There was no notification on suspension, a canned auto-response from support, no communication for over a week (I've seen Reddit posts of >90 days, so I'm one of the lucky ones), and a vague one-liner when it was resolved.

If you depend on GitHub for distribution (Homebrew taps, GitHub Pages, etc.), it's worth knowing that an automated flag can take all of that offline without warning. Hopefully this didn't scare off the (small) handful of users who utilize my repos.

Incidentally, one of the projects I'm working on is [icloudpd-rs](https://github.com/rhoopr/icloudpd-rs), a tool for downloading your iCloud photos to local storage. There is no cloud, it's just other people's computers, and this whole experience is a good reminder to make sure you're not fully reliant on it. Have good backups.
