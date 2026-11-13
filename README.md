<div align="center">

# Free Proxy List

**1,019 free HTTP, SOCKS4 and SOCKS5 proxies that passed every check, re-checked every hour. Plain text files, no signup, no API key.**

![working proxies](https://img.shields.io/badge/working%20proxies-1%2C019-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-313-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-348-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-358-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--11--13%2019:29%20UTC-grey?style=flat-square&labelColor=121113) ![checked](https://img.shields.io/badge/checked-every%20hour-grey?style=flat-square&labelColor=121113)

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

**Last run:** 2026-11-13 19:29 UTC · **1,019** working proxies · **512** HTTPS-capable · median latency **1,855 ms** · median download **82 KB/s** · 93 countries

This run checked **150,000** candidates, collected from **363** tracked public sources. **1,019** (0.68%) passed every check and made the list.

<a id="download"></a>

## Download

Every file is sorted **best first** (first answer plus measured download speed), so `head -n 20` gives you the good ones. Hitting the raw.githubusercontent rate limit or need CORS? Use the CDN or proxy-scraper.de link.

| List | Format | Proxies | Download |
|---|---|---:|---|
| All proxies | `type://ip:port` | 1,019 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) · [proxy-scraper.de](https://proxy-scraper.de/all.txt) |
| HTTP | `ip:port` | 313 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) · [proxy-scraper.de](https://proxy-scraper.de/http.txt) |
| SOCKS4 | `ip:port` | 348 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks4.txt) |
| SOCKS5 | `ip:port` | 358 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 512 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) · [proxy-scraper.de](https://proxy-scraper.de/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 852 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) · [proxy-scraper.de](https://proxy-scraper.de/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 46 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) · [proxy-scraper.de](https://proxy-scraper.de/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 1,019 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
| 🇺🇸 United States | 232 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇮🇩 Indonesia | 83 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇳🇱 Netherlands | 77 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) |
| 🇨🇭 Switzerland | 44 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇮🇳 India | 42 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) | 🇨🇳 China | 38 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) |
| 🇫🇷 France | 34 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) | 🇧🇷 Brazil | 33 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇷🇺 Russia | 32 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) |
| 🇿🇼 ZW | 26 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) | 🇭🇰 Hong Kong | 23 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇩🇪 Germany | 22 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) |
| 🇻🇳 Vietnam | 18 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) | 🇨🇴 Colombia | 17 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) | 🇹🇭 Thailand | 17 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) |
| 🇯🇵 Japan | 16 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) | 🇺🇦 Ukraine | 15 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇰🇭 Cambodia | 13 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) |
| 🇰🇷 South Korea | 12 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) | 🇵🇱 Poland | 11 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇧🇩 Bangladesh | 10 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) |
| 🇧🇬 Bulgaria | 10 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇨🇦 Canada | 10 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇵🇰 Pakistan | 10 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) |
| 🇸🇬 Singapore | 9 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) | 🇳🇵 Nepal | 7 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇸🇪 Sweden | 7 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) |
| 🇹🇷 Turkey | 7 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇹🇼 Taiwan | 7 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) | 🇨🇿 Czechia | 6 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) |
| 🇬🇧 United Kingdom | 6 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇵🇭 Philippines | 6 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) | 🇦🇷 Argentina | 5 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) |
| 🇲🇾 Malaysia | 5 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) | 🇦🇱 Albania | 4 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) | 🇱🇹 Lithuania | 4 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) |
| 🇲🇽 Mexico | 4 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) | 🇦🇹 Austria | 3 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇧🇮 Burundi | 3 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) |
| 🇧🇴 BO | 3 | [bo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bo.txt) | 🇪🇪 Estonia | 3 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇭🇺 Hungary | 3 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) |
| 🇮🇶 Iraq | 3 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) | 🇮🇷 Iran | 3 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇮🇹 Italy | 3 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) |
| 🇱🇻 Latvia | 3 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) | 🇷🇴 Romania | 3 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) | 🇸🇳 Senegal | 3 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) |
| 🇿🇦 South Africa | 3 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) | 🇧🇼 BW | 2 | [bw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bw.txt) | 🇨🇾 Cyprus | 2 | [cy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cy.txt) |
| 🇪🇬 Egypt | 2 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) | 🇪🇸 Spain | 2 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) | 🇫🇮 Finland | 2 | [fi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fi.txt) |
| 🇬🇭 Ghana | 2 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) | 🇬🇷 Greece | 2 | [gr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gr.txt) | 🇭🇷 Croatia | 2 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) |
| 🇰🇪 Kenya | 2 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) | 🇲🇦 Morocco | 2 | [ma.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ma.txt) | 🇲🇩 Moldova | 2 | [md.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/md.txt) |
| 🇲🇳 MN | 2 | [mn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mn.txt) | 🇵🇾 Paraguay | 2 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇸🇰 Slovakia | 2 | [sk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sk.txt) |
| 🇸🇾 Syria | 2 | [sy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sy.txt) | 🇺🇾 UY | 2 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) | 🇺🇿 UZ | 2 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) |
| 🇦🇫 AF | 1 | [af.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/af.txt) | 🇦🇲 AM | 1 | [am.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/am.txt) | 🇦🇺 Australia | 1 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) |
| 🇧🇫 Burkina Faso | 1 | [bf.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bf.txt) | 🇨🇩 CD | 1 | [cd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cd.txt) | 🇨🇱 Chile | 1 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) |
| 🇨🇲 CM | 1 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) | 🇩🇰 Denmark | 1 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) | 🇬🇶 GQ | 1 | [gq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gq.txt) |
| 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) | 🇱🇦 LA | 1 | [la.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/la.txt) | 🇲🇪 ME | 1 | [me.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/me.txt) |
| 🇲🇲 MM | 1 | [mm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mm.txt) | 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) | 🇲🇺 MU | 1 | [mu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mu.txt) |
| 🇲🇼 MW | 1 | [mw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mw.txt) | 🇳🇬 Nigeria | 1 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇪 Peru | 1 | [pe.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pe.txt) |
| 🇵🇬 PG | 1 | [pg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pg.txt) | 🇵🇸 PS | 1 | [ps.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ps.txt) | 🇷🇸 Serbia | 1 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) |
| 🇸🇦 Saudi Arabia | 1 | [sa.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sa.txt) | 🇸🇨 Seychelles | 1 | [sc.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sc.txt) | 🇹🇿 TZ | 1 | [tz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tz.txt) |
| 🇺🇬 UG | 1 | [ug.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ug.txt) | 🇼🇸 WS | 1 | [ws.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ws.txt) | 🇾🇪 YE | 1 | [ye.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ye.txt) |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 118 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 161 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 7 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 99 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 143 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 248 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="checks"></a>

## What the checks mean

| Check | What a pass means | Needed for | Passed in this run |
|---|---|---|---:|
| **Handshake** | The proxy completed a real handshake and fetched a page from checkip.amazonaws.com. The exit IP it showed was public and not the checker's own. | every list | 2,133 |
| **Second request** | A second request, to an unrelated site (httpbin.org), came out of the same exit IP. Proxies that answer once and then stall or switch exits drop out here. | every list | 1,217 |
| **Unchanged page** | A known static page (httpbin.org/html) arrived byte for byte. A proxy that rewrites plain-HTTP pages, e.g. injects ads or scripts, fails. It covers that one page at that moment, nothing more. | every list | 1,034 |
| **Verified TLS** | A tunnel to port 443 with a TLS handshake whose certificate verified on one test host (checkip.amazonaws.com). It says nothing about other sites, later requests or who runs the proxy. | `https.txt` | 547 |

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
