# Username enumeration via different responses

> This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password, which can be found in the following wordlists:
>
> *  [Candidate usernames](https://portswigger.net/web-security/authentication/auth-lab-usernames)
> *  [Candidate passwords](https://portswigger.net/web-security/authentication/auth-lab-passwords)
>
>  To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.

 

{% tabs %}
{% tab title="Padin" %}
```
-----------------------------------
```
{% endtab %}

{% tab title="Users" %}
```text
root
admin
test
guest
info
adm
mysql
user
administrator
oracle
ftp
pi
puppet
ansible
ec2-user
vagrant
azureuser
academico
acceso
access
accounting
accounts
acid
activestat
ad
adam
adkit
admin
administracion
administrador
administrator
administrators
admins
ads
adserver
adsl
ae
af
affiliate
affiliates
afiliados
ag
agenda
agent
ai
aix
ajax
ak
akamai
al
alabama
alaska
albuquerque
alerts
alpha
alterwind
am
amarillo
americas
an
anaheim
analyzer
announce
announcements
antivirus
ao
ap
apache
apollo
app
app01
app1
apple
application
applications
apps
appserver
aq
ar
archie
arcsight
argentina
arizona
arkansas
arlington
as
as400
asia
asterix
at
athena
atlanta
atlas
att
au
auction
austin
auth
auto
autodiscover 
```
{% endtab %}

{% tab title="Pass" %}
```
123456
password
12345678
qwerty
123456789
12345
1234
111111
1234567
dragon
123123
baseball
abc123
football
monkey
letmein
shadow
master
666666
qwertyuiop
123321
mustang
1234567890
michael
654321
superman
1qaz2wsx
7777777
121212
000000
qazwsx
123qwe
killer
trustno1
jordan
jennifer
zxcvbnm
asdfgh
hunter
buster
soccer
harley
batman
andrew
tigger
sunshine
iloveyou
2000
charlie
robert
thomas
hockey
ranger
daniel
starwars
klaster
112233
george
computer
michelle
jessica
pepper
1111
zxcvbn
555555
11111111
131313
freedom
777777
pass
maggie
159753
aaaaaa
ginger
princess
joshua
cheese
amanda
summer
love
ashley
nicole
chelsea
biteme
matthew
access
yankees
987654321
dallas
austin
thunder
taylor
matrix
mobilemail
mom
monitor
monitoring
montana
moon
moscow 
```
{% endtab %}
{% endtabs %}

Dadas las dos listas de candidate usernames y pass hice un ataque con el intruder probando las correspondientes. No dio resultado exitoso pero si marca cual usuario existe

![](../../../.gitbook/assets/imagen%20%28659%29.png)

Con esto luego hacemos un ataque sniper para conseguir la contrase??a. 

It was cheese all along

![](../../../.gitbook/assets/imagen%20%28655%29.png)

