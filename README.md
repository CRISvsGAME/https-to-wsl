# CRISvsGAME

## HTTPS to WSL

### Windows PowerShell

```
New-NetFirewallRule -DisplayName 'HTTPS Inbound' -Protocol TCP -LocalPort 443
netsh interface portproxy add v4tov4 `
listenport=443 `
listenaddress=0.0.0.0 `
connectport=443 `
connectaddress=(wsl hostname -I).Split(' ')[0].Trim()
```
