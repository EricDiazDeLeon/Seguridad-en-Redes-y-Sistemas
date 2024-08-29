## Objetivo 
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.
## Datos de acceso al nivel 
bandit15
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
## Solución  
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: E3F9A3655504C2442AFC16DC324D64BEEB2EF935595BB409A0B0B1597347286C
    Session-ID-ctx:
    Resumption PSK: 5FF23DB324F1047D80ADF68FF2B46E4B758B198E3F79E96BA2CBC152256A35D9B81CD8DD5544519B752CDC2773B4D648
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - 9d 82 af 18 d4 dc 9e 59-64 3a 1d 3b 43 8f 0d 0f   .......Yd:.;C...
    0020 - 4c 08 26 0a 6e 8b 91 0a-16 73 7f 7c d5 3e d0 cf   L.&.n....s.|.>..
    0030 - 15 67 98 37 00 e0 6a 5b-3c 62 ed 49 a5 39 e2 91   .g.7..j[<b.I.9..
    0040 - f7 6a d6 2c 11 a9 50 a9-f4 c4 65 59 87 ad 86 da   .j.,..P...eY....
    0050 - c5 71 dc b6 25 46 7f f6-11 20 31 3d 10 ee 59 07   .q..%F... 1=..Y.
    0060 - 45 61 2c d5 9f 1c 8c 27-62 fa 30 3e 2a e8 39 26   Ea,....'b.0>*.9&
    0070 - 39 49 ad f4 02 79 63 bf-ec aa 7e d9 d9 f4 01 e0   9I...yc...~.....
    0080 - 48 86 45 40 3b 86 2e 09-20 8f e5 b3 24 ac 5a 15   H.E@;... ...$.Z.
    0090 - 60 cd 78 3f cc 82 eb d0-ab de f9 fd c4 27 fb 00   `.x?.........'..
    00a0 - cb 45 ae 01 fb 3e d7 15-3a 77 8d 3e 8c 78 98 5d   .E...>..:w.>.x.]
    00b0 - d1 b4 26 52 88 40 73 54-2b e0 da e1 24 e5 86 c0   ..&R.@sT+...$...
    00c0 - a4 86 d3 78 5a 43 72 2b-8e 6b 1d f0 84 23 f9 e7   ...xZCr+.k...#..
    00d0 - 4e cf b3 79 06 4d 46 a4-1c c7 4d 64 3c ad ea d0   N..y.MF...Md<...

    Start Time: 1724873518
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 6B2402DF036614C4062463197510E8EEDF1A4D5BFC5C1A68438E738CCA49AC33
    Session-ID-ctx:
    Resumption PSK: A898E8C99104EA06288A3B1C7551B7109BC84222CEE3E24B5E302ED66DA1A2429197FEC4A19473F5E7B860C8884F3C65
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - f3 a3 b0 12 a9 68 66 af-0d 31 cc 07 27 97 32 a1   .....hf..1..'.2.
    0020 - a4 58 5c c0 85 33 2b 45-79 bf 34 5a 3a 1c f6 b6   .X\..3+Ey.4Z:...
    0030 - 85 36 11 9a f0 5c 7d d6-06 06 4c b2 95 24 3b 7a   .6...\}...L..$;z
    0040 - 01 37 14 ad 48 72 d5 6f-a7 77 13 a2 99 3d d5 13   .7..Hr.o.w...=..
    0050 - d2 1b 17 62 d3 ed 37 b0-5d 0c 6d 57 8a 51 17 80   ...b..7.].mW.Q..
    0060 - ec 29 9c 96 b9 68 5e 96-6c 4b dd 32 2f bd 6f 8a   .)...h^.lK.2/.o.
    0070 - d8 a3 cd 09 dd 6b 2a fd-a7 a8 22 ad 89 d0 19 ac   .....k*...".....
    0080 - 51 83 d6 7b b1 21 8e 0f-ff d2 e7 3f 27 2f fb d3   Q..{.!.....?'/..
    0090 - 41 23 df 4d ba 9c 38 2e-29 43 e7 c9 b1 54 4a c6   A#.M..8.)C...TJ.
    00a0 - aa f2 20 e6 df 2e d0 d6-13 e9 f6 f2 1e a8 90 43   .. ............C
    00b0 - 05 96 4f e4 82 fc 17 62-93 c3 c1 8a 70 96 13 b2   ..O....b....p...
    00c0 - 7d 99 f7 1c 2e d0 5e d6-f8 e7 ee 2a 9c 5d 44 3c   }.....^....*.]D<
    00d0 - b2 18 6c 03 d1 09 49 38-1f 62 23 93 bd bf 5a 72   ..l...I8.b#...Zr

    Start Time: 1724873518
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
bandit15@bandit:~$
```

## Notas Adicionales 


### Referencias
• Over The Wire: Bandit Write Up: https://jwuk.files.wordpress.com/2016/05/writeup1.pdf

