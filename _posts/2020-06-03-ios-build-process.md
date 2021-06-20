---
title: IOS 빌드 과정
author: Yongjun
date: 2020-06-03 00:00:00 +0800
categories: [build, ios]
tags: [ios, build, certificate, provisioning profile, code sign]
---

<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRr3x-w_RSEqJfDGdjDkya3ZuXImq7u9Bcpcx5iuJIAUa_F7nIWbMGVZHAPKp7smawUtnitzfJtb6jL/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</div>
<br>

## OpenSSL commands
```c++
// plain text
echo Hello, IOS! >> test.txt

// hash
openssl dgst -sha256 test.txt >> test.hash

// .p12 -> pem
openssl pkcs12 -in privatekey.p12 -out privatekey.pem -nodes

// get publickey & info from CSR
openssl req -in CertificateSigningRequest.request -noout -pubkey -text

// cer -> pem
openssl x509 -inform der -in dev.cer -pubkey -noout > publickey_from_cer.pem

// test app
echo Hello, IOS! >> code.txt

// hash
openssl dgst -sha256 code.txt >> code.hash

// sign
openssl rsautl -sign -inkey privatekey.pem -in code.hash -out code.sign

// verify
openssl rsautl -verify -inkey publickey.pem -in code.sign -pubin
```
