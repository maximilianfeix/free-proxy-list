<div align="center">

# Free Proxy List

**1,035 free HTTP, SOCKS4 and SOCKS5 proxies that passed every check, re-checked every hour. Plain text files, no signup, no API key.**

![working proxies](https://img.shields.io/badge/working%20proxies-1%2C035-D4F77A?style=flat-square&labelColor=121113) ![http](https://img.shields.io/badge/http-226-blue?style=flat-square&labelColor=121113) ![socks4](https://img.shields.io/badge/socks4-367-blueviolet?style=flat-square&labelColor=121113) ![socks5](https://img.shields.io/badge/socks5-442-green?style=flat-square&labelColor=121113) ![updated](https://img.shields.io/badge/updated-2026--11--14%2002:31%20UTC-grey?style=flat-square&labelColor=121113) ![checked](https://img.shields.io/badge/checked-every%20hour-grey?style=flat-square&labelColor=121113)

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

**Last run:** 2026-11-14 02:31 UTC · **1,035** working proxies · **551** HTTPS-capable · median latency **2,111 ms** · median download **81 KB/s** · 88 countries

This run checked **150,000** candidates, collected from **363** tracked public sources. **1,035** (0.69%) passed every check and made the list.

<a id="download"></a>

## Download

Every file is sorted **best first** (first answer plus measured download speed), so `head -n 20` gives you the good ones. Hitting the raw.githubusercontent rate limit or need CORS? Use the CDN or proxy-scraper.de link.

| List | Format | Proxies | Download |
|---|---|---:|---|
| All proxies | `type://ip:port` | 1,035 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/all.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/all.txt) · [proxy-scraper.de](https://proxy-scraper.de/all.txt) |
| HTTP | `ip:port` | 226 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/http.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/http.txt) · [proxy-scraper.de](https://proxy-scraper.de/http.txt) |
| SOCKS4 | `ip:port` | 367 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks4.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks4.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks4.txt) |
| SOCKS5 | `ip:port` | 442 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/socks5.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/socks5.txt) · [proxy-scraper.de](https://proxy-scraper.de/socks5.txt) |
| HTTPS-capable, verified TLS | `type://ip:port` | 551 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/https.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/https.txt) · [proxy-scraper.de](https://proxy-scraper.de/https.txt) |
| Elite (no forwarded IP, no Via header) | `type://ip:port` | 924 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/elite.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/elite.txt) · [proxy-scraper.de](https://proxy-scraper.de/elite.txt) |
| Stable, on the list in 90 %+ of this week's runs | `type://ip:port` | 54 | [GitHub](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/stable.txt) · [CDN](https://cdn.jsdelivr.net/gh/maximilianfeix/free-proxy-list@main/stable.txt) · [proxy-scraper.de](https://proxy-scraper.de/stable.txt) |
| With all details | latency, country, provider, uptime, sites | 1,035 | [proxies.json](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.json) · [proxies.csv](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/proxies.csv) |

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
| 🇺🇸 United States | 184 | [us.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/us.txt) | 🇮🇩 Indonesia | 124 | [id.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/id.txt) | 🇫🇷 France | 90 | [fr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/fr.txt) |
| 🇮🇳 India | 57 | [in.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/in.txt) | 🇳🇱 Netherlands | 49 | [nl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/nl.txt) | 🇷🇺 Russia | 44 | [ru.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ru.txt) |
| 🇨🇳 China | 38 | [cn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cn.txt) | 🇨🇭 Switzerland | 30 | [ch.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ch.txt) | 🇯🇵 Japan | 30 | [jp.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/jp.txt) |
| 🇧🇷 Brazil | 28 | [br.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/br.txt) | 🇿🇼 ZW | 26 | [zw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/zw.txt) | 🇻🇳 Vietnam | 23 | [vn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/vn.txt) |
| 🇹🇭 Thailand | 19 | [th.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/th.txt) | 🇭🇰 Hong Kong | 17 | [hk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hk.txt) | 🇰🇭 Cambodia | 17 | [kh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kh.txt) |
| 🇧🇩 Bangladesh | 15 | [bd.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bd.txt) | 🇩🇪 Germany | 15 | [de.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/de.txt) | 🇰🇷 South Korea | 15 | [kr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/kr.txt) |
| 🇺🇦 Ukraine | 14 | [ua.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ua.txt) | 🇨🇲 CM | 12 | [cm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cm.txt) | 🇨🇴 Colombia | 12 | [co.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/co.txt) |
| 🇵🇱 Poland | 11 | [pl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pl.txt) | 🇧🇬 Bulgaria | 9 | [bg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bg.txt) | 🇵🇰 Pakistan | 9 | [pk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pk.txt) |
| 🇸🇪 Sweden | 7 | [se.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/se.txt) | 🇿🇦 South Africa | 7 | [za.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/za.txt) | 🇦🇷 Argentina | 6 | [ar.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ar.txt) |
| 🇲🇾 Malaysia | 6 | [my.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/my.txt) | 🇹🇷 Turkey | 6 | [tr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tr.txt) | 🇹🇼 Taiwan | 6 | [tw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/tw.txt) |
| 🇬🇧 United Kingdom | 5 | [gb.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gb.txt) | 🇳🇵 Nepal | 5 | [np.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/np.txt) | 🇵🇭 Philippines | 5 | [ph.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ph.txt) |
| 🇱🇹 Lithuania | 4 | [lt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lt.txt) | 🇱🇻 Latvia | 4 | [lv.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/lv.txt) | 🇦🇱 Albania | 3 | [al.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/al.txt) |
| 🇧🇮 Burundi | 3 | [bi.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bi.txt) | 🇨🇦 Canada | 3 | [ca.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ca.txt) | 🇨🇱 Chile | 3 | [cl.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cl.txt) |
| 🇪🇬 Egypt | 3 | [eg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/eg.txt) | 🇭🇺 Hungary | 3 | [hu.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hu.txt) | 🇮🇶 Iraq | 3 | [iq.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/iq.txt) |
| 🇮🇷 Iran | 3 | [ir.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ir.txt) | 🇷🇴 Romania | 3 | [ro.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ro.txt) | 🇸🇬 Singapore | 3 | [sg.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sg.txt) |
| 🇸🇳 Senegal | 3 | [sn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sn.txt) | 🇦🇹 Austria | 2 | [at.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/at.txt) | 🇧🇴 BO | 2 | [bo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bo.txt) |
| 🇨🇿 Czechia | 2 | [cz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cz.txt) | 🇪🇪 Estonia | 2 | [ee.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ee.txt) | 🇪🇸 Spain | 2 | [es.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/es.txt) |
| 🇲🇽 Mexico | 2 | [mx.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mx.txt) | 🇳🇬 Nigeria | 2 | [ng.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ng.txt) | 🇵🇸 PS | 2 | [ps.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ps.txt) |
| 🇵🇾 Paraguay | 2 | [py.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/py.txt) | 🇷🇸 Serbia | 2 | [rs.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/rs.txt) | 🇸🇰 Slovakia | 2 | [sk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sk.txt) |
| 🇦🇪 United Arab Emirates | 1 | [ae.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ae.txt) | 🇦🇲 AM | 1 | [am.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/am.txt) | 🇦🇺 Australia | 1 | [au.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/au.txt) |
| 🇧🇪 Belgium | 1 | [be.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/be.txt) | 🇧🇼 BW | 1 | [bw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/bw.txt) | 🇨🇮 CI | 1 | [ci.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ci.txt) |
| 🇨🇷 CR | 1 | [cr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/cr.txt) | 🇩🇰 Denmark | 1 | [dk.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/dk.txt) | 🇬🇪 GE | 1 | [ge.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ge.txt) |
| 🇬🇭 Ghana | 1 | [gh.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gh.txt) | 🇬🇷 Greece | 1 | [gr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gr.txt) | 🇬🇹 GT | 1 | [gt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/gt.txt) |
| 🇭🇷 Croatia | 1 | [hr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/hr.txt) | 🇮🇱 Israel | 1 | [il.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/il.txt) | 🇮🇸 IS | 1 | [is.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/is.txt) |
| 🇮🇹 Italy | 1 | [it.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/it.txt) | 🇰🇪 Kenya | 1 | [ke.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ke.txt) | 🇱🇸 LS | 1 | [ls.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ls.txt) |
| 🇱🇾 LY | 1 | [ly.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/ly.txt) | 🇲🇩 Moldova | 1 | [md.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/md.txt) | 🇲🇪 ME | 1 | [me.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/me.txt) |
| 🇲🇲 MM | 1 | [mm.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mm.txt) | 🇲🇳 MN | 1 | [mn.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mn.txt) | 🇲🇴 Macao | 1 | [mo.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mo.txt) |
| 🇲🇹 MT | 1 | [mt.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mt.txt) | 🇲🇼 MW | 1 | [mw.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mw.txt) | 🇲🇿 Mozambique | 1 | [mz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/mz.txt) |
| 🇵🇷 PR | 1 | [pr.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/pr.txt) | 🇸🇾 Syria | 1 | [sy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/sy.txt) | 🇺🇾 UY | 1 | [uy.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uy.txt) |
| 🇺🇿 UZ | 1 | [uz.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/countries/uz.txt) |  | |  |  | |  |

## Gets through to big sites

Many free proxies are blocked or sent to a captcha by the big sites. These got a real page in the last run:

| Site | Proxies | List |
|---|---:|---|
| Google | 115 | [google.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/google.txt) |
| Reddit | 237 | [reddit.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/reddit.txt) |
| Amazon | 49 | [amazon.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/amazon.txt) |
| Instagram | 127 | [instagram.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/instagram.txt) |
| TikTok | 134 | [tiktok.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/tiktok.txt) |
| Discord | 278 | [discord.txt](https://raw.githubusercontent.com/maximilianfeix/free-proxy-list/main/works-with/discord.txt) |

<a id="checks"></a>

## What the checks mean

| Check | What a pass means | Needed for | Passed in this run |
|---|---|---|---:|
| **Handshake** | The proxy completed a real handshake and fetched a page from checkip.amazonaws.com. The exit IP it showed was public and not the checker's own. | every list | 2,350 |
| **Second request** | A second request, to an unrelated site (httpbin.org), came out of the same exit IP. Proxies that answer once and then stall or switch exits drop out here. | every list | 1,273 |
| **Unchanged page** | A known static page (httpbin.org/html) arrived byte for byte. A proxy that rewrites plain-HTTP pages, e.g. injects ads or scripts, fails. It covers that one page at that moment, nothing more. | every list | 1,048 |
| **Verified TLS** | A tunnel to port 443 with a TLS handshake whose certificate verified on one test host (checkip.amazonaws.com). It says nothing about other sites, later requests or who runs the proxy. | `https.txt` | 600 |

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
