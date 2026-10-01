<div align="center">

# Free Proxy List

**HTTP, SOCKS4 and SOCKS5 proxies that worked less than an hour ago – checked, not just scraped.**

![working proxies](https://img.shields.io/badge/working%20proxies-1%2C059-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-391-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-191-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-477-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--10--01%2014:38%20UTC-grey?style=flat-square&labelColor=121113)

[![Stars of the tool](https://img.shields.io/github/stars/maximilianfeix/proxy-scraper?style=social&label=proxy-scraper)](https://github.com/maximilianfeix/proxy-scraper)

[Download](#download) · [Quick start](#quick-start) · [By country](#by-country) · [Why this list](#why-this-list) · [Website](https://maximilianfeix.github.io/proxy-scraper/) · [The tool](https://github.com/maximilianfeix/proxy-scraper)

</div>

---

Updated **every hour** by [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper). It pulls candidates from 700+ public sources and keeps only the ones that pass every check – a real handshake, two sites through the same exit IP, nothing injected into the page, TLS that verifies. Most free lists are 95 % dead; this one is re-checked from scratch every run.

**Last run:** 2026-10-01 14:38 UTC · **1,059** working proxies · **537** HTTPS-capable · median latency **1,481 ms** · median download **71 KB/s** · 69 countries

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
| All proxies | `type://ip:port` | 1,059 | [all.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) |
| HTTP | `ip:port` | 391 | [http.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) |
| SOCKS4 | `ip:port` | 191 | [socks4.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) |
| SOCKS5 | `ip:port` | 477 | [socks5.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 537 | [https.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 1,030 | [elite.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 92 | [stable.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 1,059 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
| 🇺🇸 United States | 232 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇨🇳 China | 185 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇩🇪 Germany | 85 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) |
| 🇧🇷 Brazil | 44 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇳🇱 Netherlands | 43 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) | 🇮🇳 India | 39 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) |
| 🇻🇳 Vietnam | 37 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇸🇬 Singapore | 30 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) | 🇷🇺 Russia | 29 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) |
| 🇭🇰 Hong Kong | 25 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇦🇺 Australia | 22 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) | 🇰🇷 South Korea | 20 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) |
| 🇮🇩 Indonesia | 19 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇨🇦 Canada | 17 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇪🇸 Spain | 17 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) |
| 🇫🇷 France | 15 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇯🇵 Japan | 15 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇮🇱 Israel | 14 | [il.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/il.txt) |
| 🇰🇭 Cambodia | 12 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇦🇹 Austria | 10 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇹🇼 Taiwan | 10 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) |
| 🇧🇬 Bulgaria | 9 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇧🇩 Bangladesh | 8 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇫🇮 Finland | 8 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) |
| 🇵🇱 Poland | 8 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇺🇦 Ukraine | 8 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇲🇾 Malaysia | 7 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) |
| 🇹🇭 Thailand | 7 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) | 🇬🇧 United Kingdom | 6 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇨🇭 Switzerland | 4 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) |
| 🇨🇿 Czechia | 4 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇲🇱 Mali | 4 | [ml.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ml.txt) | 🇿🇦 South Africa | 4 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) |
| 🇧🇮 Burundi | 3 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) | 🇨🇱 Chile | 3 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) | 🇨🇴 Colombia | 3 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) |
| 🇮🇹 Italy | 3 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) | 🇵🇰 Pakistan | 3 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇷🇴 Romania | 3 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) |
| 🇦🇪 United Arab Emirates | 2 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇪🇨 Ecuador | 2 | [ec.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ec.txt) | 🇭🇺 Hungary | 2 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) |
| 🇮🇶 Iraq | 2 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇮🇷 Iran | 2 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇰🇪 Kenya | 2 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) |
| 🇱🇷 Liberia | 2 | [lr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lr.txt) | 🇱🇹 Lithuania | 2 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) | 🇲🇽 Mexico | 2 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) |
| 🇳🇬 Nigeria | 2 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇭 Philippines | 2 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇷🇸 Serbia | 2 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) |
| 🇸🇪 Sweden | 2 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇹🇷 Turkey | 2 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇦🇱 Albania | 1 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇦🇷 Argentina | 1 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇦🇿 Azerbaijan | 1 | [az.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/az.txt) | 🇧🇼 BW | 1 | [bw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bw.txt) |
| 🇨🇲 CM | 1 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) | 🇪🇪 Estonia | 1 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇪🇬 Egypt | 1 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) |
| 🇲🇦 Morocco | 1 | [ma.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ma.txt) | 🇲🇪 ME | 1 | [me.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/me.txt) | 🇲🇺 MU | 1 | [mu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mu.txt) |
| 🇲🇿 Mozambique | 1 | [mz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mz.txt) | 🇳🇵 Nepal | 1 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇵🇸 PS | 1 | [ps.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ps.txt) |
| 🇸🇳 Senegal | 1 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) | 🇺🇿 UZ | 1 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) | 🇿🇼 ZW | 1 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 171 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 127 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 102 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 114 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 273 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |

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
