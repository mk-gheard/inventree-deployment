**Briefing Document: InvenTree Test Environment Deployment in Azure**  

**Date:** 03/03/2025

**Prepared by:** Greg Heard

**Purpose:** To evaluate and compare two deployment approaches for the InvenTree ERP test environment in Azure: **Containerized Deployment (Azure Container Apps/AKS)** vs. **Virtual Machine (VM)-based Deployment**.

---
## **1. Overview of Deployment Approaches**

### **Option 1: Containerized Deployment (Azure Container Apps or AKS)**
- **Description:** Deploys InvenTree and its required services (PostgreSQL, Redis, etc.) as containers in Azure’s managed services. 
- **Two possible container platforms:**
  - **Azure Container Apps (ACA):** Simplified, serverless container deployment with automatic scaling.
  - **Azure Kubernetes Service (AKS):** Full Kubernetes orchestration for greater flexibility and control.

### **Option 2: Virtual Machine (VM) Deployment**
- **Description:** Deploys InvenTree on a traditional Azure VM (Linux-based) with Docker Compose managing required services.
- **More familiar approach**, but requires manual scaling and maintenance.

---
## **2. Advantages and Disadvantages**

| Factor | Containerized Deployment (ACA/AKS) | VM Deployment |
|--------|------------------------------------|--------------|
| **Ease of Deployment** | Moderate complexity (initial setup for containers) | Easier (familiar VM setup) |
| **Scalability** | High (Auto-scaling available) | Limited (Manual scaling required) |
| **Maintenance** | Lower (Managed services reduce admin overhead) | Higher (OS and application maintenance needed) |
| **Security** | Higher (isolated container environment) | Lower (requires manual security hardening) |
| **Cost Efficiency** | Pay-as-you-go scaling; no need to pay for idle resources | Fixed cost even when idle |
| **Time to Deploy** | ~3-5 days (including testing) | ~1-2 days (faster but less scalable) |
| **Network Security** | Can integrate with Azure Private Link, NSGs, and VPNs | Easier to restrict via NSG rules |

---
## **3. Estimated Timeframes for Deployment**

| Task | Containerized Deployment | VM Deployment |
|------|------------------------|-------------|
| Provision Infrastructure | 1 day | 0.5 day |
| Application Deployment | 2 days | 0.5-1 day |
| Security Configuration | 1 day | 1 day |
| Testing & Validation | 1 day | 1 day |
| **Total Estimated Time** | **~3-5 days** | **~1-2 days** |

---
## **4. Cost Considerations**

| Cost Factor | Containerized Deployment (ACA/AKS) | VM Deployment |
|------------|----------------------------------|--------------|
| **Compute Costs** | Pay-per-use (~£40-£120/month for a test env) | Fixed (~£50-£80/month per VM) |
| **Storage (PostgreSQL, Redis, etc.)** | Managed DB (~£25-£80/month) | Self-hosted (~£10-£25/month) |
| **Networking** | Private Link/VPN (~£8/month) | NSG-based (minimal cost) |
| **Estimated Total Cost** | ~£80-£200/month | ~£60-£110/month |

---
## **5. Recommendation & Next Steps**

### **Recommended Approach:** 
- If ease of setup and lower admin overhead are priorities → **Containerized Deployment (Azure Container Apps preferred)**.
- If a quick, familiar setup is required → **VM-based Deployment**.

### **Next Steps:**
1. Decide on the preferred deployment approach.
2. Provision resources based on the selected approach.
3. Deploy and configure InvenTree.
4. Restrict access to office IP addresses and test the setup.
5. Validate performance and security.

**Decision Required:** Which deployment approach should we proceed with?

---
**End of Briefing**

