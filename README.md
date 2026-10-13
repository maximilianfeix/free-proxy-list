<div align="center">

# Free Proxy List

**HTTP, SOCKS4 and SOCKS5 proxies that worked less than an hour ago – checked, not just scraped.**

![working proxies](https://img.shields.io/badge/working%20proxies-2%2C012-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-275-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-225-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-1%2C512-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--10--13%2019:34%20UTC-grey?style=flat-square&labelColor=121113)

[![Stars of the tool](https://img.shields.io/github/stars/maximilianfeix/proxy-scraper?style=social&label=proxy-scraper)](https://github.com/maximilianfeix/proxy-scraper)

[Download](#download) · [Quick start](#quick-start) · [By country](#by-country) · [Why this list](#why-this-list) · [Website](https://maximilianfeix.github.io/proxy-scraper/) · [The tool](https://github.com/maximilianfeix/proxy-scraper)

</div>

---

Updated **every hour** by [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper). It pulls candidates from 700+ public sources and keeps only the ones that pass every check – a real handshake, two sites through the same exit IP, nothing injected into the page, TLS that verifies. Most free lists are 95 % dead; this one is re-checked from scratch every run.

**Last run:** 2026-10-13 19:34 UTC · **2,012** working proxies · **1,272** HTTPS-capable · median latency **1,930 ms** · median download **40 KB/s** · 76 countries

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
| All proxies | `type://ip:port` | 2,012 | [all.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) |
| HTTP | `ip:port` | 275 | [http.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) |
| SOCKS4 | `ip:port` | 225 | [socks4.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) |
| SOCKS5 | `ip:port` | 1,512 | [socks5.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 1,272 | [https.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 1,967 | [elite.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 148 | [stable.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 2,012 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
| 🇺🇸 United States | 640 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇮🇳 India | 217 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) | 🇩🇪 Germany | 205 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) |
| 🇫🇷 France | 153 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇨🇳 China | 97 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇦🇹 Austria | 70 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) |
| 🇧🇷 Brazil | 45 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇳🇱 Netherlands | 43 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) | 🇸🇬 Singapore | 42 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) |
| 🇨🇴 Colombia | 39 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇨🇭 Switzerland | 38 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇮🇱 Israel | 38 | [il.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/il.txt) |
| 🇮🇩 Indonesia | 36 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇲🇾 Malaysia | 36 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) | 🇭🇰 Hong Kong | 27 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) |
| 🇯🇵 Japan | 24 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇻🇳 Vietnam | 20 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇿🇦 South Africa | 20 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) |
| 🇷🇺 Russia | 16 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) | 🇬🇧 United Kingdom | 14 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇧🇩 Bangladesh | 12 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) |
| 🇺🇦 Ukraine | 12 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇨🇦 Canada | 11 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇰🇭 Cambodia | 11 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) |
| 🇰🇷 South Korea | 10 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) | 🇳🇿 New Zealand | 10 | [nz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nz.txt) | 🇱🇻 Latvia | 9 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) |
| 🇧🇬 Bulgaria | 8 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇧🇮 Burundi | 8 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) | 🇵🇱 Poland | 8 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) |
| 🇹🇭 Thailand | 8 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) | 🇵🇰 Pakistan | 6 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇪🇪 Estonia | 5 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) |
| 🇳🇬 Nigeria | 4 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇭 Philippines | 4 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇦🇱 Albania | 3 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇨🇱 Chile | 3 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) | 🇪🇸 Spain | 3 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇯🇲 JM | 3 | [jm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jm.txt) |
| 🇳🇴 Norway | 3 | [no.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/no.txt) | 🇹🇷 Turkey | 3 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇹🇼 Taiwan | 3 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) |
| 🇦🇪 United Arab Emirates | 2 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇦🇷 Argentina | 2 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇦🇺 Australia | 2 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) |
| 🇦🇿 Azerbaijan | 2 | [az.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/az.txt) | 🇫🇮 Finland | 2 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) | 🇭🇳 Honduras | 2 | [hn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hn.txt) |
| 🇷🇸 Serbia | 2 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) | 🇸🇪 Sweden | 2 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇸🇳 Senegal | 2 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) |
| 🇺🇿 UZ | 2 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) | 🇿🇼 ZW | 2 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) | 🇦🇶 AQ | 1 | [aq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/aq.txt) |
| 🇧🇾 BY | 1 | [by.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/by.txt) | 🇨🇮 CI | 1 | [ci.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ci.txt) | 🇨🇾 Cyprus | 1 | [cy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cy.txt) |
| 🇨🇿 Czechia | 1 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇪🇬 Egypt | 1 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) | 🇬🇪 GE | 1 | [ge.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ge.txt) |
| 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) | 🇭🇺 Hungary | 1 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) | 🇮🇪 Ireland | 1 | [ie.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ie.txt) |
| 🇮🇶 Iraq | 1 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇮🇸 IS | 1 | [is.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/is.txt) | 🇮🇹 Italy | 1 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) |
| 🇰🇬 KG | 1 | [kg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kg.txt) | 🇰🇿 Kazakhstan | 1 | [kz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kz.txt) | 🇲🇦 Morocco | 1 | [ma.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ma.txt) |
| 🇲🇱 Mali | 1 | [ml.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ml.txt) | 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇲🇽 Mexico | 1 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) |
| 🇳🇵 Nepal | 1 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇷🇴 Romania | 1 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) | 🇸🇰 Slovakia | 1 | [sk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sk.txt) |
| 🇺🇬 UG | 1 | [ug.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ug.txt) |  | |  |  | |  |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 442 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 236 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 202 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 114 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 528 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 650 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

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
