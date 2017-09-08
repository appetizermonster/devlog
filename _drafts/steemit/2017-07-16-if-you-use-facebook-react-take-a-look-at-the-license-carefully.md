---
layout: post
title: If you use Facebook React, Take a look at the LICENSE carefully!
date: 2017-07-16 12:36:24 +0000
---

<center><img src="https://steemitimages.com/DQmRQfCMx9feJZstXZCPDndqFWsaApsdduQ3HmT3JftF5ff/image.png" style="max-width:100%;">
</center>
Facebook React is an open-source project that has been widely used by many web services. (Steemit.com also uses React)
I've also used React for my small project, but I didn't really care about licensing.

and then I saw a post today in [Hacker News](https://news.ycombinator.com/) saying that [the Apache Foundation bans projects from using Code with "BSD+Patent" license](https://news.ycombinator.com/item?id=14779881), an open source license used on Facebook.
that means the React can't be used on Apache Foundation projects.

The point of controversy is the condition for the use of the patent specified in "BSD+Patent" which React uses.
Following is a part of the license:

```
The license granted hereunder will terminate, automatically and without notice,
if you (or any of your subsidiaries, corporate affiliates or agents) initiate
directly or indirectly, or take a direct financial interest in, any Patent
Assertion: (i) against Facebook or any of its subsidiaries or corporate
affiliates
```

If you file any patent lawsuit against Facebook, you will automatically lose your parent use rights to React.
It does not matter whether is is a patent suit related with React.

For example, if **A** company uses Facebook React and Facebook infringes **A**'s patent and **A** files a patent lawsuit on Facebook, then **A** loses the right to use of React.
And if React is used on **A**'s core product, the problem can be bigger.
(The actual outcome will depend on the court's decision)

And it seems that discussions are underway in the React repo because someone is requesting a license change. This may lead to change React's license to more flexible.

If you are using React (especially if you are using it for commercial product), you should learn more about its licensing.
Thank you.