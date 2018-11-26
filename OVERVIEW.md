# IndieWeb Overview
IndieWeb is an independent attempt to implement concepts of the Semantic Web.

## Semantic Web
Semantic Web is a layer upon the World Wide Web which allows a better reuse of content and data.

### Information Ownership
Large amount of online information is kept inside proprietary silos walled with access control. Information inside silos is created by people but owned by corporations. The Semantic / Indie Web movement wants to remedy this situation by giving back information ownership to its creators.

### Information Value
Information on the web is untrustworthy in most cases since the source of the information is mostly unknown. It’s hard to decide if an information is true, false, original or copied from another source. When the source is unknown the value of the information is questionable.

Information wants to be free and in the same way expensive. World Wide Web managed to make it free, Semantic Web tries to add value to it.

### Information To Data
On web we have more information than data. Information is plain content understandable only by humans when data is structured, reusable, and understandable also by machines.

Semantic web transforms content, information into data and makes it generally useful.

## The Semantic Web Proposal
Semantic Web proposes the following solutions to transform information to data, make it reusable, and attach ownership and value.

### Identity
The identity of an author is proven across all the web.

### Annotation
Even the smallest piece of content an author creates is annotated and transformed into data using semantic metadata.

### Syndication / Federation
Every piece of content a.) with an identified author b.) equipped with semantic metadata can freely circulate and grow on the web and return to its author.

## The IndieWeb Solution
Indieweb takes the Semantic Web proposal and implements on its own way, sometimes following standards, sometimes inventing them.

Implementing the IndieWeb solution can be a [very tedious task](https://vincentp.me/articles/2018/11/14/20-00/).

### Identity

#### Web sign-in / Rel-Me
Identifies people through their websites instead of their email in a more private way. It is a successor of OpenID which is shut down in 2018 in spite powering over 1 billion accounts in 2016.

#### IndieAuth
The best and most comprehensive implementation of Web sign-in / Rel-Me Auth protocol.

IndieAuth is supported by the W3C.

### Annotation
There are four semantic annotation formats that can be used in HTML documents: Microformats, RDFa, Microdata and JSON-LD.

#### Microformats 2
It’s a non-standard, community supported format. It seems its focus is on simplicity of use above else. Not sure if adheres to any standard ontologies / vocabularies like Schema.org however with a tool, W3C's GRDDL it can be made compatible with the Semantic Web.

All other three formats are standardised / associated with a body. Microformats is not. Why IndieWeb is forcing its usage?

JSON-LD seems to be the most popular format supported by Google and Mastodon.

### Syndication / Federation
This is a growing list of technologies and methods sometimes standard, sometimes proprietary, sometimes extending, other times competing with each other.

#### Webmentions
A technology to collect mentions of your content across the web. If someone else is referring to one of your URLs (permalinks) you’ll receive a webmention.

It’s an open source project not associated with any standards body.

Associated concepts are PermaShortlinks, PermaShortCitations.

#### POSSE
Publish on your own site, syndicate elsewhere — it helps you distribute automatically your content across other networks like Twitter, Facebook and so on.

Associated concepts are PESOS, PESETAS and backfeed.

#### Backfeed
Collect interactions (comments, likes, reposts) with your content from external networks. The prerequisite is that content has to be published with POSSE.

#### Web Actions
Equip your content with actionable elements like a Like button, reply or repost.

This makes your own website in the same way interactive and actionable like other social networks.

#### MicroPub
A protocol to independently manage content.

A common practice is that content is managed through a content management system. Lately many websites has no such content management system attached.

For them there it is MicroPub which is a W3C recommendation API.

#### WebSub
Notify others when your site changes. It’s the newer version of PubSubHub, a distributed publish-subscribe technology.
