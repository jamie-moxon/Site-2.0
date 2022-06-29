---
title: Getting started with a Framework for Conditional Access
date: 2022-06-01T06:15:50+06:00
hero: hugotitle.jpg
menu:
  sidebar:
    name: Persona based Conditional Access
    identifier: Persona-based-conditional-access
    parent: Azure-Active-Directory
    weight: 100
tags: ["Azure Active Directory", "Conditional Access", "Microsoft Security"]
categories: ["Microsoft Azure, Security"]
---



Conditional Access is security 101 for organisations that use Azure Active Directory. Any modern organisation will have numerous types of users and employees who have different needs, and these days with hybrid working environments, the common perimeter of a corporate network has now changed from a traditional on-premise network to a mobile devices and users working remotely.
Conditional Access allows an organisation to provide a layer of security across their identities, devices and applications. Often, I have seen Conditional Access being either mis-configured, Switched off completely or having duplicate policies that cover the same conditions, which can often cause a lot of confusion for IT admins.

Fast forward to today, and the day of the “Hybrid working” is here to stay. It is a common need for all employees to work from home or work remotely, therefore the security perimeter now extends to mobile and BYOD devices.
Thankfully with tools such as Microsoft 365 and Microsoft Azure, the possibility for fully-remote working is here, and more and more organisations are catering for hybrid working with the use of modern cloud platforms. 

### Conditional Access Issues

As I described earlier, Conditional Access policies can often be hard to understand and hard to find what they are actually doing without going into the Azure Active Directory portal and viewing the settings of a policy itself. 
Conditional Access policies are often created on the fly, in a ad-hoc way, for example recently, I’ve had clients wanting to block countries such as Ukraine and Russia from their tenant. Which is a perfectly fine requirement, but without a framework or even a naming convention in use, Ad-hoc policies can often build up, adding to the confusion. 

There are many ways to structure Conditional Access policies. One approach is to structure policies based on the sensitivity of the resource being accessed. In practice, this approach can be difficult to implement in a way that still protects access to resources for various users.
Another approach is to try to define access policies based on where a user is in the organization. This approach might result in many Conditional Access policies and might be unmanageable for your IT department.

### Personas Personas Personas

One of the best ways I have seen and used personally, is a persona-based design. In this design, policies are designed in a way that they cater for all types of users in your organisation. In the Azure Active Directory world, Personas are identity types that share common organisation attributes, responsibilities, experiences, objectives, and access.
If you have a good understanding of how numerous different personas access and use your organisations applications and resources, It can provide an integral source of providing a zero-trust strategy in your organisation. 

#### So how do we get started with Personas?

Thankfully, Microsoft have come up with a list of suggested personas an organisation tends to have in their organisation. These are:


{{< img src="Personas.png" align="center">}}

These Personas can often be described by highlighting the type of users that an organisation may have, such as the below:

| **Persona** | **Example user** |
| --- | ----------- |
| **Internal** | Full time employee of an organisation, with standard access rights. |
| **External** | External contractor who has been given an account inside of an organisation, similar to a internal user. |
| **Admins**  | Accounts that have privileged access to corporate applications and data, normally separate accounts for administrative tasks |
| **Developers** |  Users who develop applications for corporate use, may need specialised access to applications and data |
| **Guests** | Users who have been invited into an Azure Active Directory Tenant and are from a third party. |
| **Guest Admins** | User accounts same as the above, but with access to privileged roles in an AAD Tenant |
| **Service Accounts** | Accounts that are user accounts but used for specialised use cases such as backups and legacy applications |
| **Workload Identities** |  Service principals and managed identities, used similarly to service accounts. |


<br>Alongside the above, there is another persona, which is the “global” persona. This Persona is used for users that aren’t part of another persona. This Persona will also contain policies that apply globally across all personas.

### Persona Cards

So with clients I have worked with, we often investigate the type of users an organisation has, and start creating Persona cards. A persona card will contain a high level overview of each persona, including how their identity and account are created, the devices they use and the level of access needed to specific applications. 
Once these Persona cards have been created, it can give an organisation a better insight into what controls they can put in place with Conditional Access Policies. You can download a sample Persona card below:

### Persona Template blank
### example Persona card

## Naming conventions for Conditional Access Policies

With a Persona based Conditional Access design, it may actually result in more policies being created than what existed before the design was implemented, but at least an organisation can be sure that each user has a basic level of security. 
With a large collection of policies, a naming convention is basically a requirement to allow IT and non-IT users understand what each policy is doing. Thankfully Microsoft again, provide excellent guidance in terms of what a Conditional Access policy should be named:

```<CANumber>-<Persona>-<PolicyType>-<App>-<Platform>-<GrantControl>-<OptionalDescription>```

An example of the above could look like:

```CA001 [Global] [Base protection] [all apps] [anyplatform] [grant]: Require MFA```

So by looking at the above Conditional Access policy, I can read from it that the policy is a global policy for all applications and device platforms, and requires Multi-Factor Authentication to grant access.

Instead of me repeating what Microsoft recommend, See the links at the bottom of this post to access the Conditional Access framework. This shows all the other key parts of the framework, such as policy numbering and the types of protection that should appear in Conditional Access

## So how has this worked in production?

Personas are a great little tool to use, and have helped with other tools, such as M365 compliance. Having an organisation create a persona card for each user type they have, will highlight some of the key areas that the organisation must lock down, such as access to key applications and administrative roles. 
At first, I found the Persona based framework a bit hard to implement as some clients have decided to just treat all users with the same brush, basically having the Global persona only. 

Also, this has been a great entry into Azure AD P2 licensing, and even Microsoft 365 E5. As identifying risky users and risky sign ins, have aided large organisations into a bigger insight into how their users access cloud applications.

Feel free to download the Persona cards and have a go at creating a card yourself based off a type of persona you have in your organisation. From there, you should be able to understand how a persona based framework can have an impact on your security posture.

## Links to take a look at

* [Conditional Access for Zero Trust - Azure Architecture Center | Microsoft Docs](https://docs.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-zero-trust)
* [Conditional Access design principles and dependencies - Azure Architecture Center | Microsoft Docs](https://docs.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-design)
* [Conditional Access architecture and personas - Azure Architecture Center | Microsoft Docs](https://docs.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-architecture)
* [Conditional Access framework and policies - Azure Architecture Center | Microsoft Docs](https://docs.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-framework)