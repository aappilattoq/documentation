---
layout: default
title: parsejson
categories: [Reference, Functions, parsejson]
published: true
alias: reference-functions-parsejson.html
tags: [reference, io functions, functions, parsejson, json, container]
---

[%CFEngine_function_prototype(json_data)%]

**Description:** Parses JSON data directly from an inlined string and
returns the result as a `data` variable

[%CFEngine_function_attributes(json_data)%]

Please note that because JSON uses double quotes, it's usually most
convenient to use single quotes for the string (CFEngine allows both
types of quotes around a string).

**Example:**

```cf3
    vars:

      "loadthis" 

         data =>  parsejson('{ "key": "value" }');
```

**See also:** `readjson()`, `mergedata()`, and `data` documentation.
