# PodPulse – Stay in Sync with Your Kubernetes Pods, Anywhere.
> *If all pods are in the `Running` state, your cluster health is likely above 80%.*

**PodPulse** is a simple Kubernetes tool to qucik check the live pulse of Pods based on its status via  `Slack` or `Telegram` bot.<br>
No more SSH hassles. 

## 🌍 Use Case

- **Mobile First K8s Visibility**: When laptop is not in hands
-  Whether you're away from your desk or off-duty

## 🤖 Guide to create BOT

- **Slack Bot** - 
- **Telegram Bot** - 

<h2><img src="https://www.svgrepo.com/download/303320/slack-new-logo-logo.svg" alt="Slack" width="20" style="vertical-align:middle; margin-right:8px;" /> Setup Instructions for Slack</h2>

```bash
# Clone the repository
git clone https://github.com/virsuryaircas/podpulse.git

# To integrate Slack
cd slack

# Replace your token with base64 encoded
nano podpulse-secret.yaml

# Apply the all manifests
kubectl apply -k .

# Verify the pod is in running state
kubectl get po -n podpulse

# Check the logs whether bot is connected or not
k logs -n podpulse deploy/podpulse-slack
🤖 PodPulse Slack Bot is starting...
💬 Ready to respond to /pp, /green, /yellow, /red, /ppd, /help commands!
⚡️ Bolt app is running!
```
<h2><img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Telegram_2019_Logo.svg" alt="Telegram" width="20" style="vertical-align:middle; margin-right:8px;" /> Setup Instructions for Telegram</h2>

```bash
# Clone the repository
git clone https://github.com/virsuryaircas/podpulse.git

# To integrate Telegram
cd telegram

# Replace your token with base64 encoded
nano podpulse-secret.yaml

# Apply the all manifests
kubectl apply -k .

# Verify the pod is in running state
kubectl get po -n podpulse

# Check the logs whether bot is connected or not
k logs -n podpulse deploy/podpulse-telegram
🤖 PodPulse Telegram Bot is starting...
💬 Ready to respond to /pp, /green, /yellow, /red, /ppd, /help commands!
```
---

## 📡 PodPulse - Pod Status Checker

Its messaging format legends presents the live status of your pods using a traffic-light-style 🚥:

- 🟢 **Green** – Healthy Pods  
  - `Running`  
  - `Completed`

- 🟡 **Yellow** – Transitional Pods
  - `Pending`  
  - `ContainerCreating`  
  - `Terminating`  
  - `NodeAffinity`

- 🔴 **Red** – Unhealthy Pods  
  - `CrashLoopBackOff`
  - `ImagePullBackOff`
  - `ErrImagePull`
  - `Error`
  - `Unknown`
  - `Init:Error`
  - `Init:CrashLoopBackOff`


## 📘 Available Commands

Use these slash commands to query cluster pod statuses via the bot:

| Command   | Description |
|-----------|-------------|
| `/pp`     | Show a summary of **all pod statuses** |
| `/green`  | Show **healthy pods**  |
| `/yellow` | Show **transitional pods**  |
| `/red`    | Show **unhealthy pods**  |
| `/ppd`    | Display **detailed status** of all pods |
| `/help`   | List all available commands |

> 💬 Note:
For Slack, you must define these commands in your bot settings.
For Telegram, it's optional — but recommended, setting the commands enables a quick-access menu, making it easier to use.

Once commands are set, there's no need to type — just tap and go. 🚀

## 🐳 Docker Image for PodPulse
📦 Slack Bot - [virsuryaircas/podpulse-slack](https://hub.docker.com/repository/docker/virsuryaircas/podpulse-slack) <br>
📦 Telegram Bot - [virsuryaircas/podpulse-telegram](https://hub.docker.com/repository/docker/virsuryaircas/telegram-slack)

---

 Be the Doctor of your Pods by checking its Pulse!!!
