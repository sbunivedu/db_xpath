# XPath

XPath uses path expressions to select nodes or node-sets in an XML document.

The example demonstrates the use of XPath on a sample XML document. The solutions can be tested using https://www.freeformatter.com/xpath-tester.html 

* Select titles of all books.
```
/bookstore/book/title
```

* Select categories of books.
```
/bookstore/book/@category
```

* Select all the prices.
```
/bookstore/book/price[text()]
```

* Select price nodes with price>35.
```
/bookstore/book[price>35]/price
```

* Select title nodes with price>35.
```
/bookstore/book[price>35]/title
```

* Select books that are in the web category.
```
/bookstore/book[@category="web"]
```

* Select books that are in German (de).
```
/bookstore/book[title/@lang="de"]
```

* Select books published after 2004.
```
/bookstore/book[year>2004]
```

* Select titles that contain "XML".
```
/bookstore/book/title[contains(text(), "XML")]
```

* Select books with titles that contain "XML".
```
/bookstore/book[title[contains(text(), "XML")]]
```

* Select titles of books with a format element.
```
/bookstore/book[format]/title
```

* Select titles of books with a discount price due to promotion.
```
/bookstore/book[price/@discount="promo"]
```

## Reference
* https://www.w3schools.com/xml/xml_xpath.asp
* https://www.w3schools.com/xml/xpath_intro.asp
