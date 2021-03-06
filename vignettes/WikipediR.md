<!--
%\VignetteEngine{knitr::knitr}
%\VignetteIndexEntry{WikipediR}
-->

#WikipediR: A MediaWiki API client library
Many websites run on versions of MediaWiki, most prominently Wikipedia and its sister sites. WikipediR is an API client library that allows you to conveniently make requests for content and associated metadata against MediaWiki instances.

## Retrieving content
"content" can mean a lot of different things - but mostly, we mean the text of an article, either its current version or any previous versions. Current versions can be retrieved using <code>page\_content</code>, which provides both HTML and wikitext as possible output formats. Older, individual revisions can be retrieved with <code>revision\_content</code>. These functions also return a range of possible metadata about the revisions or articles in question.

Diffs between revisions can be generated using <code>revision\_diff</code>, while individual ''elements'' of a page's content - particularly links - can be extracted using <code>page\_links</code>, <code>page\_backlinks</code>, and <code>page\_external\_links</code>. And if the interest is in changes to content, rather than content itself, <code>recent\_changes</code> can be used to grab a slice of a project's Special:RecentChanges feed.

## Retrieving metadata
Page-related information can be accessed using <code>page\_info</code>, while categories that a page possesses can be retrieved with <code>categories\_in\_page</code> - the inverse of this operation (what pages are in a particular category?) uses <code>pages\_in\_category</code>.

User-related info can be accessed with <code>user\_information</code>, while <code>user\_contributions</code> allows access to recent contributions by a particular user: this can be conveniently linked up with <code>revision\_content</code>, mentioned above, to retrieve the content of the last N edits by a particular editor, or metadata about those edits.
