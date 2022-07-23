[![Actions Status](https://github.com/lizmat/HTML-Entities-Fast/actions/workflows/test.yml/badge.svg)](https://github.com/lizmat/HTML-Entities-Fast/actions)

NAME
====

HTML::Entity::Fast - Encode / Decode HTML entities

SYNOPSIS
========

```raku
use HTML::Entity::Fast;

say encode-html-entities '<ent> & ©';  # &LT;ent&GT; &AMP; &COPY;
say decode-html-entities '&LT;ent&GT; &AMP; &COPY;'  # <ent> & ©
```

DESCRIPTION
===========

HTML::Entity::Fast provides two subroutines, one for encoding HTML entities in a string, and one for decoding them.

AUTHOR
======

Elizabeth Mattijsen <liz@raku.rocks>

Source can be located at: https://github.com/lizmat/HTML-Entity-Fast . Comments and Pull Requests are welcome.

If you like this module, or what I’m doing more generally, committing to a [small sponsorship](https://github.com/sponsors/lizmat/) would mean a great deal to me!

COPYRIGHT AND LICENSE
=====================

Copyright 2022 Elizabeth Mattijsen

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

