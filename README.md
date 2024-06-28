
# Interval gaianet chat 
This repository provides playbooks to simplify setting up an interval curl command for Gaianet chat on Linux systems.

## Prerequisites
Recommended server specifications:
- opt for a VPS server from Contabo.


## Getting Started
## Step 1: Installing Dependencies
Update your system and install necessary tools:
```
sudo apt update && sudo apt upgrade -y
```
```
sudo apt install ansible git -y
```
## Step 2: Downloading the Project
Clone this repository to access the Ansible playbook and related files:
```
git clone https://github.com/nuttanont/gaianet-chat.git
cd gaianet-chat
```
## Step 3: Installing Ansible playbook
Execute the playbook using the following command:
```
ansible-playbook setup_cron_gaianet.yml 
```
Note: 
- When prompted for `subdomain` enter the Gaianet node’s subdomain, e.g. `https://0x91e88fea19bc2d6abd578fb9d87da53f49a10831.us.gaianet.network`
- When prompted for `message` enter the message to be sent, e.g. `Where is Paris?`
- prompt `interval_timer_minute` with the subdomain network of gaianet node `2` minutes
<img width="1365" alt="image" src="https://github.com/nuttanont/gaianet-chat/assets/5306857/24dadafd-c160-4c90-bc16-0364aadf5a38">
<img width="1192" alt="image" src="https://github.com/nuttanont/gaianet-chat/assets/5306857/91e2d03b-d9a4-47f8-ab94-8aaded251f09">




## Step 4: Viewing Response Logs
To view the logs for Gaianet responses, use:
```
tail -f /root/gaianet-chat/gaianet_chat.log
```

## Additional Information
To stop the service, run:

```
ansible-playbook cancel_cron_gaianet.yml
```
### Checking if the Interval Job is Running
- check on file `tail -f /root/gaianet-chat/gaianet_chat.log` still running every `interval_time` that you setup
<img width="830" alt="image" src="https://github.com/nuttanont/gaianet-chat/assets/5306857/d76d7920-7b35-43da-92b4-b89cb31cf822">


- `crontab -l` you will see job `gaianet-chat` still running
<img width="933" alt="image" src="https://github.com/nuttanont/gaianet-chat/assets/5306857/09ef4093-45a6-41fc-a846-2f45915a5172">

