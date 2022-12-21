# Public Interest Tech Webring

The **Public Interest Tech Webring** is a collection of blogs dedicated to civic tech, public interest tech, government tech policy, and similar topics.  You can [view all of the members on the main page](https://pitwebring.billhunt.dev/).

## Joining

### Criteria

You may request your site to be added to the webring if it meets the following criteria:

* The majority of the content must be relevant to the topics listed above.

* The site must be a personal site, not for a business. If you've got your own consulting company or a book, that's ok.

* The primary content must be free and accessible. You may not require a user to login, create an account, or pay to view your posts.

* We strongly recommend you have a working RSS feed of your posts that's discoverable (`link` tag in the head or similar).

* You must display the webring banner on your blog, preferably in the header or footer of each page.

### How to Join

To join the webring, please open a request to add a new site through GitHub issues.

After you're approved, check out the Join page on the main website to get your webring code snippet.


## This Repo

This repo contains both the Jekyll page for the webring website itself, as well as the following files which are used to serve the webring to member sites:

* [list.json](list.json) - The list of member sites.
* [webring.js](webring.js) - The main JavaScript file for showing the webring.
* [webring.html](webring.html) - A static html page used for redirects when the JavaScript file can't be used on a webpage.
