# genai-demo-with-rag-controlplane
GenAI demo with RAG in multi-cloud ControlPlane.com using a datacamp tutorial.  
## YouTube Demo
[![Gen AI with RAG Demo in Multi-Cloud ControlPlane.com](https://img.youtube.com/vi/FQt8XTwCS-o/0.jpg)](https://www.youtube.com/watch?v=FQt8XTwCS-o)
## Local AI with Docker, n8n, Qdrant, and Ollama
Follow along in docker with your local machine  
https://app.datacamp.com/learn/tutorials/local-ai

## ControlPlane
Multi-cloud internal deveoloper platform.  
https://controlplane.com/pricing  
https://docs.controlplane.com/quickstart/quick-start-3-cli  
### Easily deploy Deepseek-r1 on AWS using Control Plane
[![Easily deploy Deepseek-r1 on AWS using Control Plane](https://img.youtube.com/vi/gLoDcFXS5TM/0.jpg)](https://www.youtube.com/watch?v=gLoDcFXS5TM)

## InertiaLabs
https://www.inertialabs.io/

# Deploy Gen AI with RAG in ControlPlane
```
cpln apply -f genai.yaml --gvc <your-gvc>
```
## Postgres
If you prefer to deploy with a postgres db for n8n, apply pgres.yaml then n8n-pgres.yaml
```
cpln apply -f pgres.yaml --gvc <your-gvc>
cpln apply -f n8n-pgres.yaml --gvc <your-gvc>
```
You may need to delete the default n8n deployment first:
```
cpln delete -f n8n-pgres.yaml --gvc <your-gvc>
cpln apply -f n8n-pgres.yaml --gvc <your-gvc>
```

# Troubleshooting
## n8n workflow seems to stall at chat trigger, but execution was successful
In this case stopping the execution triggers a message that 
```
the execution finished before it could be stopped.
```
You may need to configure a subdomain instead of using the default n8n workload endpoint.
