Mostly cribbed from https://www.elastic.co/start
- Installed on Ubuntu, so skipping some stages we didn't have to do like installing apt-transport-https
- Assuming there is a user <loguser>

- Run all this as root, install java, elasticsearch and kibana
    sudo -i
    apt install default-jre
    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -
    echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-6.x.list
    apt update && apt install elasticsearch, kibana

- Set up elasticsearch and run it
    /bin/systemctl daemon-reload
    /bin/systemctl enable elasticsearch.service

- Note, might NOT want to start it - can give error later when trying to run as user as then running twice?
    systemctl start elasticsearch.service


    cd /usr/share/elasticsearch
    bin/elasticsearch-plugin install x-pack

- set up Kibana
    cd /usr/share/kibana
    bin/kibana-plugin install x-pack

- Fix permissions
    cd /usr/share
    chown -R elasticsearch:elasticsearch elasticsearch
    chown -R kibana:kibana kibana
    adduser <loguser> elasticsearch
    adduser <loguser> kibana
    cd /etc/default
    chown elasticsearch:elasticsearch elasticsearch
    chown kibana:kibana kibana
    
    cd /var/log/
    chown -R elasticsearch:elasticsearch elasticsearch
    chmod g+w -R elasticsearch
    
    cd /var/lib/
    chown -R elasticsearch:elasticsearch elasticsearch
    chmod g+w -R elasticsearch


- Now we can run as users but probably have to make a new terminal to get the new permissions
    exit
    exit
    
- New terminal window
    /usr/share/elasticsearch/bin/elasticsearch
    ctrl + z
    bg
    /usr/share/elasticsearch/bin/x-pack/setup-passwords auto

Grab the passwords for later
    sudo nano /etc/kibana/kibana.yml

Add them in (may have to remove # at start also):
    elasticsearch.username: "kibana"
    elasticsearch.password:  "<pwd>"
    /usr/share/kibana/bin/kibana

http://localhost:5601

Username: elastic  Password: <pwd>
