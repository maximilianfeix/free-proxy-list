<div align="center">

# Free Proxy List

**690 free HTTP, SOCKS4 and SOCKS5 proxies that passed every check, re-checked every hour. Plain text files, no signup, no API key.**

![working proxies](https://img.shields.io/badge/working%20proxies-690-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-239-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-262-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-189-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--11--21%2002:31%20UTC-grey?style=flat-square&labelColor=121113) ![checked](https://img.shields.io/badge/checked-every%20hour-grey?style=flat-square&labelColor=121113)

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

**Last run:** 2026-11-21 02:31 UTC · **690** working proxies · **308** HTTPS-capable · median latency **1,348 ms** · median download **82 KB/s** · 84 countries

This run checked **150,000** candidates, collected from **367** tracked public sources. **690** (0.46%) passed every check and made the list.

<a id="download"></a>

## Download

Every file is sorted **best first** (first answer plus measured download speed), so `head -n 20` gives you the good ones. Hitting the raw.githubusercontent rate limit or need CORS? Use the CDN or proxy-scraper.de link.

| List | Format | Proxies | Download |
|---|---|---:|---|
| All proxies | `type://ip:port` | 690 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) · [proxy-scraper.de](https://proxy-scraper.de/all.txt) |
| HTTP | `ip:port` | 239 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) · [proxy-scraper.de](https://proxy-scraper.de/http.txt) |
| SOCKS4 | `ip:port` | 262 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks4.txt) |
| SOCKS5 | `ip:port` | 189 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 308 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) · [proxy-scraper.de](https://proxy-scraper.de/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 615 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) · [proxy-scraper.de](https://proxy-scraper.de/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 77 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) · [proxy-scraper.de](https://proxy-scraper.de/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 690 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
<summary><b>Node.js, Go, Java and Rust</b></summary>

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

### Java

```java
import java.net.*;
import java.net.http.*;
import java.time.Duration;
import java.util.Random;

// Java 16+. java.net.http only speaks HTTP proxies: keep the http:// lines of https.txt
public class Main {
    public static void main(String[] args) throws Exception {
        var list = HttpClient.newHttpClient().send(
            HttpRequest.newBuilder(URI.create("https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt")).build(),
            HttpResponse.BodyHandlers.ofString()).body();
        var proxies = list.lines().filter(l -> l.startsWith("http://")).toList();
        var uri = URI.create(proxies.get(new Random().nextInt(proxies.size())));
        var client = HttpClient.newBuilder()
            .proxy(ProxySelector.of(new InetSocketAddress(uri.getHost(), uri.getPort())))
            .connectTimeout(Duration.ofSeconds(10))
            .build();
        var ip = client.send(HttpRequest.newBuilder(URI.create("https://api.ipify.org")).build(),
            HttpResponse.BodyHandlers.ofString()).body();
        System.out.println(uri + " -> " + ip);
    }
}
```

### Rust

```rust
// cargo add reqwest --features blocking,socks rand
use rand::seq::IndexedRandom;

fn main() -> Result<(), Box<dyn std::error::Error>> {
    let list = reqwest::blocking::get("https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt")?.text()?;
    let proxies: Vec<&str> = list.lines().collect();
    let proxy = proxies.choose(&mut rand::rng()).unwrap(); // socks5.txt lines are ip:port
    let client = reqwest::blocking::Client::builder()
        .proxy(reqwest::Proxy::all(format!("socks5://{}", proxy))?)
        .timeout(std::time::Duration::from_secs(10))
        .build()?;
    println!("{} -> {}", proxy, client.get("https://api.ipify.org").send()?.text()?);
    Ok(())
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
| 🇺🇸 United States | 130 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇮🇩 Indonesia | 45 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇳🇱 Netherlands | 36 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) |
| 🇨🇳 China | 34 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇷🇺 Russia | 30 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) | 🇮🇳 India | 27 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) |
| 🇿🇼 ZW | 26 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) | 🇯🇵 Japan | 21 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇧🇷 Brazil | 20 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) |
| 🇭🇰 Hong Kong | 19 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇩🇪 Germany | 17 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) | 🇻🇳 Vietnam | 15 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) |
| 🇨🇴 Colombia | 14 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇫🇷 France | 14 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇨🇲 CM | 13 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) |
| 🇰🇭 Cambodia | 12 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇵🇰 Pakistan | 12 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇺🇦 Ukraine | 12 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) |
| 🇰🇷 South Korea | 11 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) | 🇦🇷 Argentina | 10 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇧🇩 Bangladesh | 9 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) |
| 🇨🇦 Canada | 8 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇳🇵 Nepal | 8 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇮🇷 Iran | 7 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) |
| 🇵🇱 Poland | 7 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇸🇬 Singapore | 7 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) | 🇧🇬 Bulgaria | 6 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) |
| 🇸🇪 Sweden | 6 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇹🇭 Thailand | 6 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) | 🇹🇼 Taiwan | 6 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) |
| 🇮🇶 Iraq | 5 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇿🇦 South Africa | 5 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) | 🇨🇿 Czechia | 4 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) |
| 🇬🇧 United Kingdom | 4 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇱🇹 Lithuania | 4 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) | 🇸🇳 Senegal | 4 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) |
| 🇹🇷 Turkey | 4 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇦🇪 United Arab Emirates | 3 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇧🇼 BW | 3 | [bw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bw.txt) |
| 🇨🇱 Chile | 3 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) | 🇩🇰 Denmark | 3 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) | 🇪🇬 Egypt | 3 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) |
| 🇫🇮 Finland | 3 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) | 🇲🇾 Malaysia | 3 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) | 🇦🇹 Austria | 2 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) |
| 🇦🇺 Australia | 2 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) | 🇨🇮 CI | 2 | [ci.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ci.txt) | 🇪🇨 Ecuador | 2 | [ec.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ec.txt) |
| 🇭🇺 Hungary | 2 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) | 🇲🇽 Mexico | 2 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) | 🇵🇪 Peru | 2 | [pe.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pe.txt) |
| 🇵🇭 Philippines | 2 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇵🇾 Paraguay | 2 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇷🇴 Romania | 2 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) |
| 🇺🇬 UG | 2 | [ug.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ug.txt) | 🇦🇫 AF | 1 | [af.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/af.txt) | 🇦🇱 Albania | 1 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇦🇲 AM | 1 | [am.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/am.txt) | 🇧🇪 Belgium | 1 | [be.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/be.txt) | 🇨🇾 Cyprus | 1 | [cy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cy.txt) |
| 🇪🇪 Estonia | 1 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇪🇸 Spain | 1 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇬🇭 Ghana | 1 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) |
| 🇭🇳 Honduras | 1 | [hn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hn.txt) | 🇭🇷 Croatia | 1 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) | 🇮🇪 Ireland | 1 | [ie.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ie.txt) |
| 🇮🇸 IS | 1 | [is.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/is.txt) | 🇮🇹 Italy | 1 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) | 🇰🇪 Kenya | 1 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) |
| 🇰🇿 Kazakhstan | 1 | [kz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kz.txt) | 🇲🇩 Moldova | 1 | [md.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/md.txt) | 🇲🇪 ME | 1 | [me.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/me.txt) |
| 🇲🇳 MN | 1 | [mn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mn.txt) | 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇲🇼 MW | 1 | [mw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mw.txt) |
| 🇳🇪 Niger | 1 | [ne.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ne.txt) | 🇳🇬 Nigeria | 1 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇹 Portugal | 1 | [pt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pt.txt) |
| 🇸🇧 SB | 1 | [sb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sb.txt) | 🇸🇨 Seychelles | 1 | [sc.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sc.txt) | 🇸🇮 Slovenia | 1 | [si.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/si.txt) |
| 🇸🇾 Syria | 1 | [sy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sy.txt) | 🇺🇿 UZ | 1 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) | 🇾🇪 YE | 1 | [ye.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ye.txt) |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 121 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 107 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 83 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 59 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 45 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 145 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="checks"></a>

## What the checks mean

| Check | What a pass means | Needed for | Passed in this run |
|---|---|---|---:|
| **Handshake** | The proxy completed a real handshake and fetched a page from checkip.amazonaws.com. The exit IP it showed was public and not the checker's own. | every list | 1,752 |
| **Second request** | A second request, to an unrelated site (httpbin.org), came out of the same exit IP. Proxies that answer once and then stall or switch exits drop out here. | every list | 961 |
| **Unchanged page** | A known static page (httpbin.org/html) arrived byte for byte. A proxy that rewrites plain-HTTP pages, e.g. injects ads or scripts, fails. It covers that one page at that moment, nothing more. | every list | 759 |
| **Verified TLS** | A tunnel to port 443 with a TLS handshake whose certificate verified on one test host (checkip.amazonaws.com). It says nothing about other sites, later requests or who runs the proxy. | `https.txt` | 396 |

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
