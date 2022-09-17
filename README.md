# auxeticslab.com

## Configuring the website on DigitalOcean

### Adding the Domain name
Domain name can be added in the DigitalOcean account under Networks. This means you might need to change certain settings from the domain registrar. This will enable further domain configurations using the DigitalOcean account. Instructions to add the domain name can be found [here](https://docs.digitalocean.com/products/networking/dns/how-to/add-domains/).

### Creating a new Droplet
A Droplet on DigitalOcean is a server location that one may subscribe to. The current website can run on the droplet with least specs. Instructions to create a droplet can be found [here](https://docs.digitalocean.com/products/droplets/how-to/create/).

Below details can be chosen while creating the droplet.

- OS/Distribution: Marketplace/LEMP on Ubuntu 2x.xx
- Plan: Shared CPU / Basic
- CPU option: Regular with SSD / $4 p.m / RAM:512MB, 1 CPU, 10GB SSD, 500GB Bandwidth (Can be upgraded later)
- Block Storage: Skip
- Datacenter region: Any (Generally selected based on primary audience; website will be served fastest in the region of the datacenter; the latency will be negligible for small websites)
- Authentication: 
  - Select SSH Keys if you wish to limit access/modification of server/website using select machines (Preferred). Follow instructions to create SSH keys [here](https://docs.digitalocean.com/products/droplets/how-to/add-ssh-keys/create-with-openssh/)
  - Select Password if you do not wish to limit select machines to access server
- Enable Backup: Skip
- Monitoring: Yes
- IPV6: Yes
- User Data: Yes
- How many Droplets: 1
- Hostname: `ubuntu-auxeticslab` / As suitable
- Tags: As suitable

### Configuring the server
- Follow instructions for initial configurations [here](https://marketplace.digitalocean.com/apps/lemp?ipAddress=128.199.20.219#getting-started)
- Map domain name to server using instructions [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-16-04)

### Clone website repository from Github
- Using terminal, navigate to website directory. It is expected to be `/var/www/auxeticslab.com/html`
- Run `git clone <repo-address>`
- If you want to update/sync the website instead, run `git pull <repo-address`

## Website Content and Editing
### Home
- Large/Display text
- Image (preferably 16:9) + Image caption
- About Auxetics Lab
- Research Focus
- Another Paragraph (?)
- Our Team

### Research
- Large/Display text
- Overview
- Focus 1 (?)
- Focus 2 (?)
- Focus 3 (?)

### People
- Overview
- Founding team
  - Member picture
  - Member name
  - Member position
  - Member description
  - Link to website, email
- Researchers (or other member category)
  - Member picture
  - Member name
  - Member position
- Alumni
  - Member picture
  - Member name
  - Member position

### Publications
- Overview
- Year-wise publication list
  - Each item to follow this syntax: `Author names (Year) Title. Publication. DOI: XX.XXXX/XXXXXXXX.XXXX.XXXXXXX`
