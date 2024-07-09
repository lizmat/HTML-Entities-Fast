[![Actions Status](https://github.com/lizmat/HTML-Entities-Fast/actions/workflows/test.yml/badge.svg)](https://github.com/lizmat/HTML-Entities-Fast/actions)

NAME
====

HTML::Entity::Fast - Encode / Decode HTML entities faster

SYNOPSIS
========

```raku
use HTML::Entity::Fast;

say encode-html-entities '<ent> & ©';                 # &lt;ent&gt; &amp; &copy;
say decode-html-entities '&lt;ent&gt; &amp; &copy;';  # <ent> & ©

my $w-encode = whitelist-in-encode("<",">");
say encode-html-entities '<ent> & ©', $w-encode;                 # <ent> &amp; &copy;

my $w-decode = whitelist-in-decode('&amp;');
say decode-html-entities '&lt;ent&gt; &amp; &copy;', $w-decode;  # <ent> &amp; ©
```

DESCRIPTION
===========

HTML::Entity::Fast provides subroutines for encoding and decoding HTML entities in a string.

SUBROUTINES
===========

encode-html-entities
--------------------

```raku
say encode-html-entities '<ent> & ©';             # &lt;ent&gt; &amp; &copy;

my $w-encode = whitelist-in-encode("<",">");
say encode-html-entities '<ent> & ©', $w-encode;  # <ent> &amp; &copy;
```

Encode any special characters in a given string to their HTML entity counterpart. Optionally takes a second argument indicating the exact mapping to be used (which is usually the result of a call to the `whitelist-in-encode` subroutine).

decode-html-entities
--------------------

```raku
say decode-html-entities '&lt;ent&gt; &amp; &copy;';  # <ent> & ©

my $w-decode = whitelist-in-decode('&amp;');
say decode-html-entities '&lt;ent&gt; &amp; &copy;', $w-decode;  # <ent> &amp; ©
```

Decode any HTML entities in a given string to their Unicode counterpart. Optionally takes a second argument indicatig the exact mapping to be used (which is usually the result of a call to the `whitelist-in-decode` subroutine).

whitelist-in-encode
-------------------

```raku
my $w-encode = whitelist-in-encode("<",">");
```

The `whitelist-in-encode` subroutine takes any number of arguments, each indicating a character that should **not** be converted by the `encode-html-entities` subroutine. It returns a lookup map that can be specified as the second positional argument to `encode-html-entities`.

whitelist-in-decode
-------------------

```raku
my $w-decode = whitelist-in-decode('&amp;');
```

The `whitelist-in-decode` subroutine takes any number of arguments, each indicating a HTML entity that should **not** be converted by the `decode-html-entities` subroutine. It returns a lookup map that can be specified as the second positional argument to `decode-html-entities`.

AUTHOR
======

Elizabeth Mattijsen <liz@raku.rocks>

Source can be located at: https://github.com/lizmat/HTML-Entity-Fast . Comments and Pull Requests are welcome.

If you like this module, or what I’m doing more generally, committing to a [small sponsorship](https://github.com/sponsors/lizmat/) would mean a great deal to me!

COPYRIGHT AND LICENSE
=====================

Copyright 2022, 2024 Elizabeth Mattijsen

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

