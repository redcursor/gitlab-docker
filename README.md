# Gitlab Self-hosting with Docker / Docker Compose

## g1ce
This is gitlab with community-edition (ce) using `docker-compose`

### Setups 
Before running docker-compose we should do below steps:  
 - install `docker` and `docker-compose`
 - change the default SSH port from **22** to something else, since gitlab needs it and `systemctl restart sshd`
 - having a domain or sub-domain to configure `yml` file e.g. `gitlab.examp1e.ir`
 - export a global variable before running `docker-compose up -d`
   - set it globally: `echo "export GITLAB_HOME=/srv/gitlab" >> /etc/environment`
   - set it for now: `> export GITLAB_HOME=/srv/gitlab`
 - downlaod `yml` file fom [docs.gitlab.com/omnibus/docker/](https://docs.gitlab.com/omnibus/docker/) and save it on disk
 - run `docker-compose up -d` , it should be run with no error
 - waiting about 5 - 10 minutes , so installation can be finsiehd
   - you can see the installation using `docker logs <CONTAINER-ID>`
 - check with curl -LI , till the **URL** we set has `200` in response
 - open the **URL** we have configured e.g. `gitlab.examp1e.ir`
 - for first login it asks for **Admin Password** to be set, set it and finished
 - login page should be available over HTTPS, e.g. `https://gitlab.examp1e.ir/users/sign_in`
