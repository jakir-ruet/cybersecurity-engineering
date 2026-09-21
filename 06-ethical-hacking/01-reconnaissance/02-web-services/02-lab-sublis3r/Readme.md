## Goal

Simulate how ethical hackers discover vulnerabilities starting from subdomain enumeration.

### Install Tools

```bash
git clone https://github.com/aboul3la/Sublist3r.git
cd Sublist3r
pip3 install -r requirements.txt
```

```bash
sudo apt install amass -y
```

```bash
sudo apt install httpx -y
```

```bash
git clone https://github.com/maurosoria/dirsearch.git
cd dirsearch
pip3 install -r requirements.txt
```

```bash
sudo apt install nmap -y
```

### Find Subdomains

```bash
python3 sublist3r.py -d sunitlimited.com -o subdomains.txt
amass enum -d sunitlimited.com -o amass.txt # Get MORE Subdomains
```

### Combine Results

```bash
cat subdomains.txt amass.txt | sort -u > final-subs.txt
```

### Find Live Websites

```bash
cat final-subs.txt | httpx -silent -o alive.txt
cat alive.txt
```

### Scan for Hidden Files

```bash
python3 dirsearch/dirsearch.py -u https://example.sunitlimited.com
```

### Scan Open Ports

```bash
nmap -sV sunitlimited.com
```
