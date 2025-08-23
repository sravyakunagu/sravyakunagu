SCRIPTING_08 - Script error while running init script: javax.script.ScriptException: javax.script.ScriptException: javax.net.ssl.SSLHandshakeException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target

[bdadmin@devecpvm023438 ~]$ openssl s_client -connect object.lb4.rbsgrp.net :443                                                                                                           -showcerts
s_client: Use -help for summary.
[bdadmin@devecpvm023438 ~]$ openssl s_client -connect object.lb4.rbsgrp.net :443 -showcerts
s_client: Use -help for summary.
[bdadmin@devecpvm023438 ~]$ openssl s_client -connect object.lb4.rbsgrp.net:443 -showcerts
CONNECTED(00000003)
depth=2 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Root CA
verify return:1
depth=1 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA
verify return:1
depth=0 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net
verify return:1
---
Certificate chain
 0 s:C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net
   i:C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA
-----BEGIN CERTIFICATE-----
MIIHsDCCBpigAwIBAgIEZvhOUDANBgkqhkiG9w0BAQsFADB/MQswCQYDVQQGEwJn
YjEpMCcGA1UEChMgVGhlIFJveWFsIEJhbmsgb2YgU2NvdGxhbmQgR3JvdXAxIjAg
BgNVBAsTGVByb2R1Y3Rpb24gRzEgUEtJIFNlcnZpY2UxITAfBgNVBAMTGFJCUyBH
bG9iYWwgRzEgSXNzdWluZyBDQTAeFw0yNDExMDcxNzExMDhaFw0yNzExMDcxNzQx
MDhaMIGOMQswCQYDVQQGEwJnYjEpMCcGA1UEChMgVGhlIFJveWFsIEJhbmsgb2Yg
U2NvdGxhbmQgR3JvdXAxIjAgBgNVBAsTGVByb2R1Y3Rpb24gRzEgUEtJIFNlcnZp
Y2UxEDAOBgNVBAsTB0RldmljZXMxHjAcBgNVBAMTFW9iamVjdC5sYjQucmJzZ3Jw
Lm5ldDCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAKQMbcVm8jFpshRV
ZfD3FiswGavNbFcZ7vGixabgy4SPNLI1Bbdi+orMfjMNEhy5VZvOoyA9VQ7h0O+1
OagduvnacNQplHMFClpNoniJRSjn4Gfv5+vbOukMMRGHjvVkcT36lZDwqpfMtwMC
FzswhSoCjzNoccYfKZMC7gCbk7oOfdGShTUQKM+CQHalqo4f5VmPR3sGBnXxEW8M
NwcfiATOPfzDQV9IbxknXhoYAvL9NSvJoNNUNWBAyfImE/2dq2wi9w50/jsud0jO
rmFn6tFtOmmM8wTqNDWJzXsT4x5y3FgNGAkXYVGos8jqoT0jfehCCXpCBA/j9kgS
yYOvxvUCAwEAAaOCBCIwggQeMAsGA1UdDwQEAwIFoDCB8AYDVR0gBIHoMIHlMIHi
BgsqhjoAAoXBSGQBAjCB0jCBzwYIKwYBBQUHAgIwgcIagb9UaGlzIGNlcnRpZmlj
YXRlIGhhcyBiZWVuIGlzc3VlZCBhcyBhIE1lZGl1bSBBc3N1cmFuY2UgY2VydGlm
aWNhdGUgdW5kZXIgUkJTIEVudGVycHJpc2UgUEtJIENlcnRpZmljYXRlIFBvbGlj
eSB3aGljaCBpcyBpZGVudGlmaWVkIGJ5IHRoZSBmb2xsb3dpbmcgT2JqZWN0IElk
ZW50aWZpZXIgOiAxLjIuODI2LjAuMi45MDMxMi4xMDAuMTAdBgNVHSUEFjAUBggr
BgEFBQcDAgYIKwYBBQUHAwEwgaMGA1UdEQSBmzCBmIIVb2JqZWN0LmxiNC5yYnNn
cnAubmV0ghdtZzdlYzYwMy5sYjQucmJzZ3JwLm5ldIIZKi5tZzdlYzYwMy5sYjQu
cmJzZ3JwLm5ldIIXbW0yZWM1ODYubGI0LnJic2dycC5uZXSCFyoub2JqZWN0Lmxi
NC5yYnNncnAubmV0ghkqLm1tMmVjNTg2LmxiNC5yYnNncnAubmV0MIIB3QYDVR0f
BIIB1DCCAdAwggHMoIIByKCCAcSGaGh0dHA6Ly9nZW4xY2VydHMud2ViLnJic2dy
cC5uZXQvQ1JML3Jic19nbG9iYWxfZzFfaXNzdWluZ19jYV9wcm9kdWN0aW9uX2cx
X3BraV9zZXJ2aWNlX2diX2NybGZpbGVjODkuY3JshoHCbGRhcDovL2dsb2JhbGdl
bjFwa2lkaXIubGIxLnJic2dycC5uZXQvY249Q1JMODksY249UkJTJTIwR2xvYmFs
JTIwRzElMjBJc3N1aW5nJTIwQ0Esb3U9UHJvZHVjdGlvbiUyMEcxJTIwUEtJJTIw
U2VydmljZSxvPVRoZSUyMFJveWFsJTIwQmFuayUyMG9mJTIwU2NvdGxhbmQlMjBH
cm91cCxjPWdiP2NlcnRpZmljYXRlUmV2b2NhdGlvbkxpc3SkgZIwgY8xCzAJBgNV
BAYTAmdiMSkwJwYDVQQKEyBUaGUgUm95YWwgQmFuayBvZiBTY290bGFuZCBHcm91
cDEiMCAGA1UECxMZUHJvZHVjdGlvbiBHMSBQS0kgU2VydmljZTEhMB8GA1UEAxMY
UkJTIEdsb2JhbCBHMSBJc3N1aW5nIENBMQ4wDAYDVQQDEwVDUkw4OTArBgNVHRAE
JDAigA8yMDI0MTEwNzE3MTEwOFqBDzIwMjYxMjE0MDU0MTA4WjAfBgNVHSMEGDAW
gBTzgReqzsv1i+UzvTwhV5MGNWV8TTAdBgNVHQ4EFgQU/+T8jQNqX2o0upCMzFS5
uiEesRUwCQYDVR0TBAIwADANBgkqhkiG9w0BAQsFAAOCAQEAeQrokhsMjajLdNQq
73TAXeg6u6FZl+OQqlHOgTYR0RqTs3BW09bTexXmmfloGum6sxHhJVPpAj4N/0Kg
K4pvwT6HaRtcLY3dDI6X9sn++o2jFl/o/QVyrhNdLgejm6tiyeyJSFVg/mIAtQtS
C5szVxBhVagVitkFBXiuXK9tfiJdNQ358GG3LTMqB4szTjkfHPnQX4t7UMbqdV3j
LAW+LoScnX0Ip9kn6uUlv1XAhtD3JgVCAHDv19H8cuFbymydkisq7v9uvi4bx1Yf
+bLEIli2X6h5UDw+Qlqv/ys/VSaTeKHv3xI4Wzu6hnyxdRL9OLk7K63BEEOdz7Jw
V5lavw==
-----END CERTIFICATE-----
---
Server certificate
subject=C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net

issuer=C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA

---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA
Server Temp Key: ECDH, P-256, 256 bits
---
SSL handshake has read 2481 bytes and written 389 bytes
Verification: OK
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 2048 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: C23844D2177CB8B6AB00C75A7FC56038A20AA5F14665B5D756FC14834E55B04F
    Session-ID-ctx:
    Master-Key: ECB68FE73341FA24A6E63B0B71FCC4D3BC15FAAF83790A062CA1CF31178E05C4C8B64C8739EDD65C30159B70325D1027
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    Start Time: 1755864860
    Timeout   : 7200 (sec)
    Verify return code: 0 (ok)
    Extended master secret: yes
---

[bdadmin@devecpvm017474 ~]$ openssl s_client -connect object.lb4.rbsgrp.net:443 -showcerts
CONNECTED(00000003)
depth=2 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Root CA
verify return:1
depth=1 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA
verify return:1
depth=0 C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net
verify return:1
---
Certificate chain
 0 s:C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net
   i:C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA
-----BEGIN CERTIFICATE-----
MIIHsDCCBpigAwIBAgIEZvhOUDANBgkqhkiG9w0BAQsFADB/MQswCQYDVQQGEwJn
YjEpMCcGA1UEChMgVGhlIFJveWFsIEJhbmsgb2YgU2NvdGxhbmQgR3JvdXAxIjAg
BgNVBAsTGVByb2R1Y3Rpb24gRzEgUEtJIFNlcnZpY2UxITAfBgNVBAMTGFJCUyBH
bG9iYWwgRzEgSXNzdWluZyBDQTAeFw0yNDExMDcxNzExMDhaFw0yNzExMDcxNzQx
MDhaMIGOMQswCQYDVQQGEwJnYjEpMCcGA1UEChMgVGhlIFJveWFsIEJhbmsgb2Yg
U2NvdGxhbmQgR3JvdXAxIjAgBgNVBAsTGVByb2R1Y3Rpb24gRzEgUEtJIFNlcnZp
Y2UxEDAOBgNVBAsTB0RldmljZXMxHjAcBgNVBAMTFW9iamVjdC5sYjQucmJzZ3Jw
Lm5ldDCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAKQMbcVm8jFpshRV
ZfD3FiswGavNbFcZ7vGixabgy4SPNLI1Bbdi+orMfjMNEhy5VZvOoyA9VQ7h0O+1
OagduvnacNQplHMFClpNoniJRSjn4Gfv5+vbOukMMRGHjvVkcT36lZDwqpfMtwMC
FzswhSoCjzNoccYfKZMC7gCbk7oOfdGShTUQKM+CQHalqo4f5VmPR3sGBnXxEW8M
NwcfiATOPfzDQV9IbxknXhoYAvL9NSvJoNNUNWBAyfImE/2dq2wi9w50/jsud0jO
rmFn6tFtOmmM8wTqNDWJzXsT4x5y3FgNGAkXYVGos8jqoT0jfehCCXpCBA/j9kgS
yYOvxvUCAwEAAaOCBCIwggQeMAsGA1UdDwQEAwIFoDCB8AYDVR0gBIHoMIHlMIHi
BgsqhjoAAoXBSGQBAjCB0jCBzwYIKwYBBQUHAgIwgcIagb9UaGlzIGNlcnRpZmlj
YXRlIGhhcyBiZWVuIGlzc3VlZCBhcyBhIE1lZGl1bSBBc3N1cmFuY2UgY2VydGlm
aWNhdGUgdW5kZXIgUkJTIEVudGVycHJpc2UgUEtJIENlcnRpZmljYXRlIFBvbGlj
eSB3aGljaCBpcyBpZGVudGlmaWVkIGJ5IHRoZSBmb2xsb3dpbmcgT2JqZWN0IElk
ZW50aWZpZXIgOiAxLjIuODI2LjAuMi45MDMxMi4xMDAuMTAdBgNVHSUEFjAUBggr
BgEFBQcDAgYIKwYBBQUHAwEwgaMGA1UdEQSBmzCBmIIVb2JqZWN0LmxiNC5yYnNn
cnAubmV0ghdtZzdlYzYwMy5sYjQucmJzZ3JwLm5ldIIZKi5tZzdlYzYwMy5sYjQu
cmJzZ3JwLm5ldIIXbW0yZWM1ODYubGI0LnJic2dycC5uZXSCFyoub2JqZWN0Lmxi
NC5yYnNncnAubmV0ghkqLm1tMmVjNTg2LmxiNC5yYnNncnAubmV0MIIB3QYDVR0f
BIIB1DCCAdAwggHMoIIByKCCAcSGaGh0dHA6Ly9nZW4xY2VydHMud2ViLnJic2dy
cC5uZXQvQ1JML3Jic19nbG9iYWxfZzFfaXNzdWluZ19jYV9wcm9kdWN0aW9uX2cx
X3BraV9zZXJ2aWNlX2diX2NybGZpbGVjODkuY3JshoHCbGRhcDovL2dsb2JhbGdl
bjFwa2lkaXIubGIxLnJic2dycC5uZXQvY249Q1JMODksY249UkJTJTIwR2xvYmFs
JTIwRzElMjBJc3N1aW5nJTIwQ0Esb3U9UHJvZHVjdGlvbiUyMEcxJTIwUEtJJTIw
U2VydmljZSxvPVRoZSUyMFJveWFsJTIwQmFuayUyMG9mJTIwU2NvdGxhbmQlMjBH
cm91cCxjPWdiP2NlcnRpZmljYXRlUmV2b2NhdGlvbkxpc3SkgZIwgY8xCzAJBgNV
BAYTAmdiMSkwJwYDVQQKEyBUaGUgUm95YWwgQmFuayBvZiBTY290bGFuZCBHcm91
cDEiMCAGA1UECxMZUHJvZHVjdGlvbiBHMSBQS0kgU2VydmljZTEhMB8GA1UEAxMY
UkJTIEdsb2JhbCBHMSBJc3N1aW5nIENBMQ4wDAYDVQQDEwVDUkw4OTArBgNVHRAE
JDAigA8yMDI0MTEwNzE3MTEwOFqBDzIwMjYxMjE0MDU0MTA4WjAfBgNVHSMEGDAW
gBTzgReqzsv1i+UzvTwhV5MGNWV8TTAdBgNVHQ4EFgQU/+T8jQNqX2o0upCMzFS5
uiEesRUwCQYDVR0TBAIwADANBgkqhkiG9w0BAQsFAAOCAQEAeQrokhsMjajLdNQq
73TAXeg6u6FZl+OQqlHOgTYR0RqTs3BW09bTexXmmfloGum6sxHhJVPpAj4N/0Kg
K4pvwT6HaRtcLY3dDI6X9sn++o2jFl/o/QVyrhNdLgejm6tiyeyJSFVg/mIAtQtS
C5szVxBhVagVitkFBXiuXK9tfiJdNQ358GG3LTMqB4szTjkfHPnQX4t7UMbqdV3j
LAW+LoScnX0Ip9kn6uUlv1XAhtD3JgVCAHDv19H8cuFbymydkisq7v9uvi4bx1Yf
+bLEIli2X6h5UDw+Qlqv/ys/VSaTeKHv3xI4Wzu6hnyxdRL9OLk7K63BEEOdz7Jw
V5lavw==
-----END CERTIFICATE-----
---
Server certificate
subject=C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, OU = Devices, CN = object.lb4.rbsgrp.net

issuer=C = gb, O = The Royal Bank of Scotland Group, OU = Production G1 PKI Service, CN = RBS Global G1 Issuing CA

---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA
Server Temp Key: ECDH, P-256, 256 bits
---
SSL handshake has read 2481 bytes and written 389 bytes
Verification: OK
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 2048 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: 18970BE0CDBBDFA4C11E1B57F4C346E86E6BAC838BD259C4B8426A5144D3167D
    Session-ID-ctx:
    Master-Key: A6BD457496ECF7438E6F04570D9BA03D0169E68E91BD249676FB09371083F1478FC26EC49F25EEC0EEDF7EB3346F7531
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    Start Time: 1755864984
    Timeout   : 7200 (sec)
    Verify return code: 0 (ok)
    Extended master secret: yes
---



