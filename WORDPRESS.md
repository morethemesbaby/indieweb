# IndieWeb for WordPress

To sum up, IndieWeb does the following:

1. Converts monolithic, human-only understandable content into atomic chunks equipped with semantic metadata to make it understandable by machines.
2. Adds ownership to data.
3. Distributes data to grow elsewhere and collects back the results.

With the current IndieWeb for WordPress implementation we can achieve the above tasks in a way which is not always fully complete, and far from being future proof.

In the next sections a better approach is suggested.

## Decomposing content

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

A Featured image could come from Flickr created by another author. This should be annotated, and the author mentioned if supports (web) mentions.

A paragraph in Content should be quotable, likeable, re-postable, commentable etc. Something like Medium tries to do.

And so on.

Currently in WordPress a post, an article is a single non-decomposable entity. Instead it should be a container of multiple atomic elements. Each content chunk making up a post should be treated independently.

Advanced Custom Fields is a way to decompose a post into atomic chunks. And Gutenberg is another which decomposes the post on the back-end but displays as a whole on the front-end.

Gutenberg is [not ready yet for prime-time](https://morethemes.baby/2018/11/14/playing-with-gutenberg-and-react/) and there is a Gutenberg version of Advanced Custom Fields is coming.

With a combination of these technologies we can say content can be decomposed into atomic chunks in WordPress.

## Annotating data

Once we have a proper technology to decompose content we can extend it to support annotation. Perhaps any kind of annotation not just Microformats 2.

## Growing content

Distributing annotated content should be done by plugins / services not related to a theme / this case study.

In the same way getting feedback on distributed content should be done by other plugins and services not related to this theme.

## Displaying content growth

After content is distributed, syndicated, reverse-syndicated these new entries must be displayed both on the admin, and the front-end interface.

For example, in admin, re-opening an old post should display which paragraphs were liked and how many times, which quotes were reposted, how external authors reacted to using their content in this current article. And so on.

The same meta-information should be presented also on the front-end but in a different way.

While in admin all new content should be displayed centered around a content chunk using the admin dashboard display style, on front-end they should be displayed using different facets and different visual styles.

For example in the main feed after every article a summary of content growth can be displayed; current interactions and reactions can be displayed between articles as a regular feed item; the display should be themeable and configurable; a special section should be created for comments, likes; or another with referenced authors and sources. And more.

### Future compatibility

There are two concepts around IndieWeb which might be not be future compatible.

First it’s not sure the InidieWeb way is the best, and the most popular way, which will gain the support of the masses.

I guess IndieWeb was the first community who didn’t give up and wired together a solution through a decade long hard work. Now everybody else is catching up (Mozilla, Mastodon, Diaspora etc.) and it’s time to revise the approach, open up and join forces.

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
2. A WordPress / Gutenberg / ACF  based set of blocks to annotate any type of content with any standard (Microformats, JSON-LD, or anything which comes up in the future)
3. A set of data servers with public APIs syndicating / federating / managing all interactions with annotated data. Both 1.) and 2.) would rely on it.
