# htp - HTML Template Processor

_a microframework that dynamically replaces placeholders ({{var}}) in your HTML using URL query parameters_

## Installing

Add the following snippet inside your HTML:
```
<iframe hidden name=htp onload="setTimeout(()=>document.body.innerHTML=document.body.innerHTML.replace(/\{\{(.*?)\}\}/g, (_,k)=>new URL(location).searchParams.get(k)||''))"></iframe>
```
Use placeholders in your HTML:
```
<h1>Welcome, {{name}}!</h1>
<p>Your favorite color is {{color}}.</p>
```
Then pass values using URL parameters:
```
example.com/?name=Bob&color=Green
```

## How It Works
1. The `<iframe>` script finds all {{placeholder}} elements in your HTML.
2. It replaces them with values from the URL query parameters

## Why use `htp`?
* Super lightweight
* Useful for simple dynamic content in static sites


