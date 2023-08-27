## What is XML
XML (Extensible Markup Language) is a markup language designed to store and transport data in a structured format. It is a text-based format that uses tags to define elements and attributes to describe the data.

Here are some key points about XML:

1. Structure: XML documents consist of hierarchical structures where elements are nested within each other, forming a tree-like structure. Each element is enclosed in opening and closing tags, such as `<element>...</element>`.

2. Tags: XML tags define the structure and meaning of the data. Tags can have attributes, which provide additional information about the element. For example:
   ```xml
   <person id="123">
     <name>John Doe</name>
     <age>30</age>
   </person>
   ```
   In the example above, `<person>`, `<name>`, and `<age>` are tags, while `id` is an attribute.

3. Data representation: XML can represent a wide variety of data types, including text, numbers, dates, and more. Data can be stored as the content of an element or as attribute values.

4. Extensibility: XML is designed to be easily extensible and customizable. Users can define their own tags and structure, tailoring XML to specific needs.

5. Platform independence: XML is a platform-independent format, meaning it can be read and processed by various software applications on different platforms.

6. Data exchange: XML is commonly used for data interchange between different systems, as it provides a standardized and self-describing format that can be understood by multiple applications.

7. Standards and technologies: XML serves as the foundation for various other technologies, such as XPath, XSLT, XML Schema, and SOAP, which enable data manipulation, transformation, validation, and communication.

Overall, XML provides a flexible and widely supported means of representing structured data. It is often used in web services, data storage, configuration files, and other scenarios where structured data needs to be exchanged, shared, or stored in a portable and interoperable format.
- HTML: HTML is primarily focused on defining the structure and presentation of web content. It is designed for creating web pages and includes predefined tags and attributes for elements like headings, paragraphs, links, images, tables, forms, and more.
- XML: XML, on the other hand, is a general-purpose markup language designed to store and transport structured data. It is more flexible and allows users to define their own tags and document structures based on their specific needs. XML is commonly used for data interchange, configuration files, data storage, and other applications where structured data needs to be represented.
## Anatomy of SVG

#### xmlns
The `xmlns` attribute in HTML (as well as in XML) stands for "XML Namespace." It is used to define and differentiate between different sets of elements and attributes within an XML or HTML document.
namespace turn local names into globally unique

Here's a simple explanation of how `xmlns` works:

- XML (including HTML) allows the use of different markup languages or vocabularies to describe elements and attributes. These languages might define their own set of elements and attributes with specific meanings and rules.

- To avoid conflicts between different languages or vocabularies used within the same document, the `xmlns` attribute is used to assign a unique namespace to each set of elements and attributes.

- The `xmlns` attribute is typically added to the root element of the XML or HTML document. It is written as `xmlns="namespace_URI"`, where "namespace_URI" is a unique identifier for the namespace.

- By assigning a namespace to a set of elements and attributes, it ensures that the parser or processor can correctly interpret and handle the elements and attributes based on their intended meanings and rules defined by that namespace.

- Namespaces are often used when integrating different XML-based technologies, such as combining HTML with other XML dialects (like XHTML, SVG, MathML) or when using custom XML vocabularies.

To summarize, the `xmlns` attribute allows different sets of elements and attributes to coexist within an XML or HTML document without causing conflicts. It provides a way to differentiate and interpret elements and attributes based on their associated namespaces, ensuring proper processing and understanding by parsers and processors.

#### Declaring Namespaces
So what do these namespace declarations look like, and where do they go? Here is a short example.

```
<svg xmlns="http://www.w3.org/2000/svg">
  <!-- more tags here -->
</svg>
```

The namespace declaration is provided by the `xmlns` parameter. This parameter says that the `<svg>` element and its child elements belong to whichever XML dialect has the namespace name `http://www.w3.org/2000/svg` which is, of course, SVG. Note that the namespace declaration only needs to be provided once on a root element. The declaration defines the _default_ namespace, so the user agent knows that all the `<svg>` element's descendants also belong to the same namespace. User agents check to see if they recognize the namespace name to determine if they know how to handle the markup.

Note that namespace names are just strings, so the fact that the SVG namespace name also looks like a URI isn't important. URIs are commonly used because they are unique, the intention is not to "link" somewhere. (In fact URIs are used so frequently that the term "namespace URI" is commonly used instead of "namespace name".)

#### Redeclaring namespace
So if all the descendants of the root element are also defined to be in the default namespace, how do you mix in content from another namespace? Easy. You just redefine the default namespace. Here's a short example.

```
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
  <body>
    <!-- some XHTML tags here -->
    <svg xmlns="http://www.w3.org/2000/svg" width="300px" height="200px">
      <!-- some SVG tags here -->
    </svg>
    <!-- some XHTML tags here -->
  </body>
</html>
```

In this example the `xmlns` parameter on the root `<html>` element declares the default namespace to be XHTML. As a result, it and all its child elements are interpreted by the user agent as belonging to XHTML, except for the `<svg>` element. The `<svg>` element has its own `xmlns` parameter, and by redeclaring the default namespace, this tells the user agent that the `<svg>` element and its descendants (unless they also redeclare the default namespace) belong to SVG.

See, namespaces really aren't that hard.

#### Declaring namespace prefix
XML dialects not only define their own elements, but also their own parameters. By default, parameters don't have a namespace at all, and are only known to be unique because they appear on an element that itself has a unique name. However, sometimes it is necessary to define parameters so that they can be reused on many different elements and still be considered to be the same parameter, independently of the element with which they are used. A very good example of this is the `href` parameter defined by the XLink specification. This parameter is commonly used by other XML dialects as a means to link to external resources. But how do you tell the user agent which dialect the parameter belongs to, in this case XLink? Consider the following example.

```
<svg
  xmlns="http://www.w3.org/2000/svg"
  xmlns:xlink="http://www.w3.org/1999/xlink">
  <script xlink:href="cool-script.js" type="text/ecmascript" />
</svg>
```

This example has the rather unusual looking parameter `xmlns:xlink`. As you may guess from the first 'xmlns' part, this is another namespace declaration. However, instead of setting the default namespace, this namespace declaration sets the namespace for something called a "namespace prefix". In this case, we have chosen to use the prefix `xlink` (the second part) since the prefix will be used to tell the user agent about attributes that belong to XLink.

As their name suggests, namespace prefixes are used to prefix parameter and element names. This is done by putting the namespace prefix and a colon before the parameter name as shown on the `<script>` element in the example above. This tells the user agent that the particular parameter belongs to the namespace assigned to the namespace prefix (XLink), and is a parameter that can be used with the same meaning on other elements.

Note that it is an XML error to use a prefix that hasn't been bound to a namespace name. The binding created by the `xmlns:xlink` parameter in the example above is absolutely essential for the `xlink:href` parameter to not cause an error. This XLink parameter is also frequently used in SVG on the `<a>`, `<use>` and `<image>` elements among others, so it's a good idea to always include the XLink declaration in your documents.

As an aside, it's useful to know that namespace prefixes can also be used for element names. This tells the user agent that the particular element (but not its children this time!) belongs to the namespace assigned to the prefix. Knowing this will save you some confusion if you come across markup like in the following example:

```
<html
  lang="en"
  xmlns="http://www.w3.org/1999/xhtml"
  xmlns:svg="http://www.w3.org/2000/svg">
  <body>
    <h1>SVG embedded inline in XHTML</h1>
    <svg:svg width="300px" height="200px">
      <svg:circle cx="150" cy="100" r="50" fill="#ff0000" />
    </svg:svg>
  </body>
</html>
```

Note that because a namespace prefix is used for the `<svg:svg>` element and its child `<svg:circle>`, it wasn't necessary to redeclare the default namespace. In general though it is better to redeclare the default namespace rather than prefix lots of elements in this way.

namespace with scripting https://developer.mozilla.org/en-US/docs/Web/SVG/Namespaces_Crash_Course#scripting_in_namespaced_xml
