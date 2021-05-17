# 1 - Ennumeration

## Ennumeration

### General - Information disclousure

![](../../.gitbook/assets/imagen%20%28733%29.png)

![](../../.gitbook/assets/imagen%20%28731%29.png)

### Nikto results

{% tabs %}
{% tab title="Plain Text" %}
```text
└─# nikto -h https://www.directvgo.com/uy/
- Nikto v2.1.6
---------------------------------------------------------------------------
+ Target IP:          13.227.92.123
+ Target Hostname:    www.directvgo.com
+ Target Port:        443
---------------------------------------------------------------------------
+ SSL Info:        Subject:  /CN=*.directvgo.com
                   Ciphers:  TLS_AES_128_GCM_SHA256
                   Issuer:   /C=US/O=Amazon/OU=Server CA 1B/CN=Amazon
+ Message:            Multiple IP addresses found: 13.227.92.123, 13.227.92.71, 13.227.92.24, 13.227.92.74
+ Start Time:         2021-05-17 12:04:45 (GMT-4)
---------------------------------------------------------------------------
+ Server: nginx/1.15.12
+ Retrieved via header: 1.1 38808259786238a2b27a3d6a3d65d1ad.cloudfront.net (CloudFront)
+ The X-XSS-Protection header is not defined. This header can hint to the user agent to protect against some forms of XSS
+ Uncommon header 'x-cache' found, with contents: Hit from cloudfront
+ Uncommon header 'x-vhost' found, with contents: publish
+ Uncommon header 'x-amz-cf-pop' found, with contents: EZE51-C1
+ Uncommon header 'x-dispatcher' found, with contents: dispatcher1useast1
+ Uncommon header 'x-cdn' found, with contents: Imperva
+ Uncommon header 'x-amz-cf-id' found, with contents: TdDGtDSUq1JSQEiD5ixY_9kjlUdQCeBFiyTT4YKHvwjnPCizTUKPsQ==
+ Uncommon header 'x-iinfo' found, with contents: 14-141691870-141691874 SNNy RT(1621267214643 272890) q(0 0 0 -1) r(5 5) U9
+ The site uses SSL and the Strict-Transport-Security HTTP header is not defined.
+ The site uses SSL and Expect-CT header is not present.
+ Cookie visid_incap_1887049 created without the secure flag
+ Cookie incap_ses_149_1887049 created without the secure flag
+ Cookie incap_ses_149_1887049 created without the httponly flag
+ Uncommon header 'x-incap-abp' found, with contents: 1
+ Cookie incap_ses_7222_1887049 created without the secure flag
+ Cookie incap_ses_7222_1887049 created without the httponly flag
+ Cookie nlbi_1887049 created without the secure flag
+ Cookie nlbi_1887049 created without the httponly flag
+ Cookie incap_ses_7230_1887049 created without the secure flag
+ Cookie incap_ses_7230_1887049 created without the httponly flag
+ Cookie incap_ses_469_1887049 created without the secure flag
+ Cookie incap_ses_469_1887049 created without the httponly flag
+ Cookie incap_ses_1172_1887049 created without the secure flag
+ Cookie incap_ses_1172_1887049 created without the httponly flag
+ Cookie incap_ses_1170_1887049 created without the secure flag
+ Cookie incap_ses_1170_1887049 created without the httponly flag
+ Cookie incap_ses_990_1887049 created without the secure flag
+ Cookie incap_ses_990_1887049 created without the httponly flag
+ Cookie incap_ses_468_1887049 created without the secure flag
+ Cookie incap_ses_468_1887049 created without the httponly flag
+ Cookie incap_ses_989_1887049 created without the secure flag
+ Cookie incap_ses_989_1887049 created without the httponly flag
+ Cookie incap_ses_1362_1887049 created without the secure flag
+ Cookie incap_ses_1362_1887049 created without the httponly flag

+ Scan terminated:  20 error(s) and 35 item(s) reported on remote host
+ End Time:           2021-05-17 12:18:49 (GMT-4) (844 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested
                            
```
{% endtab %}

{% tab title="---------" %}
```
<--------------
```
{% endtab %}
{% endtabs %}

### Burp result

![](../../.gitbook/assets/imagen%20%28739%29.png)

## CSRF

* Posible mala configuracion de SameSite

![](../../.gitbook/assets/imagen%20%28735%29.png)

## SQLi

## Information disclosure

Accediendo a /.git

![](../../.gitbook/assets/imagen%20%28741%29.png)

/admin 

![](../../.gitbook/assets/imagen%20%28740%29.png)

