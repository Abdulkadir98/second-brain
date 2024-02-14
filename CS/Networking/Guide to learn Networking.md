

- First, understand the OSI. Memorize that bad boy, write lines if you have to. Test yourself later by pairing protocols with the OSI model ("Probably Didn't Need Those Stupid Packets, Anyway" is my favorite acronym)
    
- Understand how it can be used for troubleshooting (start at the bottom and work your way up. Is the cable plugged in is always a good first step)
    
- Learn how IPv4 addresses work (Public IPs, Private IPs, subnets, routing tables, NAT)
    
- Learn how MAC addresses work (ARP tables, switches, DHCP)
    
- Learn about routers
    
- Learn about switches
    
- Learn the difference between routers and switches (L2 vs L3 OSI)
    
- Learn about TCP and UDP (TCP = ALL the data will be received correctly, in order. UDP = All data will be sent, but it may not arrive, or it may arrive mangled, and that's OK)
    
- Learn a little about VLANs (TBH I need to brush up on these)
    
- Learn about DHCP (Static IPs vs Dynamic, IP reservations)
    
- Learn about DNS (A records, CNAME records, MX records, NS records, SRV records)
    
- Learn about IPv6 (Unfortunately, not extremely useful right now. Most companies are IPv4 only)
    
- Learn about VPNs (WireGuard is an excellent one to get started with, and will probably be the standard going forward. IPSec / OpenVPN if you want a challenge)
    
- Learn a bit how the "greater" internet works (BGP, carriers, IP blocks, IANA). You probably won't need to worry about these technologies / groups, but they're useful background knowledge
    
- Do some practical work
    
- Examples:
    
- Set up a WireGuard VPN server. Connect some clients to it. Ping the server from a client. Ping another client from a client
    
- Set up a DHCP server. Get a device to connect to it (You can use your home router for this. At least mess with the settings a bit)
    
- Buy a domain name. Point an A record to your home's public IP, or to a cloud server you control with a public IP. Configure SSH on the server, and do the necessary networking to SSH to your server using the domain name. For example, you may need to port forward on your router if your using your home public IP
    
- Configure mail for your custom domain. Send yourself some email. I recommend Zoho for a free email provider with your own domain.
    
- Secure your email using DMARC / SPF.
    
- Make a "hello world" website. Secure it (HTTPS) using LetsEncrypt.
    
- Set up a Pi-Hole DNS server for your home network (use a VM if you don't have a pi). Understand, generally, how it works.