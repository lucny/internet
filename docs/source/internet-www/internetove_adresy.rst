Internetové adresy
==================

.. contents:: Obsah
    :depth: 3

IP adresy
---------
Co je IP adresa?
~~~~~~~~~~~~~~~~
Každý počítač připojený k Internetu má svoji IP adresu. 
**IP adresa** (anglicky *IP address*) je v informatice číslo, které jednoznačně identifikuje síťové rozhraní v počítačové síti, v níž se používá **IP protokol**.

.. figure:: media/ip-adresy.jpg
    :alt: IP adresy
    :figclass: center

IP adresy jsou unikátní identifikátory síťového rozhraní

Verze IP adres
~~~~~~~~~~~~~~
Tradiční IP adresa verze 4 (*IPv4*) je *32bitový údaj*, který se zapisuje jako 4 desítková čísla v rozmezí 0 – 255 oddělená tečkou (např. ``192.168.1.1``). 
Každé z těchto 4 čísel reprezentuje osm bitů adresy (*octet*). 

IP adresu tvoří vždy **adresa sítě a podsítě** (*network address*) a **adresa síťového rozhraní** (*host address*). 
Síťová část adresy je pro množinu počítačů v jedné síti (např. LAN v učebně) společná, jedinečnost každého zařízení pak zajišťuje přidělená adresa síťového rozhraní. 

    Celkový počet různých IP adres je 2:sup:`32` = 4 294 967 296. Rozsah použitelných adres se nazývá **adresní prostor**. 

.. admonition:: Proč IPv4 nedostačuje?
    :class: zajimavost

    Adresní prostor IPv4 však nikdy nebude obsahovat 4 miliardy adres, protože určitá jeho část je rezervována pro jiné potřeby protokolu a nemohou být použity. 
    Dále jsou z praktických důvodů IP adresy shlukovány do větších celků, čímž se adresní prostor dále zmenšuje. 
    V souvislosti s prudkým rozmachem počítačů v domácnostech to vedlo k vyčerpání IPv4 adres.  
    
Z důvodu nedostatku adres je IPv4 postupně nahrazován protokolem **IP verze 6** (*IPv6*), 
který používá *128bitové* IP adresy zapsané hexadecimálně, například ``2001:db8:0:1234:0:567:8:1``.

.. admonition:: Víte, že...
    :class: vite-ze

    - První IP adresa byla přidělena v roce 1981 a byla použita pro testovací účely. První veřejná IP adresa byla přidělena v roce 1983.
    - V roce 2011 bylo přiděleno posledních 5 bloků IPv4 adres. V roce 2015 byl vyčerpán zásobník adres u IANA (Internet Assigned Numbers Authority), který přiděluje adresy regionálním registrům.
    - V roce 2012 byl přidělen první blok IPv6 adres. V roce 2016 bylo přiděleno 10 % adresního prostoru IPv6.
    - IPv6 adresy jsou zapisovány jako osm skupin čtyř hexadecimálních číslic oddělených dvojtečkou. Pokud některé skupiny obsahují nuly, mohou být vynechány. Například adresa ``2001:0db8:0000:0000:0000:0000:0000:0001`` může být zkrácena na ``2001:db8::1``.
    - V roce 2021 bylo 40 % provozu na Internetu zprostředkováno pomocí IPv6. V České republice byl podíl provozu na Internetu pomocí IPv6 v roce 2021 přibližně 30 %.

.. admonition:: Co je to IANA?
    :class: zajimavost

    IANA (*Internet Assigned Numbers Authority*) je organizace, která je zodpovědná za koordinaci některých klíčových prvků Internetu, jako jsou například adresy IP, doménová jména a čísla portů. IANA je součástí organizace ICANN (*Internet Corporation for Assigned Names and Numbers*), která je zodpovědná za celkovou správu Internetu. Více informací najdete na `stránkách IANA <https://www.iana.org/>`_.

Doménová jména
--------------
Co jsou doménová jména?
~~~~~~~~~~~~~~~~~~~~~~~
Pro označování zdrojů na internetu se nepoužívají IP adresy, ale tzv. **doménová jména**, aby byla pro člověka lépe zapamatovatelná (např. `cs.wikipedia.org`). 
Tato jména se pak převádějí na IP adresy pomocí **DNS** (*Domain Name System*).

.. figure:: media/dns.jpg
    :alt: Doménová jména
    :figclass: center

Doménová jména a DNS

DNS
~~~
**DNS** (*Domain Name System*) je hierarchický distribuovaný systém doménových jmen, který je realizován servery DNS a protokolem stejného jména, 
jehož prostřednictvím si tyto servery vyměňují informace. 

Hlavním úkolem služby DNS je k zadanému doménovému jménu najít odpovídající IP adresu a tu poskytnout některé z internetových služeb 
k navázání komunikačního spojení pomocí protokolů TCP/IP.

K ověření funkčnosti systému DNS slouží řádková utilita nslookup. Pomocí ní lze ověřit, zda je doménové jméno správně přeloženo na IP adresu.

.. code-block:: bash

    nslookup www.google.com

    Server:  UnKnown
    Address:  fe80::1

    Non-authoritative answer:
    Name:    www.google.com
    Addresses:  2a00:1450:4014:80b::2004
            142.251.37.100

Struktura doménových jmen
~~~~~~~~~~~~~~~~~~~~~~~~~
Prostor doménových jmen tvoří strom. V kořeni tohoto stromu je speciální vyhrazené prázdné doménové jméno. 
Pod tímto kořenem jsou uspořádány všechny domény nejvyššího řádu. V další úrovni jsou domény 2. úrovně atd.

Doménová jména jsou zapisována zpravidla zprava doleva, přičemž jednotlivé úrovně jsou odděleny tečkou. Například doménové jméno ``www.google.com`` má tři úrovně - ``com`` (doména nejvyššího řádu), ``google`` (doména 2. řádu) a ``www`` (doména 3. řádu).

Domény nejvyššího řádu
~~~~~~~~~~~~~~~~~~~~~~
Domény nejvyššího řádu (Top Level Domain = TLD) dělíme na obecné (generické, gTLD) - například .com, .net, .org, .edu, … a národní (ccTLD) - například .cz, .sk, .de, .ru, … 

Domény nejvyššího řádu jsou spravovány organizací ICANN (*Internet Corporation for Assigned Names and Numbers*). ICANN je zodpovědná za celkovou správu Internetu, včetně správy doménových jmen.

Domény 2. řádu
~~~~~~~~~~~~~~
Pro získání doménového jména je nutné se obrátit na doménového registrátora, který je oprávněn přidělovat doménová jména v rámci určité domény nejvyššího řádu. 
V České republice je doménovým registrátorem pro doménu ``.cz`` organizace CZ.NIC, která je zodpovědná za správu doménových jmen v České republice.

Přidělování a správa doménových jmen je stejně tak hierarchická. Např. správce domény wikipedia.org rozhoduje o přidělování domén 3. řádu končících na .wikipedia.org, 
aniž by musel toto přidělování konzultovat se správcem domény org.

.. admonition:: Víte, že...
    :class: vite-ze

    - První návrh systému doménových jmen byl publikován v roce 1983. V roce 1984 byl zaveden první doménový registr - ``.com``.
    - V roce 1985 byl zaveden doménový registr ``.cz``. V roce 1990 byl zaveden doménový registr ``.sk``.
    - V roce 1998 byla založena organizace ICANN, která je zodpovědná za celkovou správu Internetu, včetně správy doménových jmen.
    - V roce 2014 bylo zavedeno první doménové jméno s diakritikou - ``.cz``.
    - V roce 2021 bylo celosvětově registrováno přibližně 370 milionů doménových jmen. Nejvíce doménových jmen je registrováno v doménovém registrů ``.com``, ``.net`` a ``.org``.

URL
---
Co je URL?
~~~~~~~~~~
**URL** (*Uniform Resource Locator*) je adresa zdroje na internetu. URL se skládá z několika částí, které určují, 
jakým způsobem se má zdroj na internetu lokalizovat a jakým způsobem se má s ním pracovat.

URL se používá pro identifikaci zdrojů na internetu, jako jsou například webové stránky, obrázky, dokumenty, multimediální soubory, atd.

.. figure:: media/url.jpg
    :alt: URL
    :figclass: center

URL jako adresa zdroje na internetu

Struktura URL
~~~~~~~~~~~~~
URL se skládá z několika částí, které jsou odděleny dvojtečkou a dvěma lomítky.

URL definuje doménovou adresu serveru, umístění zdroje na serveru a protokol, kterým je možné zdroj zpřístupnit.

Příklad pro WWW stránku: ``http://cs.wikipedia.org:80/w/wiki.phtml?title=URL&action=edit``

- **Schéma**: `http` – protokol pro prohlížení webových stránek
- **Hierarchická část**: DNS serveru (`cs.wikipedia.org`), označení portu (`80` – jde o implicitní port protokolu HTTP, proto ho není ho třeba v tomto konkrétním případě uvádět), cesta k dokumentu (`/w/wiki.phtml`).
- **Dotaz**: první parametr se jménem `title`` a hodnotou `URL`, druhý se jménem `action`` a hodnotou `edit`.

.. admonition:: Víte, že...
    :class: zajimavost

    Pomocí URL lze zadat také autentizační informace: mezi protokol a doménové jméno je možno vložit uživatelské jméno a případně i heslo oddělená navzájem dvojtečkou a od následující domény zavináčem:
    
    ``ftp://student:00000@192.168.10.200/IT4/``

    Tento zápis umožňuje přihlášení na FTP server s IP adresou 192.168.10.200 pomocí uživatelského jména `student` a hesla `00000`. Uživateli se otevře složka `IT4`.

.. admonition:: Doporučené odkazy
    :class: doporucene-odkazy 

    Další informace o adresování na Internetu můžete najít na následujících webových stránkách:
    
    - `Internet Society <https://www.internetsociety.org/>`_
    - `World Wide Web Consortium (W3C) <https://www.w3.org/>`_
    - `The History of the Internet <https://www.history.com/topics/inventions/invention-of-the-internet>`_
    - `How Does the Internet Work? <https://www.cloudflare.com/learning/ddos/glossary/how-does-the-internet-work/>`_
    - `Internet Engineering Task Force (IETF) <https://www.ietf.org/>`_
