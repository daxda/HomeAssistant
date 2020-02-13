# Il mio Home Assistant
In questa repo mantango una copia di backup della mia configurazione di Home Assistant:


### Le mie schede
## Home
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_1.png)
## Controllo Consumi
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_2.png)

## Allarme
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_3.png)

## Automazioni e scene
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_4.png)
## Meteo
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_5.png)
## Mediaplayer
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_6.png)
## Garden
Questa scheda non è farina del mio sacco, ma è un riadattamento del pakages che trovate su questo Git ** https://github.com/kloggy/Home-Assistant ** ( thank you very much to @klogg for his gigantic work, and for his availability)
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_7.png)

## Utility
![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/screenshot/page_8.png)

## Studio
Tutte le entity di questa scheda si trovano in un'altra installazione di Home Assitant ( su un rasberry nel mio studio )  vengono importate e controllate  nella mia installazione principale con il custom component ** https://github.com/lukas-hetzenecker/home-assistant-remote **

![SchedaHome](https://github.com/daxda/HomeAssistante/raw/master/Screenshot/page_9.png)


### La mia installazione
Come server domestico utilizzo un [Intel NUC6CAYH ](https://sagg.it/2OdhJ5P) con 8 GB di RAM, 120 GB di SSD  ed una scheda di rete USB 3 aggiuntiva. [Proxmox](https://www.proxmox.com/en/) come sistema operativo mi permette di gestire  VM e CT , tra cui:
* [pfSense](https://www.pfsense.org) che utilizzo come Firewall e router
* un sistema Linux [Debian](https://www.debian.org) con [Docker](https://www.docker.com), su cui tra gli altri gira HomeAssistant a [questa pagina](https://www.saggiamente.com/2019/03/configurare-un-nuc-con-proxmox-ed-hassio-trasferendo-anche-la-configurazione-da-un-raspberry/) c'è la guda ho scritto per installare Home Assistant su una VM in Proxmox
In estrema sintesi ( dopo aver installato debian su una VM con minimo 2 GB di ram  )
```
apt-get install jq curl dbus socat bash avahi-daemon
apt-get install -y apt-transport-https ca-certificates wget software-properties-common
wget https://download.docker.com/linux/debian/gpg
apt-key add gpg
echo "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | tee -a /etc/apt/sources.list.d/docker.list
apt-get update
apt-get -y install docker-ce

curl -sL "https://raw.githubusercontent.com/home-assistant/hassio-installer/master/hassio_install.sh" | bash -s -- -m intel-nuc

```

### I miei dispositivi smart
