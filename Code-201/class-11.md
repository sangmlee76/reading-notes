# Read 11 - Study Guide: Assorted Topics (Images and Practical Information)

## CSS Images (HTML/CSS: Ch 16, p.406-427)
+ Image size can be controlled using the _________ and __________ properties, just like any other box in CSS.
  - Image size quick reference:
    - small portrait: 220 x 360
    - small landscape: 330 x 210
    - feature photo: 620 x 400

+ **Aligning images**: web page authors are increasingly using `float` property to align images. This is implemented in 2 ways:
  - the `float` property is added to the `class that was created to represent the _______ of the image.
  - the new classes are created with name such as _______ or _______ to align the images on the page.
  - it is also common to add a _______ to ensure the text does not touch the image.

+ **Centering images**: by default images are inline elements. In order to turn them into a _______-level element (so that they can be centered), use the `display` property with a value of ________. Two common ways to horizontally center an image are:
  - use the `text-align` property with a value of ________ on the containging element.
  - set the ________ values on the image itself with left and right values to *auto*.
  - you can also use class names to allow elements to be centered

+ **Background images**: the `background-image` property allows an image to be placed behind any HTML element.
  -  the background images are often the last thing on the page to load. The size of the image will affect webpage load time

  ```
  body{
    background-image: url("img/pattern.jpg");
  }
  ```
  
+ **Repeating images**: the `background-repeat` can have four values: `repeat`, `repeat-x`, `repeat-y`, and `no-repeat`:
  - _______ the image repeats both horizontally and vertically and is the default if `background-repeat` isn't used
  - _______ the image repeats horizontally only
  - _______ the image repeats vertically only
  - _______ the image is shown only once
  - the `background-attachment` property specifies whether a background image should stay in one position or move as the user scrolls up and down the page.
    - ________ background image stays in the same position on the page.
    - the background image moves upa nd down as the user scrolls.

+ **Background position**: when an image is not being repeated you can use the `background-position` property to specify the location of the image in the browser window. It uses a pair value to specify a horizontal and a vertical position **(in that order)**. The vertical value will default to *center* if not specified.

```
background-position: [horizontal value] [vertical value];

horizontal values: left, center, right
vertical values: top, center, bottom
```

+ **Shorthand**: the `background` property acts like a shorthand for all of the backgournd properties. The order must be as follows:
  1. background-color
  2. background-image
  3. background-repeat
  4. background-attachment
  5. background-position

+ **Image rollovers and sprites**: See p.417 for details  
+ **Gradients**: See p.419 for details  
+ **Contrast of background images**: See p.420 for details  

****

## Practical Information (HTML/CSS: Ch 19, p476 - 492)

### Search engine optimization (SEO):
The practice of trying to help your site appear nearer the top of search engine results. Two main concepts that optimize SEO: _________ used for the search and relevant ____________ to your site. These split into two techniques: **on-page** and **off-page**
- **On-page techniques**:
  - keywords must be in the HTML code
  - ensure images have appropriate text in the `alt` attribute
  - there are **seven** essential places to place the keywords:
    1. page title - it is specified in the `<title>` inside the `<head>`
    2. url/web address - use _________ in the file name
    3. headings - in the `<h*n*>` element
    4. text - repeat __________ in the main body at least 2-3 times
    5. link text - use _________ in the text that create links between pages rather than a generic *'click here'*
    6. image alt text - provide accurate description
    7. page description - use `<meta>` tag inside the `<head>` element
  - Note: do **NOT** try to 'fool' the search engine (e.g. placing hidden words in the background of the page) -- the search engine will penalize you for it.
- **Off-page techniques**:
  - search engines are looking for other sites whose content is related to yours
  - they are looking at the quantity of other **relevant** sites that link to your site
  - look at the words between `<a> </a>` - it should contain _________.
  - The words that appear in the link should also appear in the body of the page to which it is linked.

### Keyword and phrase identification
Using the right ________ on your site is one of the hardest tasks; take time to do this well by using the following steps:
  1. **brainstorm**: make a broad list of possible terms that can be used for the search
  2. **organize**: group words into differnt section or categories of your website. For larger sites, use subcategories
  3. **researc**: use tools such as *adwords.google.com/select/KeywordToolExternal* (when using this, select the *exact match* option rather than 'broad match')
  4. **compare**: the more sites out there that have already been optimized for a given ___________, the harder it will be for you to appear at the top of search results. Use Google's advanced search feature to just search the titles of web pages to gauge competition
  5. **refine**: look for other words that could be incorporated into a phrase (e.g. consider geographic location and other specifying/differentiating information that would set you apart). If there is a phrase that is relevant but competitive, **do** still use it.
  6. **map**: select 3-5 __________ or phrases that map to each page of your website and use these for each page. They do not have to repeat on each page and as you get farther away from the main page, use _______ that are more specific to the individual topic page.

### Web-page analtyics
One of the best tools to use is **Google Analytics**; will need to sign up for an account at: www.google.com/analytics. Use the tracking code provided by Google Analytics and put it inside your `<head>` element

### Google Analytics deep dive

+ **Site visit analysis**: how many people are coming to your site? It's the **overview page** info from the dashboard 
  - **visits**: the number of times people have come to your site. Session duration is 30 min (e.g. if someone is inactive for 30 minutes and then looks at another page on your site, this gets counted as a **new** visit)
  - **unique visits**: total number of people who have visited your site over the specified period. Should be lower than number of visits if you have a lot of revisits
  - **page views**: total number of pages all visitors have viewed on your site
  - **pages per visit**: average number of pages each visitor has looked at on your site *per visit*
  - **average time on site**: the average number of pages each user has spent on the site *per visit*
  - **date selector**: the time period to review the analysis; default is prior month
  - **export**: allows exporting of the statistic for off-line analysis (e.g. Excel)
  
+ **Site interaction analysis**: what are they doing on your site? Accessed via the **content** link option from menu
  - **pages**: which pages your visitors are looking at the most and also which pages they are spending the most time on
  - **landing pages**: the pages that people arrive on when first visiting your site. Users are not always coming via your homepage.
  - **top exit pages**: which pages people most commonly leave from.
  - **bounce rate**: the number of popel who left on the same page that they arrived on. A high bounce rate suggests that the content is not what they were looking for or that the content was not engaging. Bounces are counted on:
    - clicked a link to another site
    - clicked on an ad
    - entered a new URL
    - used the `back` button
    - closed the browser

+ **Site arrival analysis**: where are they coming from? Accessd via **traffic sources** link option from menu
  - **referrers**: the sites that have linked to your and the number of people who have come via those sites.
  - **direct**: which page a user arived on if they did not come via a link on another site. They may have typed the URL, used a browser bookmark, or clicked a link in an e-mail, PDF, or Word doc.
  - **search terms**: the terms users entered into a search engine to find your site. It can help you fine tune your SEO keywords.
  - **advanced features**: Google Analytics also offers e-commerce tracking (e.g. products sold, avg basket size, etc.). You can also specify the paths you want people to take, and then see how far they get through those paths (e.g. useful for gathering data from users).

### Domain Names and Hosting (p.487)
In order to put your site on the web you will need a domain name and web hosting

+ **Domain names** are your web address. There are many websites that allow you to register your domain name. Will have to pay an annual fee to keep the domain name.

+ **Web hosting** provides web servers onto which you will upload your site. Web servers are constantly connected to the internet and specialized to serve web pages when requested.
  - with exception of very large site, most websites live on web servers run by web hosting companies (far cheaper and more reliable than running your own web servers).
  - Some criteria to consider when choosing a web host:
    - **disk space**: total size of the files (HTML, CSS, img, scripts, etc.)
    - **bandwidth**: the amount of data the  hosting company will send to your site's visitors. For example, if 10 people looked at every page on your site, this would be equivalent to 10 times the amount of disk space used.
    - **backups**: check to ensure the hosting company performs backups on your site (and the frequency).
    - **email accounts**: most hosting companies will provide email servers with their hosting package. Check the size of the mailbox you are allowed and the number of mailboxes you can use.
    - **server-side languages and databases**: be sure that the hosting company supports the technologies your software needs to run.

### FTP and third party tools
A **file transfer protocol (FTP)** is used to transfer your code and images from your computer to your hosting company.
+ Some companies offer web browser tools but FTPs are faster at transmitting files
+ Popular FTP apps:
  - FireZilla (firezilla-project.org) for Win, Mac, Lin
  - FireFTP (fireftp.mozdev.org) for Win, Mac, Lin
  - CuteFTP (cuteftp.com) for Win, Mac
  - SmartFTP (smartftp.com) for Win
  - Transmit (panic.com/transmit) for Mac
+ Popular third party tools by category (see p.490 for details)
  - Blogs
  - E-commerce
  - Email-newsletter
  - Social Networking sharing buttons

## Article: [(MDN) Audio and Video Elements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
+ The `<video>` and `<audio>` elements allow us to embed video and audio into web pages
```
<video controls>
  <source src="video1.mp4" type="video/mp4>
  <source src="video2.webm" type="video/webm">
</video>
```
  - Note: the `controls` attribute enables a default set of playback control.

### HTMLMediaElement API
+ The `HTMLMediaElement` Api provides features that allow you to control video and audio players programmatically. This is available for both `<audio>` and `<video>`

+ Access all the example files at this repo: [mdn/learning-area](https://github.com/mdn/learning-area)

****
## Flash (HTML/CSS: Ch 9, p.201-206; skim/bookmark since Flash is no longer supported)


*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)