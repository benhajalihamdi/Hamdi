---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---

MAKING STRINGS SAF FOR ENCODING AND DECODING AND CLEANING UP
### 1. Cleaning up Newlines when Encoding

By default, the `base64` command automatically wraps long text into multiple lines. If you are trying to generate a clean, single-line token to use in a URL or a script, those newlines will break your code.

You can use `tr -d` to strip the newlines (`\n`) right out:

### 2. Creating "URL-Safe" Base64

Standard Base64 uses two characters that mess up web URLs: `+` and `/`.

Developers often use `tr` to **translate** standard Base64 characters into "URL-safe" characters (`-` and `_`), and then reverse them back later.

#### To Encode (Make URL-Safe):

Bash
```
# 1. Encode to normal Base64 
# 2. Change '+' to '-' 
# 3. Change '/' to '_' 
echo "Hello World" | base64 | tr '+/' '-_'
```

#### To Inverse (Decode the URL-Safe Base64):

To decode it, you have to use `tr` to put the original characters _back_ before passing it to `base64 -d`:

Bash 
```
# 1. Change '-' back to '+'
# 2. Change '_' back to '/'
# 3. Decode normally
 echo "SGVsbG8gV29ybGQK" | tr '-_' '+/' | base64 -d

```
