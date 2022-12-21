---
layout: page
title: Join
permalink: /join/
---
<p>
  {{ site.description }}
</p>
<p>
  If you post about the topics above, we'd love for you to join our webring! We do ask that you meet the following requirements:
</p>
<ul class="requirements">
  <li>
    The site must be a personal site, not for a business. If you’ve got your own consulting company or a book, that’s ok.
  </li>
  <li>
    The primary content must be free and accessible. You may not require a user to login, create an account, or pay to view your posts.
  </li>
  <li>
    You must display the webring banner on your blog, preferably in the header or footer of each page.
  </li>
</ul>
<p>
  Additionally, we strongly recommend that your blog have an RSS feed. If it does, we'll include it in our <a href="/feeds.opml">OPML file</a> and include your content in our recent posts list.
</p>
<p>
  To join the webring, please <a class="button" href="https://github.com/{{ site.repository }}/issues/new/choose">open a request</a> to add a new site through GitHub issues.
</p>
<p>
  After you’re approved, you’ll need to add the webring code to your website:
</p>

<h3>For Self-Hosted Websites</h3>
<p>
  You can show the webring on your site by pasting the following html snippet wherever you want it to appear:
</p>

<textarea class="code-snippet"><script src="{{ 'webring.js' | absolute_url }}"></script>
<script>showWebring(true);</script></textarea>

<p>
  If you'd like to disable the default styles, you can use this snippet instead:
</p>

<textarea class="code-snippet"><script src="{{ 'webring.js' | absolute_url }}"></script>
<script>showWebring();</script></textarea>

<h3>For Hosted Blogs</h3>

<p>
  If you're using a service to host your blog which does not allow JavaScript, you can use a static version instead, either on your bio and/or posts. Use the generator below to generate the html for your page:
</p>

<form id="webring-generator" class="webring-form">
  <fieldset class="form-group">
    <label for="website">Your Website:</label>
    <input id="website" class="webring-input form-control" name="website" placeholder="https://example.com/"/>
  </fieldset>
  <fieldset class="form-check form-group">
    <input type="radio" class="webring-input webring-type form-check-input" id="type-full" name="webring-type" value="full" checked/><label for="type-full" class="form-check-label">Full Banner</label><br>
    <input type="radio" class="webring-input webring-type form-check-input" id="type-short" name="webring-type" value="short"/><label for="type-short" class="form-check-label">Short Banner</label>
  </fieldset>
  <p>
    Get your code:
  </p>
  <textarea class="webring-html" id="webring-html"></textarea>
  <p>
    How it will appear:
  </p>
  <div class="webring-generated" id="webring-generated"></div>
</form>



<script>
  function updateCode(e) {
    console.log('update', e);
    if(e) e.preventDefault();

    let codeType = document.querySelector('input[name="webring-type"]:checked').value;
    let website = encodeURIComponent(document.getElementById('website').value);

    let code = `<a href="{{ '/redirect' | absolute_url }}?dir=prev&from=${website}">&larr;</a> &#124; <a href="{{ '/' | absolute_url }}">{{ site.title }}</a> &#124;  <a href="{{ '/redirect' | absolute_url }}?from=${website}">&rarr;</a>`;

    if(codeType == 'full') {
      code = `This blog is part of the <a href="{{ '/' | absolute_url }}">{{ site.title }}</a>. &#124; <a href="{{ '/redirect' | absolute_url }}?dir=prev&from=${website}">Previous Site</a> &#124;
    <a href="{{ '/redirect' | absolute_url }}?from=${website}">Next Site</a>`;
    }

    document.getElementById('webring-html').innerHTML = '';
    document.getElementById('webring-html').appendChild(document.createTextNode('  '+code));

    document.getElementById('webring-generated').innerHTML = code;

    return false;
  }
  updateCode();

  document.getElementById('webring-generator').addEventListener('submit', updateCode, true);

  const inputs = document.querySelectorAll('.webring-input');
  for(let i = 0; i < inputs.length; i++) {
    inputs[i].addEventListener('change', updateCode, true);
  }
</script>