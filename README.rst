helga-poems
===========

A helga command to generate either haiku or tanka poems. All five or seven syllable lines are user
generated and stored using this plugin. Usage::

    helga (haiku|tanka) [blame|tweet|about <term>|by <nick>|(add|add_use|use|remove|claim) (fives|sevens) (INPUT ...)].

Without any arguments ``helga haiku`` or ``helga tanka`` will produce a randomly generated haiku or
tanka from stored five or seven syllable lines respectively. Each subcommand acts as follows:

``blame``
    Get a list of the nicks of the users that authored the lines of a generated haiku

``about <term>``
    Generate a haiku or tanka using a given term. This term supports any valid regular expression.
    For example, ``!haiku about foo`` will search for lines containing 'foo', but ``!haiku about foo$``
    will only return lines that end with foo

``by <nick>``
    Generate a haiku or tanka with lines by the given nick. If not enough lines exist for this nick,
    then lines are selected at random

``add (fives|sevens) (INPUT ...)``
    Add a five or seven syllable line to the database but do not generate a poem

``add_use (fives|sevens) (INPUT ...)``
    Add a five or seven syllable line to the database and then generate and return a poem containing
    that line

``use (fives|sevens) (INPUT ...)``
    Generate a poem containing the given five or seven syllable line, but do not store it for future poems

``claim (fives|sevens) (INPUT ...)``
    Allows the requesting user to claim authorship of a given five or seven syllable line

A bit of an undocumented feature, but poems can be tweeted to some Twitter account. For example, generating
a poem with ``!haiku`` followed by ``!haiku tweet``. This requires some additional settings:

* ``TWITTER_CONSUMER_KEY``
* ``TWITTER_CONSUMER_SECRET``
* ``TWITTER_OAUTH_TOKEN``
* ``TWITTER_OAUTH_TOKEN_SECRET``
* ``TWITTER_USERNAME``


.. important::

    This plugin requires database access



License
-------

Copyright (c) 2015 Shaun Duncan

Licensed under an `MIT`_ license.

.. _`MIT`: https://github.com/shaunduncan/helga-poems/blob/master/LICENSE
