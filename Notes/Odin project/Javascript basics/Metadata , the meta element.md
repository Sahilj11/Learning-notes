### Specifying your document character encoding
- In the example we saw above, this line was included:

```
<meta charset="utf-8" />
```
- This element specifies the document's character encoding — the character set that the document is permitted to use. `utf-8` is a universal character set that includes pretty much any character from any human language. This means that your web page will be able to handle displaying any language; it's therefore a good idea to set this on every web page you create! For example, your page could handle English and Japanese just fine
- If you set your character encoding to `ISO-8859-1`, for example (the character set for the Latin alphabet), your page rendering may appear all messed up

### Adding an author and description 
- Many `<meta>` elements include `name` and `content` attributes:
- `name` specifies the type of meta element it is; what type of information it contains.
- `content` specifies the actual meta content.
- Two such meta elements that are useful to include on your page define the author of the page, and provide a concise description of the page.

### Other types of metadata
- As you travel around the web, you'll find other types of metadata, too. A lot of the features you'll see on websites are proprietary creations, designed to provide certain sites (such as social networking sites) with specific pieces of information they can use.
- For example, Open Graph Data is a metadata protocol that Facebook invented to provide richer metadata for websites. In the MDN Web Docs sourcecode, you'll find this
```
<meta
  property="og:image"
  content="https://developer.mozilla.org/mdn-social-share.png" />
<meta
  property="og:description"
  content="The Mozilla Developer Network (MDN) provides
information about Open Web technologies including HTML, CSS, and APIs for both websites
and HTML Apps." />
<meta property="og:title" content="Mozilla Developer Network" />
```
- One effect of this is that when you link to MDN Web Docs on Facebook, the link appears along with an image and description: a richer experience for users.
more on https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#applying_css_and_javascript_to_html

