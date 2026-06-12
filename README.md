# cockpit-charontak — manage your CoT bridge & TAK Server lanes in the browser

A [Cockpit](https://cockpit-project.org/) web console plugin for
[Charontak](https://github.com/snstac/charontak), the **Cursor on Target (CoT) bridge**
that concentrates your sensor fleet's traffic into **one TLS session to TAK Server**
(plus Mesh SA fan-out). Control the `charontak` service, edit `/etc/charontak.ini`
lanes, and tail the journal — no SSH required. Part of the TAK / ATAK / WinTAK
situational-awareness stack for Raspberry Pi and Debian sensor gateways.

## Install

```sh
sudo curl -fsSL -o /usr/share/keyrings/snstac.gpg https://snstac.github.io/packages/snstac.gpg
sudo curl -fsSL -o /etc/apt/sources.list.d/snstac.sources https://snstac.github.io/packages/snstac.sources
sudo apt update && sudo apt install cockpit-charontak charontak
```

## The snstac TAK sensor ecosystem

Different sensor, same workflow — pick the gateway for your application; most have a
matching Cockpit plugin for browser-based management:

| Application | Gateway | Cockpit plugin |
|---|---|---|
| Aircraft via ADS-B (1090 MHz / 978 MHz UAT) | [adsbcot](https://github.com/snstac/adsbcot) | [cockpit-adsbcot](https://github.com/snstac/cockpit-adsbcot) |
| Ships & vessels via AIS | [aiscot](https://github.com/snstac/aiscot) | [cockpit-aiscot](https://github.com/snstac/cockpit-aiscot), [cockpit-aiscatcher](https://github.com/snstac/cockpit-aiscatcher) |
| Drone / UAS Remote ID (counter-UAS) | [dronecot](https://github.com/snstac/dronecot) | [cockpit-dronecot](https://github.com/snstac/cockpit-dronecot) |
| Own position via GPS/GNSS | [lincot](https://github.com/snstac/lincot) | [cockpit-lincot](https://github.com/snstac/cockpit-lincot), [cockpit-gps](https://github.com/snstac/cockpit-gps) |
| Radio direction finding (KrakenSDR) | [kraktak](https://github.com/snstac/kraktak) | — |
| APRS amateur radio | [aprscot](https://github.com/snstac/aprscot) | — |
| Weather stations | [windtak](https://github.com/snstac/windtak) | — |
| CoT routing / TAK Server bridging | [charontak](https://github.com/snstac/charontak) | — |

All gateways are built on [PyTAK](https://github.com/snstac/pytak), speak
**Cursor on Target (CoT)** to **ATAK, WinTAK, iTAK, TAK Server, and Mesh SA**, ship as
signed Debian/RPM packages at [snstac.github.io/packages](https://snstac.github.io/packages),
and come pre-installed on [AryaOS](https://github.com/snstac/aryaos), the
situational-awareness OS for Raspberry Pi.
