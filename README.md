# Civic Tech Webring

The **Civic Tech Webring** is a collection of blogs dedicated to civic tech, public interest tech, government tech policy, and similar topics.  You can [view all of the members on the main page](https://billhunt.dev/civic-tech-webring/).

## Joining

### Criteria

You may request your site to be added to the webring if it meets the following criteria:

* The majority of the content must be relevant to the topics listed above.

* The site must be a personal site, not for a business. If you've got your own consulting company or a book, that's ok.

* The primary content must be free and accessible. You may not require a user to login, create an account, or pay to view your posts.

* Your site must have a working RSS feed of your posts that's discoverable (`link` tag in the head or similar).

* You must display the webring banner on your blog, preferably in the header or footer of each page.

### How to Join

To join the webring, please [open a request to add a new site through GitHub issues](https://github.com/krusynth/civic-tech-webring/issues/new/choose).

### Adding the Code
You can show the webring on your site by pasting the following html snippet wherever you want it to appear:

```
  <script src="https://static.billhunt.dev/civictech/webring.js"></script>
  <script>showWebring(true);</script>
```

If you'd like to disable the default styles, you can use this snippet instead:

```
  <script src="https://static.billhunt.dev/civictech/webring.js"></script>
  <script>showWebring();</script>
```

(You can, of course, also [download the `webring.js` file from GitHub](https://github.com/krusynth/civic-tech-webring/blob/main/webring.js) and host it yourself, but it'll be up to you to keep this file up-to-date as changes are made!)
