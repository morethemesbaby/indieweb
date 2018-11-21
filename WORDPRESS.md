# IndieWeb for WordPress
To sum up, IndieWeb does the following:

1. Converts monolithic, human-only understandable content into atomic chunks equipped with semantic metadata to make it understandable by machines.
2. Add ownership to data.
3. Distribute data, let it grow, and collect back the results.

Let’s examine how this can be done using WordPress.

## Authoring content in the WordPress admin
Let’s take a post and dissect into atomic chunks which must be annotated. We have the following parts, without trying to be complete:

- Title
- Author
- Date posted
- Excerpt
	- Paragraphs
- Content
	- Paragraphs
	- Images
	- Links
	- Quotes
	- Galleries
	- Audio
	- Video
	- … and so on
- Featured image
	- Image
- Categories and tags
- Type

Excerpt, Content, Featured image together with all contained content blocks should be considered atomic chunks. They should be independent entities forming a post.

For example a Featured image could come from Flickr created by another author. This should be annotated, and the author mentioned if supports (web) mentions.

A paragraph in Content should be quotable, likeable, re-postable, commentable etc. Something like Medium tries to do.

And so on. A post, an article is not a single non-decomposable entity. It is a container of single, atomic elements. Each part of the post, each component should be treated independently.

## Growing content
Distributing annotated content should be done by plugins / services not related to a theme.

In the same way getting feedback on distributed content should be done by other plugins and services not related to this theme.

## Displaying content growth
After content is distributed, syndicated, reverse-syndicated these new entries must be displayed both on the admin, and the front-end interface.

For example, in admin, re-opening an old post should display which paragraphs were liked and how many times, which quotes were reposted, how external authors reacted to using their content in this current article. And so on.

The same meta-information should be presented also on the front-end but in a different way.

While in admin all new content should be displayed centered around a content chunk using the admin dashboard display style, on front-end they should be displayed using different facets and different visual styles.

For example in the main feed after every article a summary of content growth can be displayed; current interactions and reactions can be displayed between articles as a regular feed item; the display should be themeable and configurable; and so on.

## Technology

### Content to data
The only technology I’m aware of capable to convert monolithic content into atomic chunks is Gutenberg. Gutenberg decomposes post content into independent blocks.

This technology is new and not ready for prime time yet. However if one creates her own custom blocks not relying on the official set it can be made to work.

### Annotating data
Right now an IndieWeb block set can be created which can deconstruct monolithic post / page content into annotated blocks.

Another approach would be to make a plugin which equips any kind of block from any provider with annotations. This would be useful in the future to let any block framework join the IndieWeb way. Now it seems to impossible to done.

### Displaying annotated data
Atomic chunks together with their growth have to be displayed both on the admin interface and the front-end.

This can be done with Gutenberg blocks.

### Future compatibility
There are two concepts around IndieWeb which might be not be future compatible.

First it’s not sure the InidieWeb way is the best, and the most popular way, which will gain the support of the masses. I guess IndieWeb was the first community who didn’t give up and wired together a solution though a decade long hard work. Now everybody else is catching up (Mozilla, Mastodon, Diaspora etc.) and it’s time to revise the approach, open up and join forces.

Second is the Headless CMS space. Today no one can expect the platform where you’ve created the content is the same platform which displays it. Even true for WordPress.

For example I’m using WordPress with HardyPress hosting which is a static site generator. Even if I use every plugin IndieWeb offers for WordPress I can’t fully implement IndieWeb features. After I deploy the site it’s just another static website nothing to do with its backend.

In this new scene a classic CMS is divided into two or three parts:

1. Front-end, theming, is fully independent of the back-end.
2. Back-end, the admin interface, is mostly used to create content, in the best possible way, via a handy visual editor, throwing together blocks and components. Its role is this simple task and nothing more.
3. Data layer, which collects all data the front-end needs, from the back-end / visual editor to third parties like Webmentions, MicroPub, and, makes this data available via an API.

Each new layer is a separate industry with its own leaders and technologies. IndieWeb should be aware of these, or better, should keep up with these new technologies.

For example, on front-end React is the clear winner. On backend the race is still open and  WordPress with the new Gutenberg direction probably having chance to emerge along Contentful,  Netlify and Take Shape.

On Data Layer I have no expertise.  

Ideally, a future compatible, easily implementable IndieWeb would look like:

1. A React based, platform independent theme.
2. A WordPress / Gutenberg based set of blocks to annotate any type of content with any standard (Microformats, JSON-LD, or anything which comes up in the future)
3. A set of data servers with public APIs syndicating / federating / managing all interactions with annotated data. Both 1.) and 2.) would rely on it. 
