# web-copilot

WebCopilot is an automation tool designed to enumerate subdomains of the target and detect bugs using different open-source tools.

The script first enumerate all the subdomains of the given target domain using assetfinder, sublister, subfinder, amass, findomain, hackertarget, riddler and crt then do active subdomain enumeration using gobuster from SecLists wordlist then filters out all the live subdomains using dnsx then it extract titles of the subdomains using httpx & scans for subdomain takeover using subjack. Then it uses gau/gauplus, waybackurls, or waymore to crawl all the endpoints of the given subdomains then it use gf patterns to filters out xss, lfi, ssrf, sqli, open redirect & rce parameters from that given subdomains, and then it scans for vulnerabilities on the subdomains using different open-source tools (like kxss, dalfox, openredirex, nuclei, etc). Then it'll print out the result of the scan and save all the output in a specified directory.

Features
Subdomain Enumeration using assetfinder, SUBLIST3R_V2.0, subfinder, amass, findomain, etc.
Active Subdomain Enumeration using gobuster & amass from SecLists/DNS wordlist.
Extract titles and take screenshots of live subdomains using aquatone & httpx.
Crawl all the endpoints of the subdomains using waymore and filter out XSS, SQLi, SSRF, etc parameters using gf patterns.
Run different open-source tools (like dalfox, nuclei, sqlmap, etc) to search for vulnerabilities on these parameters and then save all the outputs in the folder.
Usage
g!2m0:~ webcopilot -h
                                ──────▄▀▄─────▄▀▄
                                ─────▄█░░▀▀▀▀▀░░█▄
                                ─▄▄──█░░░░░░░░░░░█──▄▄
                                █▄▄█─█░░▀░░┬░░▀░░█─█▄▄█
 ██╗░░░░░░░██╗███████╗██████╗░░█████╗░░█████╗░██████╗░██╗██╗░░░░░░█████╗░████████╗
░██║░░██╗░░██║██╔════╝██╔══██╗██╔══██╗██╔══██╗██╔══██╗██║██║░░░░░██╔══██╗╚══██╔══╝
░╚██╗████╗██╔╝█████╗░░██████╦╝██║░░╚═╝██║░░██║██████╔╝██║██║░░░░░██║░░██║░░░██║░░░
░░████╔═████║░██╔══╝░░██╔══██╗██║░░██╗██║░░██║██╔═══╝░██║██║░░░░░██║░░██║░░░██║░░░
░░╚██╔╝░╚██╔╝░███████╗██████╦╝╚█████╔╝╚█████╔╝██║░░░░░██║███████╗╚█████╔╝░░░██║░░░
░░░╚═╝░░░╚═╝░░╚══════╝╚═════╝░░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚══════╝░╚════╝░░░░╚═╝░░░
                                                                [●] Version: 2.0.0
                                                                [●] @h4r5h1t | G!2m0


[❌] Warning: Use with caution. You are responsible for your own actions.
[❌] Developers assume no liability and are not responsible for any misuse or damage cause by this tool.


Usage:
webcopilot -d <target>
webcopilot -d <target> -a
webcopilot [-d target] [-o output destination] [-t threads] [-b blind server URL] [-x exclude domains] [-f subdomains file] [-a] [-v] [-h]
Flags:
  -d        Add your target [Optional]
  -o        To save outputs in folder [Default: webcopilot-<timestamp>]
  -t        Number of threads [Default: 100]
  -b        Add your server for BXSS [Default: False]
  -x        Exclude out of scope domains [Default: False]
  -f        Specify a file containing subdomains, this will skip subdomain enumeration [Optional]
  -a        Run all Enumeration by default it will run only subdomain enumeration [Default: False][Time Consuming]
  -v        Show version of the tool
  -h        Show this help message

Example:./webcopilot  -d domain.com -a -o domain -t 333 -x exclude.txt -b testServer.oast.fun
You can use  https://app.interactsh.com/ to get your server
Installing WebCopilot
WebCopilot requires git to install successfully. Run the following command as a root to install webcopilot

git clone https://github.com/h4r5h1t/webcopilot && cd webcopilot/ && chmod +x webcopilot install.sh && mv webcopilot /usr/bin/ && ./install.sh
[*] Installing Tools
[*] Creating Directories
[*] Installing Dependencies and Checking is Installed or Not
[*] git is already installed
[*] python3 is already installed
[*] python3-pip is already installed
[*] ruby is already installed
[*] golang-go is already installed
[*] snapd could not be found [*] Installing snapd
[*] snapd is not installed successfully, Please install it manually
[*] cmake is already installed
[*] jq is already installed
[*] gobuster is already installed
[*] chromium is already installed
[*] parallel is already installed
[*] Installing Python Tools
[*] Sublist3r could not be found [*] Installing Sublist3r
[*] Sublist3r is installed successfully
[*] sqlmap is already installed
[*] urldedupe is already installed
[*] openredirex is already installed
[*] waymore is already installed
[*] findomain is already installed
[*] uro is already installed
[*] Installing Wordlists and Payloads
[*] Skipping payloads/lfi.txt, already exists.
[*] Skipping resolvers.txt, already exists.
[*] Skipping subdomains.txt, already exists.
[*] Skipping fuzz.txt, already exists.
[*] Skipping dicc.txt, already exists.
[*] Skipping big.txt, already exists.
[*] Skipping dns.txt, already exists.
[*] Installing Go Tools
[*] anew is already installed
[*] gf is already installed
[*] aquatone could not be found [*] Installing aquatone
[*] aquatone is not installed successfully, Please install it manually
[*] assetfinder is already installed
[*] gau is already installed
[*] waybackurls is already installed
[*] httpx could not be found [*] Installing httpx
[*] httpx is not installed successfully, Please install it manually
[*] amass could not be found [*] Installing amass
[*] amass is not installed successfully, Please install it manually
[*] kxss is already installed
[*] subjack is already installed
[*] qsreplace is already installed
[*] dnsx could not be found [*] Installing dnsx
[*] dnsx is not installed successfully, Please install it manually
[*] dalfox is already installed
[*] crlfuzz is already installed
[*] nuclei could not be found [*] Installing nuclei
[*] nuclei is not installed successfully, Please install it manually
[*] subfinder could not be found [*] Installing subfinder
[*] subfinder is not installed successfully, Please install it manually
[*] Configuring Tools and Setting Up Environment
[*] All Tools are installed successfully
Tools Used:
SubFinder • Sublist3r • Findomain • gf • OpenRedireX • dnsx • sqlmap • gobuster • assetfinder • httpx • kxss • qsreplace • Nuclei • dalfox • anew • jq • aquatone • urldedupe • Amass • gauplus • waybackurls • crlfuzz • gau • waymore • SUBLIST3R_V2.0 • uro

Running WebCopilot
To run the tool on a target, just use the following command.

g!2m0:~ webcopilot -d example.com
The -o command can be used to specify an output dir.

g!2m0:~ webcopilot -d example.com -o example
The -a command can be used for running all enumerations (Subdomain Enumeration + Vulnerabilities Scanning).

g!2m0:~ webcopilot -d example.com -o example -a
The -t command can be used to add threads to your scan for faster result.

g!2m0:~ webcopilot -d example.com -o example -t 333 
The -b command can be used for blind xss (OOB), you can get your server from interact

g!2m0:~ webcopilot -d example.com -o example -t 333 -b eeuyhzfnsezrraragtd70ex5oc2hsw.oast.fun
The -x command can be used to exclude out of scope domains.

g!2m0:~ echo out.example.com > excludeDomain.txt
g!2m0:~ webcopilot -d example.com -o example -t 333 -x excludeDomain.txt -b eeuyhzfnsezrraragtd70ex5oc2hsw.oast.fun
The -f command can be used to pass file containing subdomains (using this skip Active + Passive Subdomain enumeration)

g!2m0:~ webcopilot -d example.com -o example -f /home/ubuntu/subdomains.txt -a
Example
Default options looks like this:

g!2m0:~ webcopilot -d http://testphp.vulnweb.com/ -a -b eeuyhzfpwgnsezrraragtd70ex5oc2hsw.oast.fun
                                ──────▄▀▄─────▄▀▄
                                ─────▄█░░▀▀▀▀▀░░█▄
                                ─▄▄──█░░░░░░░░░░░█──▄▄
                                █▄▄█─█░░▀░░┬░░▀░░█─█▄▄█
 ██╗░░░░░░░██╗███████╗██████╗░░█████╗░░█████╗░██████╗░██╗██╗░░░░░░█████╗░████████╗
░██║░░██╗░░██║██╔════╝██╔══██╗██╔══██╗██╔══██╗██╔══██╗██║██║░░░░░██╔══██╗╚══██╔══╝
░╚██╗████╗██╔╝█████╗░░██████╦╝██║░░╚═╝██║░░██║██████╔╝██║██║░░░░░██║░░██║░░░██║░░░
░░████╔═████║░██╔══╝░░██╔══██╗██║░░██╗██║░░██║██╔═══╝░██║██║░░░░░██║░░██║░░░██║░░░
░░╚██╔╝░╚██╔╝░███████╗██████╦╝╚█████╔╝╚█████╔╝██║░░░░░██║███████╗╚█████╔╝░░░██║░░░
░░░╚═╝░░░╚═╝░░╚══════╝╚═════╝░░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚══════╝░╚════╝░░░░╚═╝░░░
                                                                [●] Version: 2.0.0
                                                                [●] @h4r5h1t | G!2m0


[❌] Warning: Use with caution. You are responsible for your own actions.
[❌] Developers assume no liability and are not responsible for any misuse or damage cause by this tool.


Target:  http://testphp.vulnweb.com/
Output:  /home/ubuntu/github/webcopilot/webcopilot-1714304809
Threads: 100
Server:  eeuyhzfpwgnsezdyeragtd70ex5oc2hsw.oast.fun
Exclude: False
Mode:    Running all Enumeration
Time:    28-04-2024 17:16:49

[!] Please wait while scanning...

[●] Passive Subdomain Scanning is in progress:

[●] Subdomain Scanned  -  [assetfinder✔]                 Subdomain Found: 0
[●] Subdomain Scanned  -  [SUBLIST3R_V2.0✔]              Subdomain Found: 0
[●] Subdomain Scanned  -  [subfinder✔]                   Subdomain Found: 1
[●] Subdomain Scanned  -  [amass✔]                       Subdomain Found: 0
[●] Subdomain Scanned  -  [findomain✔]                   Subdomain Found: 1

[●] Subdomain Scanned  -  [crt.sh✔]                      Subdomain Found: 0
[●] Subdomain Scanned  -  [hackertarget✔]                Subdomain Found: 1
[●] Subdomain Scanned  -  [riddler✔]                     Subdomain Found: 0
[●] Subdomain Scanned  -  [certspotter✔]                 Subdomain Found: 0

[●] Active Subdomain Scanning is in progress:
[!] Please be patient. This may take a while...
[●] Active Subdomain Scanned  -  [gobuster✔]             Subdomain Found: 0
[●] Active Subdomain Scanned  -  [amass✔]                Subdomain Found: 0

[●] Subdomain Filtering: Filtering Alive subdomains
[●] Subdomain Filtering  -   Filtering alive subdomains is completed.    Check: /subdomains/alivesub.txt
[●] Subdomain Scanning: Getting titles of valid subdomains
[●] Visual inspection of Subdomains is completed.        Check: /subdomains/aquatone/

[●] Subdomain Enumeration Completed.    Total: 1 | Alive: 1

[●] Endpoints Scanning Completed.  Total: 0
[●] Vulnerabilities Scanning is in progress: Getting all vulnerabilities of 
[●] Vulnerabilities Scanning is in progress:

[●] Vulnerabilities Scanned  -  [XSS✔]                   Found: 0
[●] Vulnerabilities Scanned  -  [SQLi✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [LFI✔]                   Found: 0
[●] Vulnerabilities Scanned  -  [CRLF✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [SSRF✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [Open redirect✔]         Found: 0
[●] Vulnerabilities Scanned  -  [Subdomain Takeover✔]    Found: 0
[●] Vulnerabilities Scanned  -  [Nuclie✔]                Found: 0
[●] Vulnerabilities Scanning Completed.    Check: /vulnerabilities/


▒█▀▀█ █▀▀ █▀▀ █░░█ █░░ ▀▀█▀▀
▒█▄▄▀ █▀▀ ▀▀█ █░░█ █░░ ░░█░░
▒█░▒█ ▀▀▀ ▀▀▀ ░▀▀▀ ▀▀▀ ░░▀░░

[+] Subdomains of http://testphp.vulnweb.com/
[+] Subdomains Found: 1
[+] Subdomains Alive: 1
[+] Endpoints: 0
[+] XSS: 0
[+] SQLi: 0
[+] Open Redirect: 0
[+] SSRF: 0
[+] CRLF: 0
[+] LFI: 0
[+] Subdomain Takeover: 0
[+] Nuclei: 0
