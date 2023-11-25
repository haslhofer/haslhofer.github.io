Rent a server from lambda labs https://cloud.lambdalabs.com/instances
I started with rent an instance on vast.ai

### Need to generate SSH keys
[Windows SSH guide](https://vast.ai/docs/guides/windows-ssh-scp-guide)

### tunnel traffic from linux

Install ngrok
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok

Add authtoken
ngrok config add-authtoken <token>

### Universal NER
https://github.com/universal-ner/universal-ner
