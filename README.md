# XPath

XPath uses path expressions to select nodes or node-sets in an XML document.

The example demonstrates the use of XPath on a sample XML document. The solutions can be tested using https://www.freeformatter.com/xpath-tester.html

* Select titles of all books.
```
/bookstore/book/title
//title
```

Expected output:
```xml
Element='<title lang="en">Everyday Italian</title>'
Element='<title lang="en">Harry Potter</title>'
Element='<title lang="en">XQuery Kick Start</title>'
Element='<title lang="de">Lernen XML</title>'
```

* Select categories of books.
```
/bookstore/book/@category
```

Expected output:
```xml
Attribute='category=cooking'
Attribute='category=children'
Attribute='category=web'
Attribute='category=web'
```

* Select all prices __elements__.
```
/bookstore/book/price
```

Expected output:
```xml
Element='<price discount="promo">20.00</price>'
Element='<price>30.00</price>'
Element='<price>29.99</price>'
Element='<price discount="promo">30.99</price>'
Element='<price>49.99</price>'
Element='<price>39.95</price>'
```

* Select all price __values__.
```
/bookstore/book/price/text()
```

Expected output:
```xml
Text='20.00'
Text='30.00'
Text='29.99'
Text='30.99'
Text='49.99'
Text='39.95'
```

* Select price nodes of books with a `price>35`.
```
/bookstore/book[price>35]/price
```

Expected output:
```xml
Element='<price discount="promo">30.99</price>'
Element='<price>49.99</price>'
Element='<price>39.95</price>'
```

* Select price nodes with `price>35`.
```
/bookstore/book/price[.>35]
```
Expected output:
```xml
Element='<price>49.99</price>'
Element='<price>39.95</price>'
```

* Select title nodes with `price>35`.
```
/bookstore/book[price>35]/title
```

Expected output:
```xml
Element='<title lang="en">XQuery Kick Start</title>'
Element='<title lang="de">Lernen XML</title>'
```

* Select books that are in the web category.
```
/bookstore/book[@category="web"]
```

Expected output:
```xml
Element='<book category="web">
    <title lang="en">XQuery Kick Start</title>
    <author>James McGovern</author>
    <author>Per Bothner</author>
    <author>Kurt Cagle</author>
    <author>James Linn</author>
    <author>Vaidyanathan Nagarajan</author>
    <year>2003</year>
    <price discount="promo">30.99</price>
    <price>49.99</price>
  </book>'
Element='<book category="web">
    <title lang="de">Lernen XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>'
```

* Select books that are in German - books with the "lang" attribute equals to "de" in the title.
```
/bookstore/book[title/@lang="de"]
```

Expected output:
```xml
Element='<book category="web">
    <title lang="de">Lernen XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>'
```

* Select books published after 2004.
```
/bookstore/book[year>2004]
```

Expected output:
```xml
Element='<book category="cooking">
    <title lang="en">Everyday Italian</title>
    <author>Giada De Laurentiis</author>
    <year>2005</year>
    <price discount="promo">20.00</price>
    <format>hardcover</format>
    <price>30.00</price>
  </book>'
Element='<book category="children">
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>'
```

* Select titles that contain "XML".
```
/bookstore/book/title[contains(text(), "XML")]
```

Expected output:
```xml
Element='<title lang="de">Lernen XML</title>'
```

* Select books with titles that contain "XML".
```
/bookstore/book[title[contains(text(), "XML")]]
```

Expected output:
```xml
Element='<book category="web">
    <title lang="de">Lernen XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>'
```

* Select titles of books with a format element.
```
/bookstore/book[format]/title
```

Expected output:
```xml
Element='<title lang="en">Everyday Italian</title>'
```

* Select titles of books with a discount price due to promotion.
```
/bookstore/book[price/@discount="promo"]
```

Expected output:
```xml
Element='<book category="cooking">
    <title lang="en">Everyday Italian</title>
    <author>Giada De Laurentiis</author>
    <year>2005</year>
    <price discount="promo">20.00</price>
    <format>hardcover</format>
    <price>30.00</price>
  </book>'
Element='<book category="web">
    <title lang="en">XQuery Kick Start</title>
    <author>James McGovern</author>
    <author>Per Bothner</author>
    <author>Kurt Cagle</author>
    <author>James Linn</author>
    <author>Vaidyanathan Nagarajan</author>
    <year>2003</year>
    <price discount="promo">30.99</price>
    <price>49.99</price>
  </book>'
```

## Reference
* https://www.w3schools.com/xml/xml_xpath.asp
* https://www.w3schools.com/xml/xpath_intro.asp
