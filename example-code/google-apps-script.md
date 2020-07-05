---
layout: page
title: Google Apps Script
parent: Example code
permalink: /example-code/google-apps-script/
description: >-
  Convert HTML to an image (png, jpg or webp) with Google Apps Script + the HTML/CSS to Image
  API. Renders exactly like Google Chrome.
---
# Google Apps Script
{: .no_toc }
{: .fs-9 }

Generate a png, jpg or webp images with Google Apps Script.
{: .fs-4 .fw-300 }

[Live demo](https://htmlcsstoimage.com/demo){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Get an API Key](https://htmlcsstoimage.com){: .btn .fs-5 .mb-4 .mb-md-0 }
<hr>

Table of contents
{: .text-delta }
- TOC
{:toc}

## Generate an image with Google Apps Script
With [Google Apps Script](https://developers.google.com/apps-script), you can build add-ons for Google. It is based on JavaScript, but includes built in functions that you'll need to use to work with the HTML/CSS to Image API.

Our documented JavaScript examples won't work with GAS. You can make use of the built in UrlFetchApp to generate images with the API.

## Example code

This shows you how to authenticate with the API and pass parameters in a POST request. This is passing html/css parameters to the API. You can adapt this sample to pass any parameters or work with any of our endpoints.

```javascript
var formData = {
  'html': 'Test',
  'css': 'test',
};

var options = {
  'method' : 'post',
  'payload' : formData
};
// Replace username with your User ID and password with your API Key
options.headers = {"Authorization": "Basic " + Utilities.base64Encode(username + ":" + password)};
UrlFetchApp.fetch("https://hcti.io/v1/image", options);
```

{% include code_footer.md version=2 %}