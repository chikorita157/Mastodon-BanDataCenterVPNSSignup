# Mastodon-BanDataCenterVPNSSignup
A Nginx Config File that Blocks Datacenter and VPN IPs from Mastodon's Signup Page

Note: this is only being used for a lockdown situation, but this is not currently being used.

## Why block Datacenter and VPNs?
VPNs and VPN servers from datacenters (VPS) can be used to hide the user's IP address. A VPN (Virtual Private Network) encrypts the user traffic and hides the user's actual IP address. This makes it ripe for bad actors like trolls and spammers to create accounts and do things like SPAM. trolling, and/or harass users.

The config file is a NGINX include config file that blocks the signup page from VPNs and datacenter IPs. It only contains known VPN, datacenter IPs, StopForumSpam bad IPs, and Cloudflare IPs from viewing the signup page.

Move the file to the nginx's include folder. In the server block (SSL) for NGINX, add the following

include includes/datacentersignupblock.conf;

# How to contribute
If you find a new IP addres of a bad actor that is using a VPN when you have this config file applied, fork this repo, add a deny rule for the CIDR block that contains the perpetrator's IP address and do a pull request.
