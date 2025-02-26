

---

# T-Rex NVIDIA GPU Miner

T-Rex is a versatile cryptocurrency mining software that supports a variety of algorithms, focusing on speed and ease of use.

### Supported Algorithms:
- **Ethash**
- **Etchash**
- **Autolykos2**
- **Kawpow**
- **Blake3**
- **Octopus**
- **Firopow**
- And many more...

### Developer Fee:
- **1%** (for Octopus, Autolykos2, and their dual modes: 2%).

---

## Getting Started

Quick start example:

```bash
t-rex -a ethash -o stratum+tcp://eu1.ethermine.org:4444 -u YOUR_ETHEREUM_ADDRESS -p x
```

For more details on options, see below.

---

## Command-Line Options

### Core Parameters:

| Parameter             | Description                                           |
|-----------------------|-------------------------------------------------------|
| `-a, --algo`           | Specifies the hashing algorithm (e.g., `ethash`, `kawpow`, etc.). |
| `--coin`               | Coin name (e.g., "etc" for Ethereum Classic).          |
| `-d, --devices`        | Comma-separated list of CUDA devices to use (e.g., `0,1` for two GPUs). |
| `-i, --intensity`      | GPU intensity (from 8 to 25).                         |
| `-o, --url`            | Pool URL in the format `<scheme>://<host>:<port>`.    |
| `-u, --user`           | Pool username.                                        |
| `-p, --pass`           | Pool password.                                        |
| `-w, --worker`         | Worker name for mining.                               |

### Additional Options:

- **LHR Tuning:** Set the LHR limit for NVIDIA GPUs with hash rate restrictions.
  ```bash
  --lhr-tune 74
  ```
- **Dual Mining:** Use two algorithms simultaneously.
  ```bash
  --dual-algo ethash+kawpow
  ```

### Example for Dual Mining:
```bash
t-rex -a ethash -o stratum+tcp://ethpool.org:4444 -u YOUR_ETHEREUM_ADDRESS -p x --dual-algo kawpow -o stratum+tcp://kawpowpool.com:7777 -u YOUR_KAWPOW_ADDRESS -p x
```

---

## Key Options and Settings

### API & Management:

- **API for Monitoring:**
  - `--api-bind-http` — IP:port for API binding.
  - `--api-key` — API key for authentication.

- **Temperature Limits:**
  - `--temperature-limit` — Set temperature limit for GPUs (e.g., `--temperature-limit 85`).

- **Auto-Update:**
  - `--autoupdate` — Enable automatic updates.

---

## FAQ

For additional information and frequently asked questions, please visit the [official documentation](https://github.com/trexminer/T-Rex/wiki/FAQ).

---

## Supported Algorithms

- **Ethash**: Suitable for Ethereum and other coins using this algorithm.
- **Kawpow**: Used for mining Ravencoin.
- **Octopus**: Suitable for mining Ergo and other coins.
- And many more!

---

## Important Notes

1. **Make sure you have the necessary GPU drivers installed.**
2. **Some settings may require administrator privileges.**

---

This version is more concise, uses clear headings, and organizes information for easier reading. Additionally, formatting tables for options gives a quick glance at available parameters. Let me know if you'd like to adjust anything further!


```

### Examples
* **ETHW+ALPH**</br>
```
t-rex -a ethash --dual-algo blake3 -o stratum+tcp://ethw.2miners.com:2020 -u 0x4121c43205D4244cb6395B2318d711a73fc1a6DE -p x -w rig0 --url2 stratum+tcp://de.alephium.herominers.com:1199 --user2 1qUuxVuXN2Pk4nnYTbL4qihjLWyRkVMQVYQDAajCcuPq --pass2 x
```

* **ETC+ALPH**</br>
```
t-rex -a etchash --dual-algo blake3 -o stratum+tcp://etc.2miners.com:1010 -u 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2 -p x -w rig0 --url2 stratum+tcp://de.alephium.herominers.com:1199 --user2 1qUuxVuXN2Pk4nnYTbL4qihjLWyRkVMQVYQDAajCcuPq --pass2 x
```

* **ERGO-nanopool**</br>
```
t-rex -a autolykos2 -o stratum+tcp://ergo-eu1.nanopool.org:11111 -u 9gpNWA3LVic14cMmWHmKGZyiGqrxPaSEvGsdyt7jt2DDAWDQyc9.rig0/your@email.org -p x
```

* **ERGO-herominers**</br>
```
t-rex -a autolykos2 -o stratum+tcp://de.ergo.herominers.com:1180 -u 9gpNWA3LVic14cMmWHmKGZyiGqrxPaSEvGsdyt7jt2DDAWDQyc9.rig0 -p x
```

* **ERGO-woolypooly**</br>
```
t-rex -a autolykos2 -o stratum+tcp://pool.woolypooly.com:3100 -u 9gpNWA3LVic14cMmWHmKGZyiGqrxPaSEvGsdyt7jt2DDAWDQyc9.rig0 -p x
```

* **ERGO-2miners**</br>
```
t-rex -a autolykos2 -o stratum+tcp://erg.2miners.com:8888 -u 9gpNWA3LVic14cMmWHmKGZyiGqrxPaSEvGsdyt7jt2DDAWDQyc9.rig0 -p x
```

* **ETHW+ZIL-ezil**</br>
```
t-rex -a ethash --coin eth+zil -o stratum+tcp://ethw.2miners.com:2020 -u 0x4121c43205D4244cb6395B2318d711a73fc1a6DE --url2 stratum+tcp://eu.ezil.me:4444 --user2 0x4121c43205D4244cb6395B2318d711a73fc1a6DE.zil1yn92lnkkfsn0s2hlvfdmz6y2yhpqm98vng38s9.WORKER --extra-dag-epoch 0
```

* **ETC+ZIL-ezil**</br>
```
t-rex -a etchash --coin etc+zil -o stratum+tcp://eu1-etc.ethermine.org:4444 -u 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2 --url2 stratum+tcp://eu.ezil.me:4444 --user2 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2.zil1yn92lnkkfsn0s2hlvfdmz6y2yhpqm98vng38s9.WORKER --extra-dag-epoch 0
```

* **ETC-2miners**</br>
```
t-rex -a etchash -o stratum+tcp://etc.2miners.com:1010 -u 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2 -p x -w rig0
```

* **ETC-woolypooly**</br>
```
t-rex -a etchash -o stratum+tcp://pool.woolypooly.com:35000 -u 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2 -p x -w rig0
```

* **ETC-ISP-hidden-mode**</br>
```
t-rex -a etchash -o stratum+tcp://eu1-etc.ethermine.org:4444 -u 0x0924EF9ecBcC1287047cAFd2EAD3A133313eE6A2 -p x -w rig0 --no-sni --dns-https-server 1.1.1.1
```

* **ETHW-ethproxy**</br>
```
t-rex -a ethash -o stratum+http://127.0.0.1:8080
```

* **CFX-woolypooly**</br>
```
t-rex -a octopus -o stratum+tcp://pool.woolypooly.com:3094 -u cfx:aajauymfc0cpd4aj91wmfyd150avfg3fmym9j2xrh8.rig0 -p x
```

* **CFX-nanopool**</br>
```
t-rex -a octopus -o stratum+tcp://cfx-eu1.nanopool.org:17777 -u cfx:aajauymfc0cpd4aj91wmfyd150avfg3fmym9j2xrh8.rig0/your@email.org -p x
```

* **ALPH-woolypooly**</br>
```
t-rex -a blake3 -o stratum+tcp://pool.woolypooly.com:3106 -u 1qUuxVuXN2Pk4nnYTbL4qihjLWyRkVMQVYQDAajCcuPq -p x -w rig0
```

* **ALPH-herominers**</br>
```
t-rex -a blake3 -o stratum+tcp://de.alephium.herominers.com:1199 -u 1qUuxVuXN2Pk4nnYTbL4qihjLWyRkVMQVYQDAajCcuPq -p x -w rig0
```

* **RVN-2miners**</br>
```
t-rex -a kawpow -o stratum+tcp://rvn.2miners.com:6060 -u RNm4LMBGyfH8ddCGvncQKrMtxEydxwhUJL.rig -p x
```

* **RVN-ravenminer**</br>
```
t-rex -a kawpow -o stratum+tcp://stratum.ravenminer.com:3838 -u RNm4LMBGyfH8ddCGvncQKrMtxEydxwhUJL.rig -p x
```

* **RVN-woolypooly**</br>
```
t-rex -a kawpow -o stratum+tcp://pool.woolypooly.com:55555 -u RNm4LMBGyfH8ddCGvncQKrMtxEydxwhUJL.rig -p x
```

* **SERO-serocash**</br>
```
t-rex -a progpow --coin sero -o stratum+tcp://pool2.sero.cash:8808 -u JCbZnEb8XtWV814QWRpDcDxpQpXZXw4ARneAtwXNYdd3reuo4xQDcuZivopA761QnQyfMermHR9Mpi156F5n7ez9tv75Wt7vWbHXtuyZsQVWLbKNHnZgwcXbR2yZmbw89WT -p x -w rig0
```

* **VBK-reb0rn**</br>
```
t-rex -a progpow-veriblock -o stratum+tcp://vbk-reb0rn.ddns.net:8502 -u V5h6udgGe6eL4M9cYGi776WCP75URm -p x -w rig0
```

* **VEIL-woolypooly**</br>
```
t-rex -a progpow-veil -o stratum+tcp://pool.woolypooly.com:3098 -u bv1qzftz0vuqa82zy29avylv8sclskweqsrwysgrkg -p x -w rig0
```

* **ZANO-luckypool**</br>
```
t-rex -a progpowz -o stratum+tcp://zano.luckypool.io:8877 -u iZ2bZfXdeN626rkyy9YsnfeT1Qq1K6XamE4brWm3tzP5hDUAig4dHmKSqe4yyq5dgbSPjmpLbfidqPyDXAuFY2J9544F95vagSF1Xqq3eCUp -p x -w rig0
```

* **FIRO-2miners**</br>
```
t-rex -a firopow -o stratum+tcp://firo.2miners.com:8181 -u aBR3GY8eBKvEwjrVgNgSWZsteJPpFDqm6U.rig0 -p x
```

* **FIRO-mintpond**</br>
```
t-rex -a firopow -o stratum+ssl://firo.mintpond.com:3005 -u aBR3GY8eBKvEwjrVgNgSWZsteJPpFDqm6U.rig0 -p x
```

* **FIRO-woolypooly**</br>
```
t-rex -a firopow -o stratum+tcp://pool.woolypooly.com:3104 -u aBR3GY8eBKvEwjrVgNgSWZsteJPpFDqm6U.rig0 -p x
```



## JSON Config File

To start T-Rex with a config file `config.txt`, type in the console: `t-rex -c config.txt`.
You can use the `config_example` file as a starting point to create your own configuration.  
If a parameter is set in both the config file and the command line, the latter takes precedence.  
For example: `t-rex -c config.txt -w <worker_name_to_override_the_one_in_config_file>`  
You can also use environment variables: simply place `%YOUR_ENV_VAR%` anywhere in your config file, and it will be automatically substituted with the value of the `YOUR_ENV_VAR` variable at runtime.

## Watchdog

The watchdog is designed to monitor the miner's state and restart T-Rex if it crashes or hangs for any reason.  
Additionally, the watchdog can optionally perform automatic updates if a newer version is available.  
We recommend using the watchdog to avoid any downtime in mining and ensure that your GPUs remain active 24/7.  
If you need to disable the watchdog, you can do so by using the `--no-watchdog` parameter.

## HTTP API

For more information, visit: [T-Rex API Documentation](https://github.com/trexminer/T-Rex/wiki/API)

## Antivirus Alerts

To protect the miner from reverse engineering attacks, the binaries are packed using third-party software, which mangles the original machine code. As a result, some antivirus engines may detect certain signatures within the executable that are similar to those found in real viruses protected by the same packer.  
It is advisable not to use cryptocurrency miners on computers where you store sensitive data (e.g., wallets, passwords, etc.).

## Useful Links

Mining calculator: [https://woolypooly.com/en/calc/what-to-mine-gpu](https://woolypooly.com/en/calc/what-to-mine-gpu)

## Tips

To maximize the hash rate, our software utilizes all available GPU resources. It is important to review your overclocking settings before you start mining.  
Our general recommendation is to start with the GPU's stock settings (no overclock, default power limit). After ensuring stability, gradually increase your overclock to find the "sweet spot," where the miner performs optimally without crashing.


