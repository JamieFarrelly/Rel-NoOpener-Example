# Rel NoOpener Example

Example of how the rel attribute can be used for phishing purposes, [available here](https://jamiefarrelly.github.io/Rel-NoOpener-Example/).


Overview
--------------------------

Any website that uses target="_blank" on their links, allows user generated content and doesn't use the rel="noopener" attribute on 
their links (I'm looking at you Facebook, Twitter etc.) is vulnerable to this type of phishing attack.

The new link that is opened can run a very simple script [like the one in this example](https://github.com/JamieFarrelly/Rel-NoOpener-Example/blob/master/opened-link.html)
which allows you to change what the previous tab was. In this case I changed the previous tab to point towards one of my tweets, but
imagine if it posted to a login page to the site you were previously on - that's where someone could do serious damage.


How to use target="_blank" properly
--------------------------

**Good**
```html
<!-- noopener is for all browsers but Firefox, noreferrer is for Firefox -->
<a href="opened-link.html" target="_blank" rel="noopener noreferrer">Facebook.com</a>
```

**Bad**
```html
<a href="opened-link.html" target="_blank">Facebook.com</a>
```

Solution (for now)
--------------------------
If you use Chrome, I've created an extension which adds rel="noopener noreferrer" to all the links on the current page that you are on. Take a look at it [here](https://github.com/JamieFarrelly/No-Opener-No-Phishers).

Useful Links
--------------------------

[Bug raised with Chrome in 2013](https://bugs.chromium.org/p/chromium/issues/detail?id=168988)

[Another example, and Instagram adding noopener to their links](https://dev.to/ben/the-targetblank-vulnerability-by-example)

[Discussion on Reddit](https://www.reddit.com/r/programming/comments/4zikpx/the_target_blank_vulnerability_by_example/)
