---
title: "Page Layout"
permalink: /docs/pages/
excerpt: "Suggestions and Front Matter defaults for working with pages."
last_modified_at: 2016-11-03T11:13:12-04:00
classes: wide
---

The initial layout of the pages is defined by creating a special file on the SPIFFS file system.
This layout is displayed each time HASP starts up.
You can upload this file *(and other resource assets like fonts and images)* in the web interface Configuration > HASP Settings.

## pages.jsonl

The location of this file is `/pages.jsonl` in the root of the filesystem.
It uses the [JSON Lines format](http://www.jsonlines.org) with one json object per line.
Each line should contain exactly **one** valid json object and end with a line-break `\n` *(not a comma)*.

The file is interpreted **line-by-line**.
When a malformed line is encountered, the processing of the rest of the file stops.
If you are missing objects, check the logs to see which line was processed last.
You probably have a typo in the following line which blocks parsing the rest of the file.

**Note** The complete file in its entirety is *not* a valid json file.
Each individual line however must be a valid json object.
The file extension is `.jsonl` and not `.json`.
{: .notice--info}

### Objects
Each individual line defines **one object** on a page and the line has the json format.
The order of objects dictates the layer on the page from bottom to top.

Example Objects
```json
{"page":2,"id":1,"objid":12,"x":20,"y":20,"h":50,"w":50,"enabled":"true","hidden":"false"}
{"page":2,"id":2,"objid":50,"x":20,"y":120,"h":100,"w":150,"enabled":"false","hidden":"false"}
```
