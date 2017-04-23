# Reading API documentation

Now we're ready to start making API requests! To do that, let's look at Wikipedia's API documentation.![](/assets/Screen Shot 2017-04-04 at 12.46.33 AM.png)

Here's a screenshot of [https://www.mediawiki.org/wiki/API:Main\_page](https://www.mediawiki.org/wiki/API:Main_page), the homepage for Wikipedia's API \(it's also the API used by WikiHow and other MediaWiki projects\). Often, the homepage of an API's documentation will provide a deep overview of how the API is structured and the kinds of requests included in it. It's very useful information but not something you need to read through at the moment. The one thing on the homepage I'd like to focus on briefly is the section about the **endpoint**:

![](/assets/Screen Shot 2017-04-04 at 12.55.59 AM.png)

"Endpoint" is a term you'll see in most API documentation which just means the url you'll be using to do the thing being described. This means that all requests using the Wikipedia API will look like `https://en.wikipedia.org/w/api.php[whatever else is going on in our request].` Keep that in mind since all the other pages in this documentation won't refer to the base URL, and will just tell you what to add to it.

Next, we're going to look at the page that describes how to request random articles. I found [https://www.mediawiki.org/wiki/API:Random](https://www.mediawiki.org/wiki/API:Random) by googling "wikipedia api random," but you could also use the MediaWiki API search box.

This page tells us everything we need to know to request random articles from the API. There are 4 optional parameters, rnlimit, rnnamespace, rnredirect, and rnfilterredir. We'll only be using **rnnamespace** in this tutorial. We will set it to 0, so we only get articles, as opposed to pages like user profiles and discussions about articles.

Looking at the example provided, we can see that the base url is unchanged. The only necessary addition is adding the parameters `action=query`, `list=random`, and `rnnamespace=0`.
![](/assets/Screen Shot 2017-04-04 at 1.00.25 AM.png)


 



