# Restack AI - Agent Tool

This repository contains a tool for an AI agent.
It demonstrates how to set up a basic workflow and functions.

## Prerequisites

- Docker (for running Restack)
- Python 3.10 or higher

## Start Restack

To start the Restack, use the following Docker command:

```bash
docker run -d --pull always --name restack -p 5233:5233 -p 6233:6233 -p 7233:7233 ghcr.io/restackio/restack:main
```

## Start python shell

```bash
poetry env use 3.10 && poetry shell
```

## Install dependencies

```bash
poetry install
```

```bash
poetry env info # Optional: copy the interpreter path to use in your IDE (e.g. Cursor, VSCode, etc.)
```

```bash
poetry run dev
```

## Configure Your Environment Variables

Duplicate the `env.example` file and rename it to `.env`.

Obtain a Restack API Key to interact with the 'restack-c1' model at no cost from [console.restack.io](https://console.restack.io)

## Run workflows

### from UI

You can run workflows from the UI by clicking the "Run" button.

![Run workflows from UI](./screenshot-endpoints.png)

### from API

You can run workflows from the API by using the generated endpoint:

`POST http://localhost:6233/api/workflows/AgentChatToolFunctions`

## Send an event to the 
```
{
  "workflowId": "{workflow_id}",
  "runId": "{run_id}",
  "eventName": "message",
  "eventInput": {
    "content": "What clothes are currently on sales?"
  }
}
```

Now, you can simply trigger more events from the Developer UI by clicking in the timeline on 'Send again' for the event and change the payload.

![Send another message from UI](./event-send-again.png)

## Deploy on Restack Cloud

To deploy the application on Restack, you can create an account at [https://console.restack.io](https://console.restack.io)
