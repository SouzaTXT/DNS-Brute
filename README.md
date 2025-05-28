<div align="start">
<h1> DNS Brute.py - A Brute Force DNS code </h1>
</div>

#### Yep, another pentest script made in [Python 3](https://www.python.org/downloads/release/python-370/). This time I decided to create a Brute Force DNS code, I used the ***dns.resolver toolkit***. 🔗

```
import dns.resolver 

res = dns.resolver.Resolver()
arquivo = open("/home/kali/wordlist.txt", "r")
subdominios = arquivo.read().splitlines()

alvo = "bancocn.com"

for subdominio in subdominios:
    try:
        sub_alvo = subdominio + "." + alvo
        resultado = res.resolve(sub_alvo, "A")
        for ip in resultado:
            print(sub_alvo, "->", ip)
    except:    
        pass

```
+ **[Click here to check the toolkit link](https://github.com/rthalley/dnspython)** 

<h1> How it works: </h1>

So, you add the website that you want at the ```alvo``` variable, in the example here, it's say ```"bancocn.com"``` (I explain why at the ***"A Pratical Example"*** topic ⬇). After that, when you run the code, it will use the subdomains texts form the wordlist.txt archive, returning all possible sites together with the subdomain and IP protocol.
<br>
<br>

 **OBS:** That's a Brute Force Attack, so, if it return nothing, you can add new subdomains and try then whenever you want. ⚠

<h1>A pratical example: </h1>


![layout example](https://github.com/user-attachments/assets/91433b73-8adb-4582-8954-fe75a40d21ab)



In this case, I'm using  ```"bancocn.com"``` website, which is provided by the course **[Introdução ao Hacking e Pentest 2.0 by Solid Offensive Security](https://solyd.com.br/aluno/)** that I'm currently using to learn about Pentesting pratices. 

That's all, thanks for reading! 🖤



