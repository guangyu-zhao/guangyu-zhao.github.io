---
title: RSA Algorithm
edit: 2022-07-27
status: Completed
description: RSA Algorithm
categories: Software-Algorithm
tags: RSA Algorithm
---

# RSA公钥私钥算法

## 目录

*   [1.选择RSA公私钥生成， 得到一对公钥PUBLIC KEY和私钥PRIVATE KEY](#1选择rsa公私钥生成-得到一对公钥public-key和私钥private-key)

    *   [公钥](#公钥)

    *   [私钥](#私钥)

*   [2.PUBLIC KEY发给公众](#2public-key发给公众)

*   [3.看到这个PUBLIC KEY的人选择根据公钥加密文本， 公钥栏输入PUBLIC KEY， 输入要加密的字符串， 得到签名](#3看到这个public-key的人选择根据公钥加密文本-公钥栏输入public-key-输入要加密的字符串-得到签名)

*   [4.再根据私钥解密文本，输入私钥PRIVATE KEY和签名， 得到那个人发的原始信息](#4再根据私钥解密文本输入私钥private-key和签名-得到那个人发的原始信息)

## 1.选择RSA公私钥生成， 得到一对公钥PUBLIC KEY和私钥PRIVATE KEY

### 公钥

```verilog
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAtPjMK4fo7GgTQjD0mVUl
nXOBtZ5f6gmZ0O3uJ/1X19xmuYLcj6R6I2Y/J7AdKR4hUtj3kIFoex8riv6KJPbq
7RtAyZSW2sqHXvrFlHR4Yo921MgvJnsFLWJl/JPgc/uNOVHvTWWzpo52PYJRQlj8
g7JhuciWtRS9s2EI0KyWHAc6iMfNbW35SIJF+gF1QmgdZu7CdG9R3h8x7KhD9PLf
zgaHzCxY3XNOOWvSipnlzrRx8SZ33cKLMlwlP9O0/wDpKmK5NpC3kYm8C8e9JLTx
wbFoiX68HrrnpYWHDc0ZuBsup67jBFjBGgVVwdReWy9eBp27b62AfJJnUuM9Z+YR
JQIDAQAB
-----END PUBLIC KEY-----
```

### 私钥

```verilog
-----BEGIN PRIVATE KEY-----
MIIEvQIBADANBgkqhkiG9w0BAQEFAASCBKcwggSjAgEAAoIBAQC0+Mwrh+jsaBNC
MPSZVSWdc4G1nl/qCZnQ7e4n/VfX3Ga5gtyPpHojZj8nsB0pHiFS2PeQgWh7HyuK
/ook9urtG0DJlJbayode+sWUdHhij3bUyC8mewUtYmX8k+Bz+405Ue9NZbOmjnY9
glFCWPyDsmG5yJa1FL2zYQjQrJYcBzqIx81tbflIgkX6AXVCaB1m7sJ0b1HeHzHs
qEP08t/OBofMLFjdc045a9KKmeXOtHHxJnfdwosyXCU/07T/AOkqYrk2kLeRibwL
x70ktPHBsWiJfrweuuelhYcNzRm4Gy6nruMEWMEaBVXB1F5bL14GnbtvrYB8kmdS
4z1n5hElAgMBAAECggEBAKyC0tXYO/BHkbwyQKh941qBRi9kJphJyKfCd5kFRpyO
DBphJXGEX62pBSEHH/UXNLrt+qh0w61CXFamJ/furKmTpiHClD9CeuLOeFP45t1F
VwilP1UWRiwqNYAdUwQc0lXGxjBod2WZPhuKQ33Up/m+rKvWC9vYRrFdGXMaYgma
O/cNCQOemWqp1ZJShF4DDUg51Gcp473DLUyzObnC0tiB6q2ikrEK1ab8rKyR+AMO
6VmXShr6Df9EA/F5HvQGiNsTf2TxMOdoPzKY+iIQSRkcXyMJvIgyFU6Bi90tIFBt
iqlyPtMizu5REf4Vp5sDXw4ldIT0YWPOWbGKUkSlvMECgYEA3GIO3tM7V22DdAHe
L0DiBMa4oM4D0QRNLrFwAuFXAbYci1KU8Hn8+DqCTT2PaTl7vLqo6FZ0k8ypTpJi
3D3n3n+EDATNEwvQ5lPKYi1y8s6A8gsdqvqkbCUNtXTaNPPc/m297zcxH0FoCdZt
SOtIbkVI1i0GUQyP1iFJDdqf63ECgYEA0jgsvz7uAsZbpWF8q/PEEMkgkgw/kk8M
uagHn8z7RgDZQAuA+aj/zyWlppYMXXoDPAC6rRF6A3B1k3jZifQc8Xe/qrJxsSYz
znMs0zPUTl4CEBOQJ/x/KoX791nyFItXhTsD5S3RkQQe1o3+1WkrZ+l4pmQEfGvs
9SOJ5ukqnvUCgYAOtkEV4PYKLRZkbSd+8g7kkLuMiJQ6pNXeMxwuJQrg415ecqHc
t9gKXiWKsHxdYuf+vls+P19C6pu20hDlcQCEmvCeuMdT6SsF5TwSd8Q/r0duYQ2W
92p4ibSzk1xpwonTNlJCoOWXl48xcO4Uuxg3vEpTeef9CyCjA8/Tq++XEQKBgDsC
Aa19IJouy7LUdoZd2n9LtZTJU17iSZQjkmBMzYuM2W6czAtIYOXoj2L/Y2Epypah
LcU+zp0AiEBo/8c1eppdHrPvevJa4tfkhISUW9fTk4intSNEQP3StjNsUANsSZjg
Q+ukvNqT6YQYP5vv9XspkfBCyu+R6+WzoBXtBUWxAoGAb8I8QMSpcBzwUSE4dXWo
ZN1d/W1qhwic8976pINj7PeJV1qpOXUE0eOmIb8UxM2F5lOtw8Q7+eN7pPNbyHVr
6RmmY9Z3HOdcypC7Rf+ZxSI1aM1phw9CToj0n5DQ7TUrzlQMVVqe4Zqz5EQwznP1
WT3mYQkt1h4wb9c6Dy8Wouw=
-----END PRIVATE KEY-----
```
<img src='https://raw.githubusercontent.com/TX-Leo/TX-Leo.github.io/main/_posts/2022-07-27-RSA-Algorithm/image/image_T8ove-MaI2.png' width="60%" alt="image_T8ove-MaI2">

## 2.PUBLIC KEY发给公众

## 3.看到这个PUBLIC KEY的人选择根据公钥加密文本， 公钥栏输入PUBLIC KEY， 输入要加密的字符串， 得到签名

<img src='https://raw.githubusercontent.com/TX-Leo/TX-Leo.github.io/main/_posts/2022-07-27-RSA-Algorithm/image/image_rQcEOq4Pxq.png' width="60%" alt="image_rQcEOq4Pxq">

## 4.再根据私钥解密文本，输入私钥PRIVATE KEY和签名， 得到那个人发的原始信息

<img src='https://raw.githubusercontent.com/TX-Leo/TX-Leo.github.io/main/_posts/2022-07-27-RSA-Algorithm/image/image_mtQMqoFYEA.png' width="60%" alt="image_mtQMqoFYEA">

公钥

> \-----BEGIN PUBLIC KEY-----
> MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAq+IV6JDLEnPYtuWahTpJ
> \+f+TExnZUPlnwayDhc5FETbLgiyTzH+NmtCcBW42aHLQUeWwEAoWCn/YsIQrun8B
> gJUaLX7xBji/gKvU5MOLaZVU86x6tE9ViO1cCdKQu1PY7OxQEjq0UIjfMX9VIG+G
> YZ2ilpFwCutVlahnWkREkXKkBHWYyD4wjIY2PWse0sMPAH35XPlP/qJ+M9QNQ3e/
> nRxnQ041y6da6pmODyBBAMNvvEoJtWBrcEj0v5g2iSMLNGqoNG/j9cgNLQyAZ/ON
> qZp4vXNdVeiaCrhsORwNP1rL8BQjh8r27pC2dur3T6YGYehlCqNGtkAakr+tOdpy
> QQIDAQAB
> \-----END PUBLIC KEY-----

私钥

> \-----BEGIN PRIVATE KEY-----
> MIIEvAIBADANBgkqhkiG9w0BAQEFAASCBKYwggSiAgEAAoIBAQCr4hXokMsSc9i2
> 5ZqFOkn5/5MTGdlQ+WfBrIOFzkURNsuCLJPMf42a0JwFbjZoctBR5bAQChYKf9iw
> hCu6fwGAlRotfvEGOL+Aq9Tkw4tplVTzrHq0T1WI7VwJ0pC7U9js7FASOrRQiN8x
> f1Ugb4ZhnaKWkXAK61WVqGdaRESRcqQEdZjIPjCMhjY9ax7Sww8Afflc+U/+on4z
> 1A1Dd7+dHGdDTjXLp1rqmY4PIEEAw2+8Sgm1YGtwSPS/mDaJIws0aqg0b+P1yA0t
> DIBn842pmni9c11V6JoKuGw5HA0/WsvwFCOHyvbukLZ26vdPpgZh6GUKo0a2QBqS
> v6052nJBAgMBAAECggEAEQjMAQtwhLikbqPcp316XWNd0RPLvMGq7b/KHRWvNKCI
> lLMURr0RbJlmDQe6LqnKSYOI6l4Fhy7aa8v9hXMW1AZy3LVq76HqILdm1vEmPOWG
> 0Mt0MbB3GqXjbDnJDDeoFPrqiJP20NBvxjkHV7qVx9DWjzOEtiBSkA1riL+hSAS5
> 8mpbAjouMAMZIsiQtnBclOo3p2BX3B20S0IHzxoRU3281PACb83vrJB4SBxJySR1
> Qsey7WI4ZppZ1+tWeduuY8eSnQZCVR/t1CAIT5Tg3wN2Yk7RAO7cHBZTIGrkWPzM
> Rz3mA9c8UbHLrpIixKHeMWjx95ArAjWpGio/HQC1UQKBgQDXsl0CqGxHQGopNFcy
> ATf46fKW03m84LA4H+PZznuJ9MbCVrFlUuWBnF4nT0NZH1Sfqbg9Wr5k/aFUWz+F
> Ia7akr0hcGx+FGRGk9AfFV8ep55P0cru996ZSX5trUC5VfE1lVJMdyPwDD2jihUD
> \+lz/Ou8hzm0+lRPHfRkEMS839QKBgQDL//GCbusUw67nttSlAR08bYqI52KEPUxm
> SAgzukgRBODYVYqXAxbE6IksUEvS0OiMs/mrC4+MTtYeWfkitt5nSCsCEkveMvfm
> IN49eF8MRxD0jBGeB6WchlLROrNey4e6sYq6V4K4LNqHOWMA0ns/3ABDfbaewjI5
> eMQNiDj9nQKBgE9TM02U7y1NDT3WF/M164XJVAQQBgdmgqhBYiRqAZj8wlQaWecv
> k2QVQ7MlPVl7Yj3NxwoZY0f01u4VGMk3V/zeVlwD4oKDsVUba0DjNTYq4tfsCbvU
> wLKTCsH/I3yFlM3l+nxQnJDdj5WjZJMv8h+TZvqB1j9byAhng1m9VOY5AoGAV+6N
> 0nQvHncuuDBlvm4ZhQeOlG5wV6H4gYoBBxL/p15b8MQGhgtN0DiPkCtYU5m685NM
> Rf8otAjzYIfVzLHYcdp4t17dlvyPQIHgacyt46PqWg7aNS0EpNB9eDR+Rpkie0W2
> D5ZTAUJMO8dvtlYDzEXvUygoBIyei4lTsKWMMz0CgYAwkV7nkpqj/PRDWRAitwTs
> FW21qSeNb3w6jOajSqNWZiMfIWtApMRSdX5okAwAkPliOO70p3fVf+Ph63lch+nF
> m5VzPZ5pO0J/HtlS3QSJd1otim31TxK9vOfplcH+gdkosTbzM53Ondc9+hfNpeSM
> lbv904ujold/Rxf8UgonwA==
> \-----END PRIVATE KEY-----
