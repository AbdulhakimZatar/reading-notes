# Html

## Process and Design

### Who is the Site For?
Every website should be designed for the
target audience, not just for yourself or the
site owner.

### Why People Visit Your Website?
1- The first attempts to discover the underlying motivations for why visitors come to the site.
2- The second examines the specific goals of the visitors. These are the triggers making them come to the site now.

### Site Maps
* The aim is to create a diagram of the pages that will be used to structure the site. This is known as a site map and it will show how those pages can be grouped.
* The groups of information are then turned into the diagram that is known as the site map.
* A site map will usually begin with the homepage. Additionally, if the site is large and is compartmentalized into sections, each section might require its own section homepage to link to all of the information within it.

![Example](img\ex_sitemap.png)

### WireFrames
Wireframes allow you to organize the information that will need to go on each page.

![Example](img\ex_wireframes.png)

### Designing Navigation
Design is about communication. Visual hierarchy helps visitors understand what you are trying to tell them.


## Structure
* HTML pages are text documents.
* HTML uses tags
* Opening tags can carry attributes.


## HTML5 Layout
HTML5 is introducing a new set of elements that help define the structure of a page.

### New Html5 Layout Elements
HTML5 introduces a new set of elements that allow you to divide up the parts of a page. The names of these elements indicate the kind of content you will find in them. They are still subject to change, but that has not stopped many web page authors using them already

![Example](img\ex_html_layout.png)


## Extra Markup

### The Evolution of HTML
* Html4
* XHtml 1.0
* Html5

### Important things in HTML
* DOCTYPES tell browsers which version of HTML you are using.
* Comment can be added between those 

```<!-- and -->```

* The id and class attributes allow you to identify particular elements.
* The <div> and <span> elements allow you to group block-level and inline elements together.
* <iframes> cut windows into your web pages through which other pages can be displayed.


### Exapmle
```
<!DOCTYPE html PUBLIC
"-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
 <meta name="description" content="Telephone, email
 and directions for The Art Bookshop, London, UK" />
 <title>Contact The Art Bookshop, London UK</title>
</head>
<body>
 <div id="header">
 <h1>The Art Book Shop</h1>
 <ul>
 <li><a href="index.html">home</a></li>
 <li><a href="index.html">new publications</a>
 </li>
 <li class="current-page">
 <a href="index.html">contact</a></li>
 </ul>
 </div><!-- end header -->
 <div id="content">
 <p>Charing Cross Road, London, WC2, UK</p>
 <p><span class="contact">Telephone</span>
 0207 946 0946</p>
 <p><span class="contact">Email</span>
 <a href="mailto:books@example.com">
 books@example.com</a></p>
 <iframe width="425" height="275" frameborder="0"
 scrolling="no" marginheight="0" marginwidth="0"
 src="http://maps.google.co.uk/maps?f=q&amp;
 source=s_q&amp;hl=en&amp;geocode=&amp;
 q=charing+cross+road+london&amp;output=embed">
 </iframe>
 </div><!-- end content -->
 <p>&copy; The Art Bookshop</p>
</body>
</html>
```