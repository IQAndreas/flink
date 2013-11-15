
Generate little favicons next to your links (FaviconLINKs). This page includes several examples (which can't be rendered in a standard readme); to see the output, see the following page:

* <http://www.iqandreas.com/flink/examples/>

#### Usage

In the repository, you will find a `stylesheets` directory. The `main.css` file is required, but after that you can pick and choose from which sites you will actually be using (the less CSS you include, the faster your site will load, which may or not be an issue with todays internet speeds). If you want to include the favicon information for all known sites, you can use `all.css` instead of having to link to each available CSS file individually.

If you want to add your own sites, follow the patterns used in the existing CSS.

To add a favicon to a `li` element, use the `flink` class followed by the name of the site with underscores instead of periods (CSS doesn't play well when there are periods in the class names). For example, if you want the favicon for `gaming.stackexchange.com`, use the class name `gaming_stackexchange_com`.

Here is some example HTML code _(note the class is on the list item, and not on the link)_:

```html
<li class="flink gaming_stackexchange_com"><a href="http://gaming.stackexchange.com/a/123883/17179">MineCraft: Is there a way to keep Zombie Pigmen off of minecart tracks?</a></li>
```

A second example which shows that you don't actually need the `li` to contain a link in order to display a favicon:

```html
Our business uses the following social media sites:
<ul>
	<li class="flink youtube_com">FooProductions</li>
	<li class="flink facebook_com">FooFanpage</li>
	<li class="flink google_com">FooProductions+</li>
	<li class="flink skype_com">BobFoomaker</li>
</ul>
```

#### Other files

If you use [Jekyll](http://jekyllrb.com/), you can save typing by taking advantage of the files in `includes` and `plugins` to make generating these links easier.

The file `includes/flink` should be placed in your Jekyll site's `_includes` directory, and is used as follows (you can put the parameters in any order you want):

```
{% include flink site="twitter.com" title="Twitter: Unicode Unsortium" url="https://twitter.com/FakeUnicode" %}
```

The Jekyll plugin in `plugins/flink.rb` should be placed in your Jekyll site's `_plugins` directory, and adds the `flink` tag. Unlike the `includes` file, it will automatically parse out the `site` property from the URL. Use it as follows (here the order of the parameters is important!):

```
{% flink http://www.youtube.com/watch?v=Bt9zSfinwFA "Vertical Video Syndrome - A PSA" %}
```

Note that [GitHub Pages](http://pages.github.com/) does not allow outside plugins, so if you use `flink.rb` in your Jekyll project, you will need to build your site before uploading it to GitHub.

#### Future plans

First, I would like to add more websites; for now, I'm just adding sites whenever the need arises for me. But eventually, those CSS lists may get very long, and a different way of finding the icons will be needed.

It is possible to [achieve this effect with JavaScript](http://askthecssguy.com/articles/hyperlink-cues-with-favicons/), but I would prefer a CSS-only solution for now, and then I'll add a JavaScript version as an alternative.

It is also possible to [use CSS selectors](http://askthecssguy.com/articles/showing-hyperlink-cues-with-css/) as an easier way of finding the originating site (the current method isn't pretty). This seems like a great idea, but I will wait to add it officially until I have read up more on how to use selectors (but pull requests are warmly welcome).

