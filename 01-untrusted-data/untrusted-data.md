# Lab Writeup – Untrusted Data

## Overview

Platform: CyberJutsu  
Difficulty: Easy

---

## 1. Register

Xuất hiện ở 2 get parameter name và email tại endpoint /register.php

```
GET /register.php?name=test&email=test%40gmail.com HTTP/1.1
...
```

---

## 2. Referer

Xuất hiện ở Header Referer

```
...
Referer: http://192.168.49.128:12000/register.php?name=test&email=test%40gmail.com
...
```

---

## 3. Hidden Path

Xuất hiện tại một endpoint (path ẩn)

```
GET /test.php HTTP/1.1
...
```

---

## 4. Đăng kí

Xuất hiện ở 2 post parameter username và password tại endpoint /sign-up.php

```
POST /sign-up.php
...
username=test&password=test
```

---

## 5. Đăng nhập

Xuất hiện ở 2 post parameter username và password tại endpoint /sign-in.php

```
POST /sign-in.php
...
username=test&password=test
```

---

## 6. Training với Hokage

```
GET /premium.php
...
```

---

## 7. Method ẩn

Một trong các method sau ["OPTIONS", "TRACE", "HEAD", "PUT", "PATCH", "DELETE", "PATCH"]

```
OPTION /index.php
...
```

---

## 8. Profile

Xuất hiện ở các Content-Disposition: bio, filename và các parameter: Content-Type của filename, File
Content

```
POST /profile.php HTTP/1.1
... ------WebKitFormBoundaryZURz268sjPl6o9Q5
Content-Disposition: form-data; name="bio"
test ------WebKitFormBoundaryZURz268sjPl6o9Q5
Content-Disposition: form-data; name="file"; filename="test"
Content-Type: test
test ------WebKitFormBoundaryZURz268sjPl6o9Q5--
```

---

## 9. User-Agent

Thông qua Header User-Agent.

```
GET / HTTP/1.1
...
User-Agent: test
...
```

---

## 10. Hidden Header

```
GET / HTTP/1.1
...
test: test
```

---

## 11. Hidden Parameter

Thêm tham số test vào gói GET nào cũng được

```
GET /?test=test HTTP/1.1
...
```

Thêm tham số test vào gói POST nào cũng được

```
POST /sign-in.php HTTP/1.1
...
username=test&password=test&test=test
```

---

## 12. Cookie

Xuất hiện ở Header Cookie.

```
POST /sign-in.php HTTP/1.1
...
Cookie: PHPSESSID=39b9706993a802a0b3c523f3a6fdf8e5;test=test
...
```

---

## 13. Track

Xuất hiện tại endpoint /track.php

```
GET /track.php?id=test HTTP/1.1
...
```
