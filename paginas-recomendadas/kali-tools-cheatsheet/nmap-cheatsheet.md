# NMap Cheatsheet

Credito:

{% embed url="https://github.com/jasonniebauer/nmap-cheatsheet" %}

#### Command Line

```text
nmap [ <Scan Type> ...] [ <Options> ] { <target specification> }
```

### Basic Scanning Techniques

The `-s` switch determines the type of scan to perform.

| Nmap Switch | Description |
| :--- | :--- |
| **-sA** | ACK scan |
| **-sF** | FIN scan |
| **-sI** | IDLE scan |
| **-sL** | DNS scan \(a.k.a. list scan\) |
| **-sN** | NULL scan |
| **-sO** | Protocol scan |
| **-sP** | Ping scan |
| **-sR** | RPC scan |
| **-sS** | SYN scan |
| **-sT** | TCP connect scan |
| **-sW** | Windows scan |
| **-sX** | XMAS scan |

#### 

#### Scan a Single Target

```text
nmap [target]
```

#### Scan Multiple Targets

```text
nmap [target1, target2, etc]
```

#### Scan a List of Targets

```text
nmap -iL [list.txt]
```

#### Scan a Range of Hosts

```text
nmap [range of IP addresses]
```

#### Scan an Entire Subnet

```text
nmap [ip address/cdir]
```

#### Scan Random Hosts

```text
nmap -iR [number]
```

#### Exclude Targets From a Scan

```text
nmap [targets] --exclude [targets]
```

#### Exclude Targets Using a List

```text
nmap [targets] --excludefile [list.txt]
```

#### Perform an Aggresive Scan

```text
nmap -A [target]
```

#### Scan an IPv6 Target

```text
nmap -6 [target]
```

### 

### Port Scanning Options

#### Perform a Fast Scan

```text
nmap -F [target]
```

#### Scan Specific Ports

```text
nmap -p [port(s)] [target]
```

#### Scan Ports by Name

```text
nmap -p [port name(s)] [target]
```

#### Scan Ports by Protocol

```text
nmap -sU -sT -p U:[ports],T:[ports] [target]
```

#### Scan All Ports

```text
nmap -p 1-65535 [target]
```

#### Scan Top Ports

```text
nmap --top-ports [number] [target]
```

#### Perform a Sequential Port Scan

```text
nmap -r [target]
```

#### Attempt to Guess an Unknown OS

```text
nmap -O --osscan-guess [target]
```

#### Service Version Detection

```text
nmap -sV [target]
```

#### Troubleshoot Version Scan

```text
nmap -sV --version-trace [target]
```

#### Perform a RPC Scan

```text
nmap -sR [target]
```

### 

### Discovery Options

**Host Discovery** The `-p` switch determines the type of ping to perform.

| Nmap Switch | Description |
| :--- | :--- |
| **-PI** | ICMP ping |
| **-Po** | No ping |
| **-PS** | SYN ping |
| **-PT** | TCP ping |

#### 

#### Perform a Ping Only Scan

```text
nmap -sn [target]
```

#### Do Not Ping

```text
nmap -Pn [target]
```

#### TCP SYN Ping

```text
nmap -PS [target]
```

#### TCP ACK Ping

```text
nmap -PA [target]
```

#### UDP Ping

```text
nmap -PU [target]
```

#### SCTP INIT Ping

```text
nmap -PY [target]
```

#### ICMP Echo Ping

```text
nmap -PE [target]
```

#### ICMP Timestamp Ping

```text
nmap -PP [target]
```

#### ICMP Address Mask Ping

```text
nmap -PM [target]
```

#### IP Protocol Ping

```text
nmap -PO [target]
```

#### ARP ping

```text
nmap -PR [target]
```

#### Traceroute

```text
nmap --traceroute [target]
```

#### Force Reverse DNS Resolution

```text
nmap -R [target]
```

#### Disable Reverse DNS Resolution

```text
nmap -n [target]
```

#### Alternative DNS Lookup

```text
nmap --system-dns [target]
```

#### Manually Specify DNS Server

Can specify a single server or multiple.

```text
nmap --dns-servers [servers] [target]
```

#### Create a Host List

```text
nmap -sL [targets]
```

### Port Specification and Scan Order

| Nmap Switch | Description |
| :--- | :--- |


### Service/Version Detection

| Nmap Switch | Description |
| :--- | :--- |
| **-sV** | Enumerates software versions |

### Script Scan

| Nmap Switch | Description |
| :--- | :--- |
| **-sC** | Run all default scripts |

### OS Detection

| Nmap Switch | Description |
| :--- | :--- |


### Timing and Performance

The `-t` switch determines the speed and stealth performed.

| Nmap Switch | Description |
| :--- | :--- |
| **-T0** | Serial, slowest scan |
| **-T1** | Serial, slow scan |
| **-T2** | Serial, normal speed scan |
| **-T3** | Parallel, normal speed scan |
| **-T4** | Parallel, fast scan |

Not specifying a `T` value will default to `-T3`, or normal speed.

### Firewall Evasion Techniques

#### Firewall/IDS Evasion and Spoofing

| Nmap Switch | Description |
| :--- | :--- |


#### Fragment Packets

```text
nmap -f [target]
```

#### Specify a Specific MTU

```text
nmap --mtu [MTU] [target]
```

#### Use a Decoy

```text
nmap -D RND:[number] [target]
```

#### Idle Zombie Scan

```text
nmap -sI [zombie] [target]
```

#### Manually Specify a Source Port

```text
nmap --source-port [port] [target]
```

#### Append Random Data

```text
nmap --data-length [size] [target]
```

#### Randomize Target Scan Order

```text
nmap --randomize-hosts [target]
```

#### Spoof MAC Address

```text
nmap --spoof-mac [MAC|0|vendor] [target]
```

#### Send Bad Checksums

```text
nmap --badsum [target]
```

### Advanced Scanning Functions

#### TCP SYN Scan

```text
nmap -sS [target]
```

#### TCP Connect Scan

```text
nmap -sT [target]
```

#### UDP Scan

```text
nmap -sU [target]
```

#### TCP NULL Scan

```text
nmap -sN [target]
```

#### TCP FIN Scan

```text
nmap -sF [target]
```

#### Xmas Scan

```text
nmap -sA [target]
```

#### TCP ACK Scan

```text
nmap -sA [target]
```

#### Custom TCP Scan

```text
nmap --scanflags [flags] [target]
```

#### IP Protocol Scan

```text
nmap -sO [target]
```

#### Send Raw Ethernet Packets

```text
nmap --send-eth [target]
```

#### Send IP Packets

```text
nmap --send-ip [target]
```

### Timing Options

#### Timing Templates

```text
nmap -T[0-5] [target]
```

#### Set the Packet TTL

```text
nmap --ttl [time] [target]
```

#### Minimum NUmber of Parallel Operations

```text
nmap --min-parallelism [number] [target]
```

#### Maximum Number of Parallel Operations

```text
nmap --max-parallelism [number] [target]
```

#### Minimum Host Group Size

```text
nmap --min-hostgroup [number] [targets]
```

#### Maximum Host Group Size

```text
nmap --max-hostgroup [number] [targets]
```

#### Maximum RTT Timeout

```text
nmap --initial-rtt-timeout [time] [target]
```

#### Initial RTT Timeout

```text
nmap --max-rtt-timeout [TTL] [target]
```

#### Maximum Number of Retries

```text
nmap --max-retries [number] [target]
```

#### Host Timeout

```text
nmap --host-timeout [time] [target]
```

#### Minimum Scan Delay

```text
nmap --scan-delay [time] [target]
```

#### Maxmimum Scan Delay

```text
nmap --max-scan-delay [time] [target]
```

#### Minimum Packet Rate

```text
nmap --min-rate [number] [target]
```

#### Maximum Packet Rate

```text
nmap --max-rate [number] [target]
```

#### Defeat Reset Rate Limits

```text
nmap --defeat-rst-ratelimit [target]
```

### Output Options

| Nmap Switch | Description |
| :--- | :--- |
| `-oN` | Normal output |
| `-oX` | XML output |
| `-oA` | Normal, XML, and Grepable format all at once |

#### 

#### Save Output to a Text File

```text
nmap -oN [scan.txt] [target]
```

#### Save Output to a XML File

```text
nmap -oX [scan.xml] [target]
```

#### Grepable Output

```text
nmap -oG [scan.txt] [target]
```

#### Output All Supported File Types

```text
nmap -oA [path/filename] [target]
```

#### Periodically Display Statistics

```text
nmap --stats-every [time] [target]
```

#### 1337 Output

```text
nmap -oS [scan.txt] [target]
```

### 

### Compare Scans

#### Comparison Using Ndiff

```text
ndiff [scan1.xml] [scan2.xml]
```

#### Ndiff Verbose Mode

```text
ndiff -v [scan1.xml] [scan2.xml]
```

#### XML Output Mode

```text
ndiff --xml [scan1.xml] [scan2.xml]
```

### 

### Troubleshooting and Debugging

#### Get Help

```text
nmap -h
```

#### Display Nmap Version

```text
nmap -V
```

#### Verbose Output

```text
nmap -v [target]
```

#### Debugging

```text
nmap -d [target]
```

#### Display Port State Reason

```text
nmap --reason [target]
```

#### Only Display Open Ports

```text
nmap --open [target]
```

#### Trace Packets

```text
nmap --packet-trace [target]
```

#### Display Host Networking

```text
nmap --iflist
```

#### Specify a Network Interface

```text
nmap -e [interface] [target]
```

### 

### Nmap Scripting Engine

#### Execute Individual Scripts

```text
nmap --script [script.nse] [target]
```

#### Execute Multiple Scripts

```text
nmap --script [expression] [target]
```

#### Execute Scripts by Category

```text
nmap --script [category] [target]
```

#### Execute Multiple Script Categories

```text
nmap --script [category1,category2,etc]
```

#### Troubleshoot Scripts

```text
nmap --script [script] --script-trace [target]
```

#### Update the Script Database

```text
nmap --script-updatedb
```

**Reference Sites**

*  [Nmap - The Basics](https://www.youtube.com/watch?v=_JvtO-oe8k8)
*  [Reference link 1](https://hackertarget.com/nmap-cheatsheet-a-quick-reference-guide/)
*  [Beginner's Guide to Nmap](https://www.linux.com/learn/beginners-guide-nmap)
*  [Top 32 Nmap Command](https://www.cyberciti.biz/security/nmap-command-examples-tutorials/)
*  [Nmap Linux man page](https://linux.die.net/man/1/nmap)
*  [29 Practical Examples of Nmap Commands](https://www.tecmint.com/nmap-command-examples/)
*  [Nmap Scanning Types, Scanning Commands , NSE Scripts](https://medium.com/@infosecsanyam/nmap-cheat-sheet-nmap-scanning-types-scanning-commands-nse-scripts-868a7bd7f692)
*  [Nmap CheatSheet](https://www.cheatography.com/netwrkspider/cheat-sheets/nmap-cheatsheet/)
*  [Nmap Cheat Sheet](https://highon.coffee/blog/nmap-cheat-sheet/)
*  [Nmap Cheat Sheet: From Discovery to Exploits](https://resources.infosecinstitute.com/nmap-cheat-sheet/)
*  [Nmap: my own cheatsheet](https://www.andreafortuna.org/2018/03/12/nmap-my-own-cheatsheet/)
*  [NMAP Commands Cheatsheet](https://hackersonlineclub.com/nmap-commands-cheatsheet/)
*  [Nmap Cheat Sheet](https://www.stationx.net/nmap-cheat-sheet/)
*  [Nmap Cheat Sheet](http://nmapcookbook.blogspot.com/2010/02/nmap-cheat-sheet.html)

