# HTML cheatsheet

Tag: ` Used to specify an element in HTML`

Attribute: `Used to specify property of a Tag`

1. `HTML` tag

It is the root element / tag of an HTML document which contains two important tags `head` and `body`

2. `head` tag

It is used to specify meta tags which will be used for search engine to search for keywords and overviews the contents in search engine. It is also used to specify title tag which will be displayed in the website's tab-name. Meta tags also specify some information such as character encoding, device width, Linking CSS files or writing inline CSS.

EX:

```HTML
    <head>
        <title>Title of the document</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="keywords" content="description HTML, JS, CSS">

    </head>
```

3. `body` tag

The actual contents of the page goes here.

```HTML
    <body>
        Contents of the page
    </body>
```

The rest of the tags metioned after body tag in this documentation belongs inside body tag

4. `p` tag

`p` tag abbreviates to `paragraph` tag.
It is used to specify paragraph contents inside this tag

EX:

```HTML
    <p>
        This is a paragraph
    </p>
```

5. `h{n}` tag

`h{n}` tag represents Heading tag where n is integer from 1 to 6.
The text written in heading tag will be of higher font size and in bold text.
Greater the value of 'n' smaller the text element is.

EX:

```HTML
    <h1> Highest font-size </h1>

    <h3> Moderate font-size </h3>

    <h6> Smaller font-size </h6>
```

