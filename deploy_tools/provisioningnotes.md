Provisioning a new site
=======================

## Required packages:

* uwsgi
* nginx
* Python 3
* Git
* pip
* virtualenv

eg, on Ubuntu:

    sudo apt-get install nginx git python3 python3-pip
    sudo pip3 install virtualenv

## Nginx Virtual Host config

* see nginx.template.conf
* replace SITENAME with, eg, staging.my-domain.com
*Example
sed "s/SITENAME/tdd.kienenmason.com/g" \
    deploy_tools/nginx.template.conf | sudo tee \
    /etc/nginx/sites-available/tdd.kienenmason.com


##uWSGI config
*see uWSGI.template.conf
sed "s/SITENAME/tdd.kienenmason.com/g" \
    deploy_tools/uwsgi.template.conf | sudo tee \
    /etc/uwsgi/sites/tdd.kienenmason.com


## Folder structure:
Assume we have a user account at /home/username

/home/username
└── sites
    └── SITENAME
         ├── database
         ├── source
         ├── static
         └── virtualenv


Setup example available at https://www.digitalocean.com/community/tutorials/how-to-serve-django-applications-with-uwsgi-and-nginx-on-ubuntu-14-04