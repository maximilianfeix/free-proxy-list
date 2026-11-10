<div align="center">

# Free Proxy List

**412 free HTTP, SOCKS4 and SOCKS5 proxies that passed every check, re-checked every hour. Plain text files, no signup, no API key.**

![working proxies](https://img.shields.io/badge/working%20proxies-412-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-131-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-84-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-197-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--11--10%2016:27%20UTC-grey?style=flat-square&labelColor=121113) ![checked](https://img.shields.io/badge/checked-every%20hour-grey?style=flat-square&labelColor=121113)

[![Stars](https://img.shields.io/github/stars/maximilianfeix/free-proxy-list?style=social)](https://github.com/maximilianfeix/free-proxy-list) [![Stars of the tool](https://img.shields.io/github/stars/maximilianfeix/proxy-scraper?style=social&label=proxy-scraper)](https://github.com/maximilianfeix/proxy-scraper)

[Download](#download) · [Usage](#quick-start) · [By country](#by-country) · [Checks](#checks) · [Why this list](#why-this-list) · [Website](https://proxy-scraper.de/) · [Benchmark](https://proxy-scraper.de/benchmark/) · [The tool](https://github.com/maximilianfeix/proxy-scraper)

</div>

---

```text
https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt
https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt
https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt
https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt
```

<sub>`http.txt`, `socks4.txt` and `socks5.txt` hold one `ip:port` per line, `all.txt` one `type://ip:port`. Best first. The same files are at `https://proxy-scraper.de/<name>.txt` and on the [jsDelivr CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt).</sub>

**Last run:** 2026-11-10 16:27 UTC · **412** working proxies · **224** HTTPS-capable · median latency **1,120 ms** · median download **78 KB/s** · 54 countries

This run checked **300,000** candidates, collected from **354** tracked public sources. **412** (0.14%) passed every check and made the list.

<a id="download"></a>

## Download

Every file is sorted **best first** (first answer plus measured download speed), so `head -n 20` gives you the good ones. Hitting the raw.githubusercontent rate limit or need CORS? Use the CDN or proxy-scraper.de link.

| List | Format | Proxies | Download |
|---|---|---:|---|
| All proxies | `type://ip:port` | 412 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) · [proxy-scraper.de](https://proxy-scraper.de/all.txt) |
| HTTP | `ip:port` | 131 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) · [proxy-scraper.de](https://proxy-scraper.de/http.txt) |
| SOCKS4 | `ip:port` | 84 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks4.txt) |
| SOCKS5 | `ip:port` | 197 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 224 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) · [proxy-scraper.de](https://proxy-scraper.de/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 400 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) · [proxy-scraper.de](https://proxy-scraper.de/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 53 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) · [proxy-scraper.de](https://proxy-scraper.de/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 412 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

<a href="https://proxy-scraper.de/"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://proxy-scraper.de/chart-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://proxy-scraper.de/chart-light.svg">
  <img src="https://proxy-scraper.de/chart-dark.svg" alt="Working proxies over the last days, by protocol" width="100%">
</picture></a>

<a id="quick-start"></a>

## Usage

### curl

```bash
curl -sL https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt | head -n 20  # the 20 best SOCKS5 proxies
curl -m 10 -x "socks5h://$(curl -sL https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt | head -n 1)" https://api.ipify.org
```

### wget

```bash
wget -qO http.txt https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt
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

<details>
<summary><b>Node.js and Go</b></summary>

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

</details>

Or let [proxy-scraper](https://github.com/maximilianfeix/proxy-scraper) do the rotating and retrying for you:

```bash
pip install proxy-scraper-cli
proxy-scraper --pick 3 --verify       # three entries of this list that pass right now, from your network
proxy-scraper --diagnose HOST:PORT    # why one entry works for you or doesn't: every check and what it found
proxy-scraper --recheck live --serve  # re-check the whole list from here and run it as one rotating local proxy
```

```python
from proxyscraper import ProxyRotator

with ProxyRotator(country="DE") as rotator:
    print(rotator.get("https://httpbin.org/ip").text)
```

<a id="by-country"></a>

## By country

One file per country, best first, as `type://ip:port`: `https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/<code>.txt` (also at `https://proxy-scraper.de/country/<code>/proxies.txt`).

| Country | Proxies | List | Country | Proxies | List | Country | Proxies | List |
| ---|---:|--- | ---|---:|--- | ---|---:|--- |
| 🇺🇸 United States | 143 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇫🇷 France | 28 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇨🇳 China | 22 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) |
| 🇮🇩 Indonesia | 21 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇮🇳 India | 18 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) | 🇩🇪 Germany | 15 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) |
| 🇷🇺 Russia | 13 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) | 🇰🇭 Cambodia | 12 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇳🇱 Netherlands | 12 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) |
| 🇭🇰 Hong Kong | 11 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇻🇳 Vietnam | 11 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇰🇷 South Korea | 10 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) |
| 🇯🇵 Japan | 9 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇺🇦 Ukraine | 7 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇧🇷 Brazil | 6 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) |
| 🇵🇱 Poland | 6 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇧🇩 Bangladesh | 5 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇸🇬 Singapore | 5 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) |
| 🇹🇼 Taiwan | 5 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) | 🇧🇬 Bulgaria | 3 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇧🇮 Burundi | 3 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) |
| 🇱🇻 Latvia | 3 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) | 🇦🇷 Argentina | 2 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇦🇺 Australia | 2 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) |
| 🇨🇦 Canada | 2 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇨🇭 Switzerland | 2 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇨🇴 Colombia | 2 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) |
| 🇫🇮 Finland | 2 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) | 🇮🇷 Iran | 2 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇮🇹 Italy | 2 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) |
| 🇳🇵 Nepal | 2 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇵🇾 Paraguay | 2 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇹🇭 Thailand | 2 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) |
| 🇿🇦 South Africa | 2 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) | 🇨🇮 CI | 1 | [ci.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ci.txt) | 🇨🇱 Chile | 1 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) |
| 🇨🇲 CM | 1 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) | 🇨🇿 Czechia | 1 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇩🇰 Denmark | 1 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) |
| 🇪🇸 Spain | 1 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇬🇭 Ghana | 1 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) | 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) |
| 🇮🇶 Iraq | 1 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇲🇲 MM | 1 | [mm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mm.txt) | 🇲🇳 MN | 1 | [mn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mn.txt) |
| 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇲🇿 Mozambique | 1 | [mz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mz.txt) | 🇳🇬 Nigeria | 1 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) |
| 🇵🇭 Philippines | 1 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇵🇰 Pakistan | 1 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇸🇪 Sweden | 1 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) |
| 🇺🇾 UY | 1 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) | 🇺🇿 UZ | 1 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) | 🇻🇪 Venezuela | 1 | [ve.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ve.txt) |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 113 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 64 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 36 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 71 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 108 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 151 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="checks"></a>

## What the checks mean

| Check | What a pass means | Needed for | Passed in this run |
|---|---|---|---:|
| **Handshake** | The proxy completed a real handshake and fetched a page from checkip.amazonaws.com. The exit IP it showed was public and not the checker's own. | every list | 2,003 |
| **Second request** | A second request, to an unrelated site (httpbin.org), came out of the same exit IP. Proxies that answer once and then stall or switch exits drop out here. | every list | 679 |
| **Unchanged page** | A known static page (httpbin.org/html) arrived byte for byte. A proxy that rewrites plain-HTTP pages, e.g. injects ads or scripts, fails. It covers that one page at that moment, nothing more. | every list | 423 |
| **Verified TLS** | A tunnel to port 443 with a TLS handshake whose certificate verified on one test host (checkip.amazonaws.com). It says nothing about other sites, later requests or who runs the proxy. | `https.txt` | 275 |

A pass means the proxy worked **from our checker, at that moment**. Free proxies come and go, so expect some entries to be gone by the time you use them. Take the top of a file and skip what fails.

<a id="why-this-list"></a>

## Why this list

- **Checked, not just collected.** Every entry completed a real handshake and loaded two different sites through the same exit IP in the last run.
- **A test page has to arrive unchanged.** Entries that returned a changed test page are left out; HTTPS counts only with a certificate that verified on the test host.
- **Best first.** Sorted by how fast pages actually load, not by a single ping.
- **Details for every proxy** in `proxies.json`: exit IP, country, ASN and provider, whether the provider looks like a hosting company, anonymity, latency, download speed, share of runs on the list over 24 hours and 7 days, first seen, and which big sites it gets through to.
- **Share of runs on the list.** `stable.txt` holds only proxies that were on the list in 90 %+ of this week's runs. Not being on the list is not a measured failure.
- **Used by other tools.** [monosans/proxy-scraper-checker](https://github.com/monosans/proxy-scraper-checker) and [gfpcom/free-proxy-list](https://github.com/gfpcom/free-proxy-list) pull these lists as a built-in source.

## Support

If this list saves you time, a ⭐ helps others find it. A star on **[proxy-scraper](https://github.com/maximilianfeix/proxy-scraper)** counts too: it's the open-source tool that builds this list. Run it to scan from your own network, filter by country, protocol and site, or use its rotating proxy server, Python API and MCP server for AI agents.

[![Star history](https://api.star-history.com/svg?repos=maximilianfeix/free-proxy-list,maximilianfeix/proxy-scraper&type=Date)](https://star-history.com/#maximilianfeix/free-proxy-list&maximilianfeix/proxy-scraper&Date)

## Good to know

- **Updates:** every hour, around 20 minutes past. A run with too few hits is skipped and the last good list stays.
- **History:** the git history is squashed at the start of every month so clones stay small. A daily archive of `proxies.json` lives in the [snapshot releases](https://github.com/maximilianfeix/proxy-scraper/releases?q=snapshots).
- **Found a problem?** Please open an issue in the [tool repository](https://github.com/maximilianfeix/proxy-scraper/issues).

> [!WARNING]
> Public proxies are run by strangers. Never send passwords or personal data through them, and use them only for things you're allowed to do.
