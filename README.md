CloudShop Lite — AI-Augmented Cloud-Native Microservices Platform

CloudShop Lite is a production-style cloud-native e-commerce platform built on AWS EKS Kubernetes and enhanced with an AI-powered Site Reliability Engineering (SRE) assistant.

The project demonstrates how Large Language Models can operate infrastructure — diagnosing failures, analyzing logs, and executing recovery actions — through a dual-agent architecture:

In-cluster AI-Ops bot → monitors & heals Kubernetes workloads

Host-level MCP agent → performs system-level investigation & operations

This transforms a traditional microservices demo into a self-healing intelligent cloud platform.

🏗️ Architecture Overview

Core Idea:
LLM + Observability + Kubernetes Control Plane = Autonomous Operations

Users → React Dashboard → Nginx Gateway → Microservices → RDS PostgreSQL
                                    ↓
                             CloudWatch Logs
                                    ↓
                           AI-Ops FastAPI Agent
                                    ↓
                         MCP Infrastructure Agent
                                    ↓
                     Automated Recovery (kubectl actions)

🧩 Microservices
Service	Technology	Responsibility
Users Service	Flask	User management
Catalog Service	Flask	Product listing
Orders Service	Flask + PostgreSQL (RDS)	Order processing
AI-Ops Bot	FastAPI	Log analysis & auto-recovery
Gateway	Nginx	Routing & API aggregation
Frontend	React + Vite	Monitoring dashboard
☁️ AWS Infrastructure

Amazon EKS Kubernetes cluster

Amazon RDS PostgreSQL

AWS ELB Load Balancer

AWS CloudWatch centralized logging & metrics

Docker containerized workloads

🤖 AI-Ops Capabilities

The platform continuously monitors runtime behavior and performs automated remediation:

Detection

CloudWatch error summarization

Top failing endpoints identification

Pod crash detection

Deployment health checks

Diagnosis

Log pattern analysis using LLM

Root-cause reasoning

Configuration validation

Action (Self-Healing)

Restart failed deployments

Scale replicas

Apply recovery playbooks

Suggest configuration fixes

🧠 MCP Infrastructure Agent

A host-level Model Context Protocol (MCP) agent allows the LLM to behave like an SRE:

Reads Kubernetes YAML manifests

Executes kubectl commands

Inspects system logs

Validates configurations

Performs guided remediation

➡️ Enables natural-language infrastructure operations

Example:

“Why are orders failing?”
→ AI checks logs → finds DB timeout → restarts deployment → scales replicas

📊 Observability

Centralized logs (CloudWatch)

Failure analytics

Endpoint error ranking

Automated incident summary

🛠️ Tech Stack

Backend: Flask, FastAPI
Frontend: React, Vite
Infra: Docker, Kubernetes, Nginx
Cloud: AWS EKS, RDS, ELB, CloudWatch
Database: PostgreSQL
AI: LLM-powered reasoning agents + MCP protocol

🎯 Key Learning Outcomes

Cloud-native microservices deployment

Kubernetes operational workflows

AI-assisted DevOps & SRE automation

Observability-driven debugging

Autonomous remediation systems
