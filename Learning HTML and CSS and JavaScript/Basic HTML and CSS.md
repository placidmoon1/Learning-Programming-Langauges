#Basic HTML and CSS 
> Version HTML5 & CSS3 

## Table of Contents: 

  1. [HTML Headers and Paragraphs](#headers-and-paragraphs)
  2. [HTML Commenting](#Commenting)
  3. [Different types of Styling](#different-types-of-styling)

## HTML5 Syntax
  
### Headers and Paragraphs:

In HTML headers as well as most HTML elements, are expressed through an opening tag and closed tag. 
Normally, h1 to h6 elements are used where h1 is the largest and h6 in the smallest header size. The size of headers depend on browser type (i.e. Chrome, IE, FireFox). Headers should be apprporiate for the target platform and should be responsive to change in size of the website. A paragraph element (similar to a h6 header) can be defined by a `<p>` opening and `</p>` closing tag. 

The recommeneded emphasis `<em>` on each headers are: 
`
h1 { font-size: 2em; }
h2 { font-size: 1.5em; }
h3 { font-size: 1.17em; }
h4 { font-size: 1.12em; }
h5 { font-size: .83em; }
h6 { font-size: .75em; }
`
Example of a header is: 

```
<h1> Hello World! </h1>
```

### Commenting 
Commenting in HTML is initiated by a `<!--` and closed by a `-->` 

### Different types of style
Elements of HTML can be changed by altered through CSS (Cascading Style Sheets) in three ways: **In-line** style (adding the style attribute in HTML elements, **Internal** style (by adding a `<style>` element tag in the `<head>` section of the HTML file) or **External** style (by using an external CSS file). 

Example of Internal Style (i.e. inline CSS):
```html
<h1 style="color:blue">This is a Blue Heading</h1>
```

Example of 
