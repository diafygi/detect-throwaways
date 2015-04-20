# detect-throwaways
Demo: https://diafygi.github.io/detect-throwaways/index.html

## Description

This is a demo that allows websites to detect and connect throwaway accounts to
their real users when the user is using Firefox's Private Browsing mode. This
exploits Firefox's [Bug #1100154](https://bugzilla.mozilla.org/show_bug.cgi?id=1100154)
that I reported in 2014. Chrome users are not affected by this exploit.

This exploit could be used by sites that allow users to create throwawy or
anonymous accounts (Reddit, HackerNews, 4Chan, etc.) to secretly detect a user's
real username if that user is using a Firefox Private Browsing window for the
throwaway account while keeping their real account open in their main browser
session.

##How the exploit works

This exploit works by using window.open with a target window name that exists
on the other side of the privacy barrier. If you have a window named "myrealwindow"
in your main browser tabs, a link or javascript window.open that targets that
name will change the url of that tab, *even if the link is across the privacy
barrier*. See [Bug #1100154](https://bugzilla.mozilla.org/show_bug.cgi?id=1100154)
for more details.
