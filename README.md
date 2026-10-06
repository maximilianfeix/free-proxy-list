<div align="center">

# Free Proxy List

**HTTP, SOCKS4 and SOCKS5 proxies that worked less than an hour ago – checked, not just scraped.**

![working proxies](https://img.shields.io/badge/working%20proxies-1%2C028-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-303-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-267-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-458-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--10--06%2012:47%20UTC-grey?style=flat-square&labelColor=121113)

[![Stars of the tool](https://img.shields.io/github/stars/maximilianfeix/proxy-scraper?style=social&label=proxy-scraper)](https://github.com/maximilianfeix/proxy-scraper)

[Download](#download) · [Quick start](#quick-start) · [By country](#by-country) · [Why this list](#why-this-list) · [Website](https://maximilianfeix.github.io/proxy-scraper/) · [The tool](https://github.com/maximilianfeix/proxy-scraper)

</div>

---

Updated **every hour** by [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper). It pulls candidates from 700+ public sources and keeps only the ones that pass every check – a real handshake, two sites through the same exit IP, nothing injected into the page, TLS that verifies. Most free lists are 95 % dead; this one is re-checked from scratch every run.

**Last run:** 2026-10-06 12:47 UTC · **1,028** working proxies · **452** HTTPS-capable · median latency **1,703 ms** · median download **58 KB/s** · 75 countries

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
| All proxies | `type://ip:port` | 1,028 | [all.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) |
| HTTP | `ip:port` | 303 | [http.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) |
| SOCKS4 | `ip:port` | 267 | [socks4.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) |
| SOCKS5 | `ip:port` | 458 | [socks5.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 452 | [https.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 991 | [elite.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 179 | [stable.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 1,028 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

Need CORS, or hitting the raw.githubusercontent rate limit? The same lists are on [GitHub Pages](https://maximilianfeix.github.io/proxy-scraper/) (e.g. `https://maximilianfeix.github.io/proxy-scraper/socks5.txt`), where you can also search and filter them.

<a id="quick-start"></a>

## Quick start

```bash
curl -sL https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt | head -n 20
```

### Python

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

### Node.js

```javascript
// needs "type": "module" in package.json or .mjs
import { fetch, ProxyAgent } from 'undici';  // npm install undici
// Note: ProxyAgent only speaks HTTP(S) proxies; socks4:// and socks5:// lines will be skipped by the loop

const response = await fetch("https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt");
const proxies = (await response.text()).split("\n");
for (const proxy of proxies.slice(0, 20)) {
    try {
        const r = await fetch("https://api.ipify.org", {
            dispatcher: new ProxyAgent(proxy.trim()),
            signal: AbortSignal.timeout(10_000)
        });
        console.log(proxy.trim(), "->", await r.text());
        break;
    } catch {}
}
```

### Go

```go
package main

import (
	"fmt"
	"io"
	"net/http"
	"net/url"
	"strings"
	"time"
)

func main() {
	resp, err := http.Get("https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt")
	if err != nil {
		return
	}
	defer resp.Body.Close()
	body, _ := io.ReadAll(resp.Body)
	proxies := strings.Fields(string(body))
	if len(proxies) > 20 {
		proxies = proxies[:20]
	}
	for _, proxy := range proxies {
		proxyURL, err := url.Parse(proxy)
		if err != nil {
			continue
		}
		client := &http.Client{
			Timeout:   10 * time.Second,
			Transport: &http.Transport{Proxy: http.ProxyURL(proxyURL)},
		}
		if r, err := client.Get("https://api.ipify.org"); err == nil {
			ip, _ := io.ReadAll(r.Body)
			r.Body.Close()
			fmt.Printf("%s -> %s\n", proxy, ip)
			break
		}
	}
}
```

### curl

```bash
curl -m 10 -x "socks5h://$(curl -sL https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt | head -n 1)" https://api.ipify.org
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
| 🇺🇸 United States | 326 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇨🇳 China | 90 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇮🇳 India | 75 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) |
| 🇮🇩 Indonesia | 51 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇳🇱 Netherlands | 48 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) | 🇧🇷 Brazil | 35 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) |
| 🇫🇷 France | 30 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇯🇵 Japan | 26 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇩🇪 Germany | 24 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) |
| 🇷🇺 Russia | 24 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) | 🇨🇴 Colombia | 23 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇭🇰 Hong Kong | 22 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) |
| 🇻🇳 Vietnam | 18 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇦🇹 Austria | 17 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇵🇱 Poland | 15 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) |
| 🇸🇬 Singapore | 15 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) | 🇰🇷 South Korea | 13 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) | 🇬🇧 United Kingdom | 12 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) |
| 🇧🇩 Bangladesh | 11 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇰🇭 Cambodia | 11 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇨🇦 Canada | 10 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) |
| 🇨🇲 CM | 10 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) | 🇺🇦 Ukraine | 10 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇫🇮 Finland | 9 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) |
| 🇨🇿 Czechia | 6 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇹🇼 Taiwan | 6 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) | 🇹🇭 Thailand | 5 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) |
| 🇦🇪 United Arab Emirates | 4 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇨🇭 Switzerland | 3 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇪🇸 Spain | 3 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) |
| 🇮🇱 Israel | 3 | [il.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/il.txt) | 🇮🇶 Iraq | 3 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇲🇽 Mexico | 3 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) |
| 🇵🇭 Philippines | 3 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇵🇰 Pakistan | 3 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇷🇴 Romania | 3 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) |
| 🇸🇪 Sweden | 3 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇿🇦 South Africa | 3 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) | 🇦🇷 Argentina | 2 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) |
| 🇦🇺 Australia | 2 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) | 🇧🇬 Bulgaria | 2 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇨🇱 Chile | 2 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) |
| 🇩🇰 Denmark | 2 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) | 🇭🇳 Honduras | 2 | [hn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hn.txt) | 🇱🇻 Latvia | 2 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) |
| 🇲🇳 MN | 2 | [mn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mn.txt) | 🇲🇾 Malaysia | 2 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) | 🇳🇬 Nigeria | 2 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) |
| 🇳🇴 Norway | 2 | [no.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/no.txt) | 🇳🇵 Nepal | 2 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇷🇸 Serbia | 2 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) |
| 🇸🇳 Senegal | 2 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) | 🇹🇷 Turkey | 2 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇦🇱 Albania | 1 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇧🇦 BA | 1 | [ba.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ba.txt) | 🇧🇼 BW | 1 | [bw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bw.txt) | 🇨🇾 Cyprus | 1 | [cy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cy.txt) |
| 🇩🇴 DO | 1 | [do.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/do.txt) | 🇪🇨 Ecuador | 1 | [ec.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ec.txt) | 🇪🇪 Estonia | 1 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) |
| 🇪🇬 Egypt | 1 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) | 🇬🇭 Ghana | 1 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) | 🇭🇷 Croatia | 1 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) |
| 🇮🇪 Ireland | 1 | [ie.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ie.txt) | 🇮🇷 Iran | 1 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇮🇹 Italy | 1 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) |
| 🇰🇪 Kenya | 1 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) | 🇰🇿 Kazakhstan | 1 | [kz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kz.txt) | 🇲🇲 MM | 1 | [mm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mm.txt) |
| 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇵🇾 Paraguay | 1 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇸🇦 Saudi Arabia | 1 | [sa.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sa.txt) |
| 🇸🇰 Slovakia | 1 | [sk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sk.txt) | 🇹🇿 TZ | 1 | [tz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tz.txt) | 🇺🇾 UY | 1 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 132 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 144 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 80 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 132 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 227 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 202 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="why-this-list"></a>

## Why this list

- **Checked, not collected.** Every proxy had to complete a real protocol handshake and load two different sites through the same exit IP in the last run.
- **No honeypots, no injected scripts.** Pages that come back modified are thrown out; HTTPS counts only with a certificate that verifies.
- **Best first.** Sorted by how fast pages actually load, not by a single ping.
- **Details for every proxy** in `proxies.json`: exit IP, country, ASN and provider, datacenter or not, anonymity, latency, download speed, uptime over 24 hours and 7 days, first seen, and which big sites it gets through to.
- **Honest about uptime.** `stable.txt` holds only proxies that were on the list in 90 %+ of this week's hourly runs.
- **Used by other tools.** [monosans/proxy-scraper-checker](https://github.com/monosans/proxy-scraper-checker) and [gfpcom/free-proxy-list](https://github.com/gfpcom/free-proxy-list) pull these lists as a built-in source.

Want more than a list? **[proxy-scraper](https://github.com/maximilianfeix/proxy-scraper)** is the open-source tool behind it: scan from your own network, filter by country, protocol and site, a rotating proxy server, a Python API and an MCP server for AI agents. If this list saves you time, a ⭐ on [the tool](https://github.com/maximilianfeix/proxy-scraper) helps others find it.

## Good to know

- **Updates:** every hour, about 20 minutes past. A run with too few hits is skipped – the last good list stays.
- **History:** the git history is squashed at the start of every month so clones stay small. A daily archive of `proxies.json` lives in the [snapshot releases](https://github.com/maximilianfeix/proxy-scraper/releases?q=snapshots).
- **Found a problem?** Please open an issue in the [tool repository](https://github.com/maximilianfeix/proxy-scraper/issues).

> [!WARNING]
> Public proxies are run by strangers. Never send passwords or personal data through them, and use them only for things you're allowed to do.
