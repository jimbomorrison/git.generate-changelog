git.generate-changelog

This is a *very* basic script for generating a nice bit of changelog from your git commits.

It's usage is:

git.generate-changelog xxxxxxxx

Where xxxxxxx is a bit of the commit-id of your last release.

-----------

All the script does is regex for various keywords and then groups the type of changes together in little blocks.

The types are:

* Fix* => **FIXED**
* Add* => **NEW**
* *minor* => Excluded/hidden
* Merges => **MERGED BRANCHES**; We include them if they look useful (we use git-flow so it's designed to highlight 'finished features')
* ... everthing else => **OTHER CHANGES** 

We also stick the person who made the commit at the end of the line.. ~MyName

Example:

 - FIXED:

 -- Fixed bug in new foo ~Jim
 -- Fix - reduced button size to small in common fragments ~David
 -- FIX to unit sizing in record header to avoid button wrap ~David

 - NEW:

 -- Added; allow_304 & cancel_304 to memcache to allow modules/templates/use-cases to prevent 304s being thown on an ad-hoc basis.  Useful for ajax/search results ~Jim
 -- Added config switch for v6 subnav ~Jim
 -- Added class hooks and extra wrappers to ifxless units ~David

 - BRANCHES MERGED IN:

 -- Merged: feature/ifx6 -> develop

 - OTHER CHANGES:

 -- Minor debug fixes for vpath_module caching ~Jim
 -- Creating new debug template for Progress bars ~David
 -- Conflicts: ~Jim


TODO:

Read the docs for this markdown! ;-)