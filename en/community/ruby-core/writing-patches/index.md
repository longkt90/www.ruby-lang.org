---
layout: page
title: "Patch Writer’s Guide"
lang: en
---

Here follow some tips, straight from Matz, on how to get
your patches considered. They were originally
[posted on the Ruby-Core mailing list][ruby-core-post].
{: .summary}

~~~
Subject: [ruby-core:25139] Patch writer's guide to submit
From: Yukihiro Matsumoto <matz ruby-lang.org>
Date: Wed, 26 Aug 2009 22:06:22 +0900
~~~

Hi,

Sometimes we lazy core developers have procrastinated to review
submitted patches, have been late to merge patches, and have
frustrated submitters. That is unfortunate for both sides.
Here are guidelines on how to avoid such miscommunication.

* one modification per patch

  This is the biggest issue for most deferred patches. When you
  submit a patch that fixes multiple bugs (and adds features) at once,
  we have to separate them before applying it. It is a rather hard task
  for us busy developers, so this kind of patches tends to be deferred.
  No big patches please.

* more description

  Sometimes mere patches do not describe the problems they fix.
  A better description (a problem that they fix, preconditions, platform, etc.)
  would help a patch to be merged earlier.

* diff to the latest

  Your problem might have been fixed in the latest revision. Or the code
  might be totally different. Before submitting a patch, try to fetch
  the latest version (`trunk` for 1.9, `ruby_1_8` for 1.8) from Subversion,
  please.

* `diff -u`

  We prefer `diff -u` style unified diff patches to `diff -c` or
  any other style of patches. They are far easier to review.
  Do not send modified files, we do not want to make a diff by ourselves.

* (optional) test cases

  A patch to test cases (preferably a patch to `test/*/test_*.rb`)
  would help us understand the patch and your intention.

We might move to Git style push/pull in the future. But until then,
the above guidelines would help you to avoid frustration.

Thank you.

matz.

[ruby-core-post]: http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-core/25139
