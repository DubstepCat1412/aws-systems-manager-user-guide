# AWS Systems Manager Application Manager<a name="application-manager"></a>

Application Manager, a capability of AWS Systems Manager, helps DevOps engineers investigate and remediate issues with their AWS resources in the context of their applications\. Application Manager aggregates operations information from multiple AWS services and Systems Manager capabilities to a single AWS Management Console\.

In Application Manager, an *application* is a logical group of AWS resources that you want to operate as a unit\. This logical group can represent different versions of an application, ownership boundaries for operators, or developer environments, to name a few\.

When you choose **Get started** on the Application Manager home page, Application Manager automatically imports metadata about your resources that were created in other AWS services or Systems Manager capabilities\. Specifically, Application Manager imports metadata about all of your AWS resources organized into resource groups\. Each resource group is listed in the **Custom applications** category as a unique application\. Application Manager also automatically imports metadata about resources that were created by AWS CloudFormation, Amazon Elastic Kubernetes Service \(Amazon EKS\), and AWS Launch Wizard\. Application Manager then displays those resources in the following predefined application categories:
+ Custom applications
+ CloudFormation stacks
+ EKS clusters
+ Launch Wizard

After import completes, you can view operations information about your resources in these predefined application categories\. Or, if you want to provide more context about a collection of resources, you can manually create an application in Application Manager and move resources or groups of resources into that application\. This enables you to view operations information in the context of an application\. 

After you [set up](https://docs.aws.amazon.com/systems-manager/latest/userguide/application-manager-getting-started-related-services.html) and configure AWS services and Systems Manager capabilities, Application Manager displays the following types of information about your resources:
+ Alarms provided by Amazon CloudWatch
+ Compliance information provided by AWS Config and Systems Manager State Manager
+ Kubernetes cluster information provided by Amazon EKS
+ Log data provided by AWS CloudTrail and Amazon CloudWatch Logs
+ OpsItems provided by Systems Manager OpsCenter
+ Resource details provided by the AWS services that host them\.

To help you remediate issues with components or resources, Application Manager also provides runbooks that you can associate with your applications\. 

## Benefits of using Application Manager<a name="application-manager-learn-more-benefits"></a>

Application Manager reduces the time it takes for DevOps engineers to detect and investigate issues with AWS resources\. To do this, Application Manager displays many types of operations information in the context of an application in one console\. Application Manager also reduces the time it takes to remediate issues by providing runbooks that perform common remediation tasks on AWS resources\.

## Features of Application Manager<a name="application-manager-learn-more-features"></a>

Application Manager includes the following features:
+ **Import your AWS resources automatically**

  During initial setup, you can choose to have Application Manager automatically import and display resources in your AWS account that are based on CloudFormation stacks, AWS Resource Groups, Amazon EKS clusters, and Launch Wizard deployments\. The system displays these resources in predefined application categories\. Thereafter, whenever new resources based on CloudFormation stacks, Resource Groups, Amazon EKS clusters, and Launch Wizard deployments are added to your AWS account, Application Manager automatically displays the new resources in the predefined application categories\. 
+ **View operational metrics and alarms for an application**

  Application Manager integrates with [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) to provide real\-time operational metrics and alarms for an application\. You can drill down into your application tree to view alarms at each component level\.
+ **View log data for an application**

  Application Manager integrates with [Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html) to provide log data in the context of your application without having to leave Systems Manager\.
+ **View and manage OpsItems for an application** 

  Application Manager integrates with [AWS Systems Manager OpsCenter](OpsCenter.md) to provide a list of operational work items \(OpsItems\) for your applications\. The list reflects automatically generated and manually created OpsItems\. You can view details about the resource that created an OpsItem, as well as the OpsItem status, source, and severity\. 
+ **View resource compliance data for an application** 

  Application Manager integrates with [AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) to provide compliance and history details about your AWS resources according to rules you specify\. Application Manager also integrates with [AWS Systems Manager State Manager](systems-manager-state.md) to provide compliance information about the state you want to maintain for your Amazon Elastic Compute Cloud \(Amazon EC2\) instances\. 
+ **View Amazon EKS cluster infrastructure information**

  Application Manager integrates with [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) to provide information about the health of your Amazon EKS cluster infrastructure as well as a component runtime view of the compute, networking, and storage resources in a cluster\.

  However, you can't manage or view operations information about your Amazon EKS pods or containers in Application Manager\. You can only manage and view operations information about the infrastructure that is hosting your Amazon EKS resources\.
+ **View detailed resource information in one console**

  Choose a resource name listed in Application Manager and view contextual information and operations information about that resource without having to leave Systems Manager\.
+ **Receive automatic resource updates** 

  If you make changes to a resource in a service console, and that resource is part of an application in Application Manager, then Systems Manager automatically displays those changes\. For example, if you update a stack in the AWS CloudFormation console, and if that stack is part of an Application Manager application, then the stack updates are automatically reflected in Application Manager\. 
+ **Discover Launch Wizard applications automatically**

  Application Manager is integrated with [AWS Launch Wizard](https://docs.aws.amazon.com/launchwizard/?id=docs_gateway)\. If you used Launch Wizard to deploy resources for an application, Application Manager can automatically import and display them in a Launch Wizard section\.
+ **Remediate issues with runbooks** 

  Application Manager includes predefined Systems Manager runbooks for remediating common issues with AWS resources\. You can choose a resource in Application Manager and then choose a runbook that performs a remediation task\.

## Pricing for Application Manager<a name="application-manager-learn-more-cost"></a>

Application Manager is available at no additional charge\.

## Resource quotas for Application Manager<a name="application-manager-learn-more-quotas"></a>

Application Manager has the resource quotas shown in the following table\.


****  

| Resource | Default limit | 
| --- | --- | 
|  Maximum number of applications in Application Manager  |  100 When you add an application in Application Manager, Systems Manager automatically creates a resource group to organize all of the resources for that application\. The maximum number of applications is based on the underlying quota for AWS Resource Groups\.  | 
|  Maximum number of AWS resources you can assign to an application  |  For applications based on AWS CloudFormation stacks: 200 For applications based on AWS Resource Groups: Unlimited  | 

**Topics**
+ [Benefits of using Application Manager](#application-manager-learn-more-benefits)
+ [Features of Application Manager](#application-manager-learn-more-features)
+ [Pricing for Application Manager](#application-manager-learn-more-cost)
+ [Resource quotas for Application Manager](#application-manager-learn-more-quotas)
+ [Getting started with Systems Manager Application Manager](application-manager-getting-started.md)
+ [Working with Application Manager](application-manager-working.md)
+ [Working with Amazon EKS in Application Manager](application-manager-working-EKS.md)
+ [Working with runbooks](application-manager-working-runbooks.md)