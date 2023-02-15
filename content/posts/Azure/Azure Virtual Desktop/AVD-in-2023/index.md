---
title: Azure Virtual Desktop in 2023
date: 2023-02-14T06:15:50+06:00
hero: avdtitle.png
menu:
  sidebar:
    name: AVD in 2023
    identifier: AVD-in-2023
    parent: Azure-Virtual-Desktop
    weight: 100
tags: ["Azure Virtual Desktop", "Cloud", "Azure"]
categories: ["Microsoft Azure, Blogging"]
---

# An introduction to the Azure Virtual Desktop series

The COVID-19 pandemic has accelerated the shift towards remote work and it’s now clear that this trend will continue even after the pandemic subsides and companies are introducing a new way of hybrid-working. In light of this, it’s important for companies to find solutions that allow employees to work from anywhere with ease. This is where Azure Virtual Desktop (AVD) comes in. Azure Virtual Desktop has evolved a lot since its introduction in 2019, and now in 2023, its now easier than ever to deploy an Azure Virtual Desktop environment, with more flexibility and control available now than there was at launch.

In this blog series, we’ll explore what Azure Virtual Desktop is, its key features and benefits, and how to deploy Azure Virtual Desktop in your environment, whether that's through the Azure Portal with AVD getting-Started or by deploying an enterprise ready, Azure Virtual Desktop Accelerator landing zone.

## What is Azure Virtual Desktop?

Azure Virtual Desktop is a cloud-based desktop virtualization solution that enables users to access a Windows desktop, or remote application from any device with an internet connection. This means employees can access their work desktop, files, and applications from a laptop, tablet, or mobile device without having to install anything on the device.

Windows Virtual Desktop as it was known back in 2020, seen a large spike of demand, with the shift to remote working due to the pandemic, a lot of organisations scrambled to provide a platform that allows its staff to continue working even when they are away from the office. Other remote-work opportunities such as introducing Microsoft 365 and Microsoft Teams, also aided in Microsofts effort to becoming the main cloud provider to go to for a hybrid or remote workforce.

{{< youtube aPEibGMvxZw >}}

### Brief history of Azure Virtual Desktop

- Originally announced in September 2018 as Windows Virtual Desktop, it became generally available in September 2019
- Microsoft describe a huge shift into cloud and into modern tools use as Microsoft Teams and Windows Virtual Desktop at their Microsoft Inspire Partner conference in July 2020, due to the shift to remote working.
- Microsoft rebranded the Windows Virtual Desktop service to Azure Virtual Desktop in June 2021 with new capabilities for security and management. [Microsoft Blog post](https://azure.microsoft.com/en-us/blog/azure-virtual-desktop-the-desktop-and-app-virtualization-platform-for-the-hybrid-workplace/)
- Microsofts latest Windows release, Windows 11, became generally available on Azure Virtual Desktop in Oct 2021 [Microsoft blog post](https://techcommunity.microsoft.com/t5/azure-virtual-desktop-blog/windows-11-is-now-generally-available-on-azure-virtual-desktop/ba-p/2810545)

## Key Features and Benefits of AVD

**Scability and Accessibility**

AVD is designed to scale to meet the needs of even the largest organizations. With AVD, Users can access their work desktop and applications from any device with an internet connection, making it easy to work from anywhere. An organisation can have up to 5,000 session hosts per Azure Subscription.
Users can access Azure Virtual Desktop from a Windows, Mac, iOS or Android device or even via a modern web browser.

**Security**

AVD is built on Azure, which is known for its security and compliance standards. This means that companies can be confident that their data is secure and in compliance with industry regulations. AVD can take use of the many security tools Microsoft provides such as Defender for Cloud.

**Licensing - You may already have it!**

You may already have the licensing capability to use AVD. Numerous Microsoft 365 based licenses have Azure Virtual Desktop usage built in. 

**Microsoft 365 integration**

Azure Virtual Desktop can seamlessy work with Microsoft 365. Users can get to work in a safe and fast environment allowing them to make calls through Microsoft Teams, or work on Microsoft office documents, straight from Azure Virtual Desktop.

**Cost effectiveness**

With the introduction of Windows 10/11 Multi-session, this allows for multiple users to access the same Windows virtual machine at the same time. Replicating something similar that we have seen in the past with Remote Desktop Services. The main difference now, being that its a Windows 10 or 11 desktop experience, whereas previously with RDS, it was built ontop of Windows server operating systems.
With Windows Multi-session, this reduces the amount of compute resources needed to provide a VDI experience in Azure, therefore being more cost effective for an organisation.

## Some use cases of Azure Virtual Desktop

**Privileged Access Workstation**

For Enterprise and smaller organisations, Privileged Access Workstations (PAWs) may be required to complete administrative tasks, such as changing security policies or converting a mailbox in Microsoft Exchange. It is recommended that any administrative tasks are completed on a secure, separate device from a users day-to-day device. Having to use or even carry around multiple devices doesn't sound like a feesable solution for this, therefore Azure Virtual Desktop could replace that second device for a PAW.

Microsoft provide some great guidance on how to deploy a [Privileged Access Workstation](https://learn.microsoft.com/en-us/security/compass/privileged-access-deployment), I will write on how to do this in Azure Virtual Desktop as part of this blog series, so watch this space!

**High Performance Computing**

Similar to other VDI solutions such as Windows 365, Azure Virtual Desktop can be a great solution for high performance computing. Workloads such as CAD often require high spec, expensive hardware to run, This hardware can get out of date quickly. Instead of providing a high-spec device for each user, it could be more beneficial to provide those users with a standard device for day to day tasks, and have an Azure Virtual Desktop environment built to match the requirements of those compute-hungry applications. Obviously nothing is free, therefore proper planning of this type of environment would be needed, but with AVDs scaling solutions, it could be a cost-beneficial exercise to use AVD for this.

**Device replacement**

Devices can still fail in todays modern world, and it can be a pain to end users if they don't have another way to work whilst they are waiting on a new device to be deployed to them. AVD is an ideal solution to have in the background, for users to access their files and applications whilst waiting for their new device. Windows 365 is also a great solution for this, but is billed on a monthly-license, Therefore if an AVD environment was already deployed, there would be no additional cost to the extra users using AVD whilst their device is being deployed.

**External Third-party users**

Most enterprises and organisations today have external people such as Auditors, Contractors or even third party IT companies (Not every company uses Azure Bastion!) needing to access applications and documents securely. AVD can be good for external third parties, as it can be quickly deployed to give them access to a secure environment and they won't be able to move any data from the platform to their own device. 

So there is a quick overview of Azure Virtual Desktop, its uses and how it could be a good platform for your organisation to use in different scenarios. In this blog series I hope to give a good overview of how to configure AVD for multiple scenarios, and how to use modern deployment methods such as Terraform and Azure Landing Zones. 
