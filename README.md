# 🎉 Traefik reverse proxy (Docker) on a VPS server 🎉

**Hello geeks! 😎 **

After struggling 😭 for weeks to set up Traefik reverse proxy on my VPS server, I finally managed to obtain a stable and efficient configuration 😏. Today I'm sharing my configuration with you, to help you avoid the same setbacks 🎁.

## Prerequisites 
- One domain name or more 
- Cloudflare account
- A VPS server

## Before running docker-compose
- Create an .env file near the docker-compose.yml file
- In the .env file add EMAIL constant and a DOMAIN1 constant
- Create the letsencrypt directory near the docker-compose file then add an acme.json file there
- Do a chmod 600 on acme.json
- Create secret files and add your cloudflare email and global token

## Attention 

In this chapter, I will share with you the crucial details that I IGNORED and which wasted my precious time.
- To add an entry point to a subdomain, you must create a CNAME record in the Cloudflare manager.
	> For example, if your domain is domain.com and you want to add an entry point to the subdomain subdomain.domain.com, you must create a CNAME record named subdomain with the value subdomain.domain.com
- If you have configured your server to use HTTPS, but are having problems using it on one of your entry points, here are some steps you can take to resolve the problem.
	- Clear the contents of the acme.json file
	- Pause cloudflare on all domains
	- Restart the docker-compose.yml file

## Conclusion
I hope this configuration will help you set up Traefik reverse proxy on your VPS server. Please let me know if you have any questions or comments.
