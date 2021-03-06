Phabricator Extensions
----------------------

This repository is a collection (known as libdisqus) of extensions for `Phabricator <http://phabricator.org/>`_, a tool
originally open sourced by Facebook for task management and code review.

Installing Arcanist Globally
============================

You'll need write access to /usr/local::

    $ curl -L https://raw.github.com/disqus/disqus-arcanist/master/getarcanist.sh | sudo sh

This will give you access to the following additional commands:

**create-arcconfig [path]**

Generates a .arcconfig based on the global arcanist installation at the given path.

If path is not set, it generates it in the current working directory.

**update-arcanist**

This executes the same script which you used to originally install Arcanist.

DisqusUnitTestEngine
====================

A basic implementation of a test runner that uses nose and nose-json to collect test results and submit them upstream
with differentials.

Add to your client's .arcconfig::

    {
      "unit_engine": "DisqusUnitTestEngine",
    }

ProjectAssignmentEventListener
==============================

Automatically assigns an owner to a new task (where one is not set) based on the first assigned project's ownership.

Add to your Phabricator's config::

    'events.listeners' => array(
      'ProjectAssignmentEventListener',
    ),