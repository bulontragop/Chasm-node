# Chasm-node
Chasm - Installation Node

-Update and install packages
sudo apt update && sudo apt upgrade -y
-Install Docker
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
-Create Folder
mkdir chasm
cd chasm
-Setup Environment
nano .env
Paste the command below into the .env file

PORT=3001
LOGGER_LEVEL=debug

# Chasm
ORCHESTRATOR_URL=https://orchestrator.chasm.net
SCOUT_NAME=NAMASCOUTKAMU
SCOUT_UID=DARIMINTSCOUT
WEBHOOK_API_KEY=your_Webhook_API_Key
# Scout Webhook Url, update based on your server's IP and Port
# e.g. http://123.123.123.123:3001/
WEBHOOK_URL=http://your_VPS_ip:3001/

# Chosen Provider (groq, openai)
PROVIDERS=groq
MODEL=gemma2-9b-it
GROQ_API_KEY=your_Groq_API_Key

# Optional
OPENROUTER_API_KEY=
OPENAI_API_KEY=
Start and run Node with Docker
docker pull johnsonchasm/chasm-scout
docker run -d --restart=always --env-file ./.env -p 3001:3001 --name scout johnsonchasm/chasm-scout
Check if your node is running successfully
curl localhost:3001
if it runs successfully the output is “OK”
Check your Scouts Here