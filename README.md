<div align="center">

# Free Proxy List

**647 free HTTP, SOCKS4 and SOCKS5 proxies that passed every check, re-checked every hour. Plain text files, no signup, no API key.**

![working proxies](https://img.shields.io/badge/working%20proxies-647-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-192-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-305-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-150-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--11--26%2011:28%20UTC-grey?style=flat-square&labelColor=121113) ![checked](https://img.shields.io/badge/checked-every%20hour-grey?style=flat-square&labelColor=121113)

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

**Last run:** 2026-11-26 11:28 UTC · **647** working proxies · **296** HTTPS-capable · median latency **1,314 ms** · median download **75 KB/s** · 85 countries

This run checked **150,000** candidates, collected from **382** tracked public sources. **647** (0.43%) passed every check and made the list.

<a id="download"></a>

## Download

Every file is sorted **best first** (first answer plus measured download speed), so `head -n 20` gives you the good ones. Hitting the raw.githubusercontent rate limit or need CORS? Use the CDN or proxy-scraper.de link.

| List | Format | Proxies | Download |
|---|---|---:|---|
| All proxies | `type://ip:port` | 647 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) · [proxy-scraper.de](https://proxy-scraper.de/all.txt) |
| HTTP | `ip:port` | 192 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) · [proxy-scraper.de](https://proxy-scraper.de/http.txt) |
| SOCKS4 | `ip:port` | 305 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks4.txt) |
| SOCKS5 | `ip:port` | 150 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 296 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) · [proxy-scraper.de](https://proxy-scraper.de/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 595 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) · [proxy-scraper.de](https://proxy-scraper.de/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 96 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) · [proxy-scraper.de](https://proxy-scraper.de/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 647 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
| 🇺🇸 United States | 107 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇮🇩 Indonesia | 46 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇷🇺 Russia | 44 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) |
| 🇨🇳 China | 29 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇧🇷 Brazil | 27 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇿🇼 ZW | 26 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) |
| 🇻🇳 Vietnam | 25 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇮🇳 India | 21 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) | 🇳🇱 Netherlands | 17 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) |
| 🇩🇪 Germany | 16 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) | 🇰🇭 Cambodia | 16 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) | 🇰🇷 South Korea | 15 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) |
| 🇧🇩 Bangladesh | 14 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇺🇦 Ukraine | 14 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇨🇲 CM | 13 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) |
| 🇭🇰 Hong Kong | 12 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇵🇱 Poland | 11 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇹🇭 Thailand | 11 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) |
| 🇨🇴 Colombia | 10 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇧🇬 Bulgaria | 9 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇳🇵 Nepal | 9 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) |
| 🇵🇰 Pakistan | 9 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) | 🇱🇹 Lithuania | 8 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) | 🇨🇦 Canada | 7 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) |
| 🇫🇷 France | 7 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇹🇼 Taiwan | 6 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) | 🇿🇦 South Africa | 6 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) |
| 🇦🇺 Australia | 5 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) | 🇵🇭 Philippines | 5 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇸🇬 Singapore | 5 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) |
| 🇪🇸 Spain | 4 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇬🇧 United Kingdom | 4 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇯🇵 Japan | 4 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) |
| 🇰🇪 Kenya | 4 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) | 🇦🇷 Argentina | 3 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) | 🇨🇭 Switzerland | 3 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) |
| 🇭🇳 Honduras | 3 | [hn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hn.txt) | 🇭🇺 Hungary | 3 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) | 🇮🇷 Iran | 3 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) |
| 🇮🇹 Italy | 3 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) | 🇱🇻 Latvia | 3 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) | 🇳🇬 Nigeria | 3 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) |
| 🇸🇳 Senegal | 3 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) | 🇸🇾 Syria | 3 | [sy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sy.txt) | 🇦🇱 Albania | 2 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇦🇲 AM | 2 | [am.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/am.txt) | 🇪🇪 Estonia | 2 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇪🇬 Egypt | 2 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) |
| 🇫🇮 Finland | 2 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) | 🇬🇭 Ghana | 2 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) | 🇵🇪 Peru | 2 | [pe.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pe.txt) |
| 🇷🇸 Serbia | 2 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) | 🇹🇷 Turkey | 2 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇺🇾 UY | 2 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) |
| 🇦🇹 Austria | 1 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇧🇪 Belgium | 1 | [be.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/be.txt) | 🇧🇴 BO | 1 | [bo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bo.txt) |
| 🇨🇬 CG | 1 | [cg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cg.txt) | 🇨🇮 CI | 1 | [ci.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ci.txt) | 🇨🇱 Chile | 1 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) |
| 🇨🇾 Cyprus | 1 | [cy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cy.txt) | 🇨🇿 Czechia | 1 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇩🇰 Denmark | 1 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) |
| 🇪🇨 Ecuador | 1 | [ec.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ec.txt) | 🇬🇷 Greece | 1 | [gr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gr.txt) | 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) |
| 🇭🇷 Croatia | 1 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) | 🇮🇪 Ireland | 1 | [ie.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ie.txt) | 🇮🇶 Iraq | 1 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) |
| 🇯🇲 JM | 1 | [jm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jm.txt) | 🇲🇩 Moldova | 1 | [md.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/md.txt) | 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) |
| 🇲🇹 MT | 1 | [mt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mt.txt) | 🇲🇽 Mexico | 1 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) | 🇲🇾 Malaysia | 1 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) |
| 🇳🇴 Norway | 1 | [no.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/no.txt) | 🇳🇿 New Zealand | 1 | [nz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nz.txt) | 🇵🇦 PA | 1 | [pa.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pa.txt) |
| 🇵🇹 Portugal | 1 | [pt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pt.txt) | 🇵🇾 Paraguay | 1 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇶🇦 QA | 1 | [qa.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/qa.txt) |
| 🇸🇪 Sweden | 1 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇸🇰 Slovakia | 1 | [sk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sk.txt) | 🇺🇬 UG | 1 | [ug.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ug.txt) |
| 🇾🇪 YE | 1 | [ye.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ye.txt) |  | |  |  | |  |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 71 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 123 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 66 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 75 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 46 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 136 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="checks"></a>

## What the checks mean

| Check | What a pass means | Needed for | Passed in this run |
|---|---|---|---:|
| **Handshake** | The proxy completed a real handshake and fetched a page from checkip.amazonaws.com. The exit IP it showed was public and not the checker's own. | every list | 1,902 |
| **Second request** | A second request, to an unrelated site (httpbin.org), came out of the same exit IP. Proxies that answer once and then stall or switch exits drop out here. | every list | 908 |
| **Unchanged page** | A known static page (httpbin.org/html) arrived byte for byte. A proxy that rewrites plain-HTTP pages, e.g. injects ads or scripts, fails. It covers that one page at that moment, nothing more. | every list | 756 |
| **Verified TLS** | A tunnel to port 443 with a TLS handshake whose certificate verified on one test host (checkip.amazonaws.com). It says nothing about other sites, later requests or who runs the proxy. | `https.txt` | 418 |

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
