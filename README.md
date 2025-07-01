# Pod Status Checker with BOT
> *If all pods are in the `Running` state, your cluster health is likely above 80%.*

**PodPulse** is a simple Kubernetes tool to show the live pulse of your cluster based on Pod status. It helps you quickly identify pod states in a clean and color-coded way using a traffic-light style view (Green, Yellow, Red).

## ⚙️ Setups Instructions for Slack

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
## ⚙️ Setups Instructions for Telegram

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

Legends presents the live status of your pods using a traffic-light-style 🚥:

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
  - `Error`  
  - `Init:Error`  
  - `ImagePullBackOff`  
  - `ErrImagePull`  
  - `Unknown`  
  - `Init:CrashLoopBackOff`

---

---
## 📘 Available Commands

Use these Slack slash commands to query cluster pod statuses via the **PodPulse** bot:

| Command   | Description |
|-----------|-------------|
| `/pp`     | Show a summary of **all pod statuses** |
| `/green`  | Show only **healthy pods** (`Running`, `Completed`) |
| `/yellow` | Show **transitional pods** (`Pending`, `ContainerCreating`, `Terminating`, `NodeAffinity`) |
| `/red`    | Show **unhealthy pods** (`CrashLoopBackOff`, `Error`, `Init:Error`, `ImagePullBackOff`, `ErrImagePull`, `Unknown`, `Init:CrashLoopBackOff`) |
| `/ppd`    | Display **detailed status** of all pods |
| `/help`   | List all available commands and usage help |

> 💬 These commands are triggered directly from Slack using the PodPulse integration.

---


