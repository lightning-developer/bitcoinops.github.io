---
title: Onion messages

## Optional.  Shorter name to use for reference style links e.g., "foo"
## will allow using the link [topic foo][].  Not case sensitive
# shortname: foo

## Optional.  An entry will be added to the topics index for each alias
#aliases:
#  - Foo

## Required.  At least one category to which this topic belongs.  See
## schema for options
categories:
  - Lightning Network

## Optional.  Produces a Markdown link with either "[title][]" or
## "[title](link)"
primary_sources:
    - title: Onion message support
      link: https://github.com/lightning/bolts/pull/759

## Optional.  Each entry requires "title" and "url".  May also use "feature:
## true" to bold entry and "date"
optech_mentions:
  - title: Proposal for LN direct messages
    url: /en/newsletters/2020/02/26/#ln-direct-messages

  - title: "C-Lightning #3600 adds experimental support for onion messages using blinded paths"
    url: /en/newsletters/2020/04/08/#onion-messages

  - title: "Eclair #1957 adds basic support for onion messages"
    url: /en/newsletters/2021/11/17/#eclair-1957

## Optional.  Same format as "primary_sources" above
# see_also:
#   - title:
#     link:

## Optional.  Force the display (true) or non-display (false) of stub
## topic notice.  Default is to display if the page.content is below a
## threshold word count
#stub: false

## Required.  Use Markdown formatting.  Only one paragraph.  No links allowed.
## Should be less than 500 characters
excerpt: >
  **Onion messages** are messages that can be sent across the LN network
  by nodes that support the protocol.  Messages don't use HTLCs,
  minimizing the use of LN node resources.
---

{% include references.md %}
{% include linkers/issues.md issues="" %}
