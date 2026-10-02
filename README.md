<div align="center">

# Free Proxy List

**HTTP, SOCKS4 and SOCKS5 proxies that worked less than an hour ago – checked, not just scraped.**

![working proxies](https://img.shields.io/badge/working%20proxies-1%2C488-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-367-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-302-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-819-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--10--02%2003:40%20UTC-grey?style=flat-square&labelColor=121113)

[![Stars of the tool](https://img.shields.io/github/stars/maximilianfeix/proxy-scraper?style=social&label=proxy-scraper)](https://github.com/maximilianfeix/proxy-scraper)

[Download](#download) · [Quick start](#quick-start) · [By country](#by-country) · [Why this list](#why-this-list) · [Website](https://maximilianfeix.github.io/proxy-scraper/) · [The tool](https://github.com/maximilianfeix/proxy-scraper)

</div>

---

Updated **every hour** by [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper). It pulls candidates from 700+ public sources and keeps only the ones that pass every check – a real handshake, two sites through the same exit IP, nothing injected into the page, TLS that verifies. Most free lists are 95 % dead; this one is re-checked from scratch every run.

**Last run:** 2026-10-02 03:40 UTC · **1,488** working proxies · **820** HTTPS-capable · median latency **1,572 ms** · median download **70 KB/s** · 83 countries

<a href="https://maximilianfeix.github.io/proxy-scraper/"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://maximilianfeix.github.io/proxy-scraper/chart-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://maximilianfeix.github.io/proxy-scraper/chart-light.svg">
  <img src="https://maximilianfeix.github.io/proxy-scraper/chart-dark.svg" alt="Working proxies over the last days, by protocol" width="100%">
</picture></a>

<a id="download"></a>

## Download

Every file is sorted **best first** – by first answer plus measured download speed – so `head -n 20` gives you the good ones.

| List | Format | Proxies | Link |
|---|---|---:|---|
| All proxies | `type://ip:port` | 1,488 | [all.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) |
| HTTP | `ip:port` | 367 | [http.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) |
| SOCKS4 | `ip:port` | 302 | [socks4.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) |
| SOCKS5 | `ip:port` | 819 | [socks5.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 820 | [https.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 1,460 | [elite.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 100 | [stable.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 1,488 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

Need CORS, or hitting the raw.githubusercontent rate limit? The same lists are on [GitHub Pages](https://maximilianfeix.github.io/proxy-scraper/) (e.g. `https://maximilianfeix.github.io/proxy-scraper/socks5.txt`), where you can also search and filter them.

<a id="quick-start"></a>

## Quick start

```bash
curl -sL https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt | head -n 20
```

```python
import requests  # pip install "requests[socks]"

proxies = requests.get("https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt", timeout=10).text.split()
for proxy in proxies[:20]:  # best first
    try:
        r = requests.get("https://api.ipify.org", proxies={"http": proxy, "https": proxy}, timeout=10)
        print(proxy, "->", r.text)
        break
    except requests.RequestException:
        continue
```

Or let [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper) do the rotating and retrying for you:

```bash
pip install proxy-scraper-cli
proxy-scraper --recheck live          # re-check this list from your own network (~30 s)
proxy-scraper --recheck live --serve  # ... and run it as one rotating local proxy
```

```python
from proxyscraper import ProxyRotator

with ProxyRotator(country="DE") as rotator:
    print(rotator.get("https://httpbin.org/ip").text)
```

<a id="by-country"></a>

## By country

| Country | Proxies | List | Country | Proxies | List | Country | Proxies | List |
| ---|---:|--- | ---|---:|--- | ---|---:|--- |
| 🇺🇸 United States | 412 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇩🇪 Germany | 148 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) | 🇮🇳 India | 116 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) |
| 🇨🇳 China | 76 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇧🇷 Brazil | 75 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇦🇺 Australia | 59 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) |
| 🇭🇰 Hong Kong | 50 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇷🇺 Russia | 48 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) | 🇳🇱 Netherlands | 42 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) |
| 🇫🇷 France | 40 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇫🇮 Finland | 36 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) | 🇮🇩 Indonesia | 28 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) |
| 🇻🇳 Vietnam | 22 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇧🇮 Burundi | 21 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) | 🇨🇦 Canada | 18 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) |
| 🇹🇼 Taiwan | 17 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) | 🇧🇩 Bangladesh | 16 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇧🇬 Bulgaria | 16 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) |
| 🇯🇵 Japan | 16 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇰🇷 South Korea | 14 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) | 🇺🇦 Ukraine | 14 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) |
| 🇹🇭 Thailand | 13 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) | 🇰🇭 Cambodia | 12 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇬🇧 United Kingdom | 11 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) |
| 🇮🇱 Israel | 11 | [il.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/il.txt) | 🇵🇱 Poland | 11 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇱🇹 Lithuania | 10 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) |
| 🇸🇬 Singapore | 10 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) | 🇨🇴 Colombia | 9 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇲🇾 Malaysia | 7 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) |
| 🇪🇸 Spain | 6 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇸🇪 Sweden | 6 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇿🇦 South Africa | 6 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) |
| 🇨🇭 Switzerland | 5 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇨🇿 Czechia | 5 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇲🇦 Morocco | 5 | [ma.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ma.txt) |
| 🇨🇱 Chile | 4 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) | 🇦🇹 Austria | 3 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇬🇭 Ghana | 3 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) |
| 🇭🇺 Hungary | 3 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) | 🇮🇹 Italy | 3 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) | 🇵🇸 PS | 3 | [ps.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ps.txt) |
| 🇷🇴 Romania | 3 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) | 🇦🇷 Argentina | 2 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇦🇿 Azerbaijan | 2 | [az.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/az.txt) |
| 🇪🇨 Ecuador | 2 | [ec.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ec.txt) | 🇪🇪 Estonia | 2 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇬🇷 Greece | 2 | [gr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gr.txt) |
| 🇭🇷 Croatia | 2 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) | 🇮🇶 Iraq | 2 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇱🇻 Latvia | 2 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) |
| 🇲🇴 Macao | 2 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇳🇬 Nigeria | 2 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇭 Philippines | 2 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) |
| 🇵🇰 Pakistan | 2 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇸🇳 Senegal | 2 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) | 🇾🇪 YE | 2 | [ye.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ye.txt) |
| 🇿🇼 ZW | 2 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) | 🇦🇪 United Arab Emirates | 1 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇦🇫 AF | 1 | [af.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/af.txt) |
| 🇧🇪 Belgium | 1 | [be.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/be.txt) | 🇩🇰 Denmark | 1 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) | 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) |
| 🇭🇳 Honduras | 1 | [hn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hn.txt) | 🇮🇷 Iran | 1 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇯🇲 JM | 1 | [jm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jm.txt) |
| 🇱🇸 LS | 1 | [ls.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ls.txt) | 🇲🇰 North Macedonia | 1 | [mk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mk.txt) | 🇲🇲 MM | 1 | [mm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mm.txt) |
| 🇲🇹 MT | 1 | [mt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mt.txt) | 🇲🇺 MU | 1 | [mu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mu.txt) | 🇲🇼 MW | 1 | [mw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mw.txt) |
| 🇲🇽 Mexico | 1 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) | 🇲🇿 Mozambique | 1 | [mz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mz.txt) | 🇳🇴 Norway | 1 | [no.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/no.txt) |
| 🇵🇦 PA | 1 | [pa.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pa.txt) | 🇵🇪 Peru | 1 | [pe.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pe.txt) | 🇵🇷 PR | 1 | [pr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pr.txt) |
| 🇵🇾 Paraguay | 1 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇷🇸 Serbia | 1 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) | 🇹🇷 Turkey | 1 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) |
| 🇺🇬 UG | 1 | [ug.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ug.txt) | 🇺🇾 UY | 1 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) |  | |  |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 270 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 265 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 116 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 169 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 465 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |

<a id="why-this-list"></a>

## Why this list

- **Checked, not collected.** Every proxy had to complete a real protocol handshake and load two different sites through the same exit IP in the last run.
- **No honeypots, no injected scripts.** Pages that come back modified are thrown out; HTTPS counts only with a certificate that verifies.
- **Best first.** Sorted by how fast pages actually load, not by a single ping.
- **Details for every proxy** in `proxies.json`: exit IP, country, ASN and provider, datacenter or not, anonymity, latency, download speed, uptime over 24 hours and 7 days, first seen, and which big sites it gets through to.
- **Honest about uptime.** `stable.txt` holds only proxies that were on the list in 90 %+ of this week's hourly runs.

Want more than a list? **[proxy-scraper](https://github.com/maximilianfeix/proxy-scraper)** is the open-source tool behind it: scan from your own network, filter by country, protocol and site, a rotating proxy server, a Python API and an MCP server for AI agents. If this list saves you time, a ⭐ on [the tool](https://github.com/maximilianfeix/proxy-scraper) helps others find it.

## Good to know

- **Updates:** every hour, about 20 minutes past. A run with too few hits is skipped – the last good list stays.
- **History:** the git history is squashed at the start of every month so clones stay small. A daily archive of `proxies.json` lives in the [snapshot releases](https://github.com/maximilianfeix/proxy-scraper/releases?q=snapshots).
- **Found a problem?** Please open an issue in the [tool repository](https://github.com/maximilianfeix/proxy-scraper/issues).

> [!WARNING]
> Public proxies are run by strangers. Never send passwords or personal data through them, and use them only for things you're allowed to do.
