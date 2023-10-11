# ENFORE AUTOMATED K8s CLUSTER SECURITY USING KYNERNO POLICY GENERATOR AND ARGOCD

REF LINK 1 : https://github.com/iam-veeramalla/k8s-kyverno-argocd
REF LINK 2 : https://kyverno.io/
REF LINK 3 : https://github.com/kyverno/policies/tree/main/best-practices

- In Organizations generally we have very huge amount of MIRCOSERVICES
- There are development teams dedicated for these MICROSERVICES, Like namespace - A (logging) namespace -B (payments) namespace -C (DB) and etc
- Here we are created ISOLATED in kubernets cluster
- And the dev are like created CI CD and deployed in K8s
- COMPILANCE like : 1) No one should create EC2 instance more than 64GB 2) No one should use tag as latest
- Application is changed with your interfirence (Ex)
- Every organization has some rules or compilance so a DEVOPS Engineer we have to make sure compilance or rules are met

## THESE ALL GOVERNANCE WILL BE DONE BY USING ONE TOOL CALLED KYVERNO POLICIES 
Problem statement
--
**If we want to do the Governance of Kubernetes, KUBERnetes have ADMISSION CONTROLLER** 
-- ADMISSION CONTROLLER 
- It will Validate and Multate the admission control the authenticated and authorized user request
- If we create the kubernetes pod, we have one governance rule -- the rule is that pod should have resource request and limit set

## How do you define this Governance Rule
- One thing we can do is by using ADMISSION CONTROLLER
- Whenever creating to create POD or doing DEPLOYMENT or creating SERVICE, everything will goes through KUBE API
- If we create admission controller in kubernetes basically in go language and deploy in KUBERNETES
- Now all the things will go to ADMISSION CONTROLLER will basically VALIDATE, the RESOURCE REQUEST AND LIMITS
- Any POD that is created should have Resource request and limit
- Writing ADMISSION CONTROLLER in GO language is not that easy and if we have new rules then it is very defficult to write.

## KYVERNO
- We can write KYVERNO custom resources
- It will automatically creates the DYNAMIC ADMISSION CONTROLLER with some web hook configuration
- KYVERNO is Dynamic Admission Controller which is solving this problem for Devops Engineer
- Read our request and create configuration accordingly
- It will read the policy -- KYVERNO Controller
