---
layout: api
title: Streams
icon: fa-ellipsis-h
group: api-io
---

Streams
===

Streams module provides classes and utilities for working with streams.

- Module: **api/io/streams**
- Definition: [/core_api/issues/34](https://github.com/dirigiblelabs/core_api/issues/34)
- Source: [/api/io/streams.js](https://github.com/dirigiblelabs/core_api/blob/master/core_api/ScriptingServices/api/io/streams.js)
- Status: **stable**

Basic Usage
---

```javascript
/* globals $ */
/* eslint-env node, dirigible */

var streams = require('api/io/streams');
var response = require('api/http/response');

var outputStream = streams.createByteArrayOutputStream();

streams.writeText(outputStream, "Some text content");

var bytes = outputStream.getBytes();
response.println("[Stream Content as Bytes]: " + bytes);

var text = String.fromCharCode.apply(String, bytes);
response.println("[Stream Content as Text]: " + text);

var inputStream = streams.createByteArrayInputStream(bytes);
var outputStreamCopy = streams.createByteArrayOutputStream();
streams.copy(inputStream, outputStreamCopy);
var copiedBytes = outputStreamCopy.getBytes();
var copiedText = String.fromCharCode.apply(String, copiedBytes);
response.println("[Stream Copied Content as Text]: " + copiedText);

response.flush();
response.close();
```
