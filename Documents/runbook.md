# How to Create a Runbook: A Guide for Sysadmins & MSPs | Process Street

Benjamin Brandall  September 20, 2017

13-16 minutes

------

![img](https://www.process.st/wp-content/uploads/2017/09/Runbook-for-MSP.png)

How do you name a new server, export config data, or fix that one really annoying bug that keeps popping up every 2nd Thursday?

For prepared IT professionals, that information is stored in a runbook. A runbook is a set of [standardized](https://www.process.st/standardizing-processes/) documents, references and [procedures](https://www.process.st/how-to-write-a-procedure/)  that explain common recurring IT tasks. Instead of figuring out the  same problem time and time again, you can refer to your runbook for an  optimal way to get the work done. What’s more, you can also [delegate tasks](https://www.process.st/how-to-delegate-tasks/) and [onboard employees](https://www.process.st/new-employee-onboarding-process/) more effectively if you have documentation to train them with.

Whenever you do a task, think of this quote:

> *“Will you remember how to do these things 6 months  from now? I find myself having to re-invent a process from scratch if I  haven’t done it in a few months (or sometimes just a few days!). Not  only do I re-invent the process, I repeat all my old mistakes and learn  from them again. What a waste of time.” —* [Tom Limoncelli](https://twitter.com/yesthattom), [The Operations Report Card](http://opsreportcard.com/section/11) 

In short, the less time wasted figuring out how to do a task, the better it’ll be for your [business efficiency](https://www.process.st/business-efficiency/), productivity, and sanity.

This post will look at runbook examples, documentation methods, and  some processes you can use in your own business. Also, it will show you  how to use Process Street as your cloud-based runbook for all IT  documentation.

First, let’s look at some example runbooks so we can get context on what I’m going to talk about.

## The 2 types of runbook

Runbook is a broad term. It can refer to [two kinds](https://www.ibm.com/support/knowledgecenter/en/SSZQDR/com.ibm.rba.doc/CR_create_new_rb.html) of documentation:

- **General documentation** updated by a sysadmin when new procedures arise or evolve
- **Specialized documentation** written for one team, one use-case, or one system

With this in mind, it’s likely that any one IT department or sysadmin  will have multiple runbooks that assist with their routine tasks and  act as reference manuals for special cases.

For example, to build a **general daily tasks** runbook inside [Process Street](http://process.st/) you could use this template as a starting point:

Runbook documentation is precise. It’s specific to the systems your  company is running, and the custom configurations you’ve made. While the  process above can’t cater to your systems and existing procedures, it  can act as a demonstration or template you can fill in with your common  daily tasks.

As for **specialized documentation:** this varies drastically for each organization. The below example — [Installation Runbook for Palo Alto Networks virtual Firewall and Juniper Contrail plugin for Fuel](https://content.mirantis.com/rs/451-RBY-185/images/PaloAltoNetworksvFWwithContrailFuelPluginrunbook.pdf) — contains diagrams, tables and procedures that will guide the user through every step and contingency.

![img](https://www.process.st/wp-content/uploads/2017/09/Snip20170912_13.png)

Aside from system-specific documentation, most organizations will prepare **use-case specific documentation**. The most operationally-vital use-case for documentation in IT will always be **disaster recovery**, which needs to be executed quickly and thoroughly.

[Xtium](http://www.xtium.com/) has released a [33-page disaster recovery runbook template](http://www.jimrcpa.com/~jimrcpa/images/Disaster Recovery Template from Xtium.pdf) which runs you through example procedures and recommendations for creating and updating your disaster recovery procedures.

![img](https://www.process.st/wp-content/uploads/2017/09/Disaster-Recovery-Template-Runbook.png)

A [disaster recovery process](http://www.omsar.gov.lb/ICTSG/204SC/12.1_SOP_7_Disaster_Recovery_Procedures.htm)  is something many businesses only make when it’s too late. The top  three causes of downtime are power outages, hardware failures, and  network failures. How do you respond to these incidents in each case?

For a cloud-based option, you can edit our information security  incident response template, for example of one kind of disaster  recovery:

## How to create a runbook

Every runbook is unique and specific. The actual content will be  specific to your needs. The methodology, however, is the same as it is  for all [process creation](https://www.process.st/when-to-create-processes/).  The first stage is to plan which procedures need to be documented in  your runbook. When you have a list, you can write them up in detail.  After field testing a process, you can make updates and optimizations as  necessary.

Author and ex-Google sysadmin Tom Limoncelli recommends that each runbook contains [7 sections](http://opsreportcard.com/section/11):

1. **Overview:** Overview of the service: what is it, why  do we have it, who are the primary contacts, how to report bugs, links  to design docs and other relevant information.
2. **Build:** How to build the software that makes the  service. Where to download it from, where the source code repository is,  steps for building and making a package or other distribution  mechanisms. If it is software that you modify in any way (open source  project you contribute to or a local project) include instructions for  how a new developer gets started. Ideally the end result is a package  that can be copied to other machines for installation.
3. **Deploy:** How to deploy the software. How to build a  server from scratch: RAM/disk requirements, OS version and  configuration, what packages to install, and so on. If this is automated  with a configuration management tool like cfengine/puppet/chef (and it  should be), then say so.
4. **Common Tasks:** Step-by-step instructions for common  things like provisioning (add/change/delete), common problems and their  solutions, and so on.
5. **Pager Playbook**: A list of every alert your  monitoring system may generate for this service and a step-by-step “what  do to when…” for each of them.
6. **DR:** Disaster Recovery Plans and procedure. If a service machine died how would you fail-over to the hot/cold spare?
7. **SLA:** Service Level Agreement. The (social or real)  contract you make with your customers. Typically things like Uptime Goal  (how many 9s), RPO (Recovery Point Objective) and RTO (Recovery Time  Objective).

The way that’s structured is up to you, but it’d best to put non-interactive documents in [cloud storage](https://www.process.st/dropbox-vs-google-drive/), and then use a [workflow app](https://www.process.st/workflow-apps/) to record and assign the common tasks.

### 1. Planning

Which procedures do you regularly execute? Some ideas:

- Disaster recovery
- Data backup
- New user setup
- Virtual machine troubleshooting
- Patch management

A runbook should contain your most regularly executed tasks, as well  as instructions for complex semi-regular issues with easily-forgotten  details.

Our CTO, Cameron, uses Process Street to fire an [SSL renewal checklist](http://process.st/checklist/ssl-certificate-renewal-process)  once every three years (because it’s an archaic and fiddly task), but  he also runs daily and weekly checklists for system maintenance.

### 2. Writing

It’s sustainable and scalable to **write runbook documentation in language that anyone can understand**  because later down the line staff of every level need to be able to  understand it for training and onboarding purposes. This means cutting  jargon, avoiding abbreviations, and making no assumptions about the  skill level of the user.

To create a process, it’s best to actually **do the task and record your work**.  You can do this by taking notes of every button you click, and all of  the information you enter, but you could also just record your screen  and take notes afterwards. That way, you get a realistic step-by-step  procedure that can be replicated by non-technical staff, too.

To summarize:

1. Choose a process to document (it should be a common cause for error, or a critical regular task)
2. Start recording your screen
3. Work through the task as you normally would
4. Pause the screenshot at each action and note down everything you do  (“Open the Start menu. All programs > Accessories > Paint”)
5. For actions that need more explanation, take a screenshot of the screencast and use it in the runbook
6. Repeat until the end of the screencast

Make sure to **pull together any resources you used** while doing the task:

- Reference documentation
- Network diagrams
- Login credentials
- Config information

Process Street has everything you need to create rich-media processes  that include images, videos, sub-checklists, code snippets and more.  You can also easily update your processes and have the changes reflected  to all users.

### 3. Improving

It’s one thing to document a process for yourself, but having that  process executed by someone else in a real-world situation is a  different story. The first time your process is battle-tested, you’ll  notice any errors you’ve made by seeing the efficiency and accuracy of  the work done.

A good way to improve processes is to be present when the  instructions are being carried out, then hand the process off to be  updated and used by more general staff.

Process consultant [Ian James](http://theprocessconsultant.com/) says that improving a process after it’s documented includes [11 steps](http://theprocessconsultant.com/infographic-process-improvement-preparations/):

1. **Get everyone on board.** When you’re making changes  to the generally accepted way of doing work, it’s likely you’re going to  need approval from higher-ups, and time from everybody involved.
2. **Choose the right process to optimize.** Which process is causing pains, needs to be handed off, or is too out of date to be useful?
3. **Calculate the time and resources you’ll need.** A pitch to upper management will need backing up with data.
4. **Act when the time is right.** Process improvement is necessary, but often that’s only apparent in a crisis.
5. **Set expectations for everyone involved.** If you’ll need 5 hours per week of a certain team’s time, and expect the project to take three weeks, make it clear.
6. **Offer process training.** Thinking critically about business systems is a learned skill. If your team doesn’t have training, prepare by getting them some.
7. **Build the process out in a workflow application.** Paper or Word documents will eventually fall flat. Pages can get lost, and collaboration is impossible in Word.
8. **Know why you’re improving the process.** Is it  because it’s done frequently, has a high margin for variance, or because  it needs to be predictable? Categorize the process by this criteria.
9. **Select your team size.** Choose a small number of trained individuals to help.
10. **Pick the right team members.** The only people who should be involved with optimizing a process are the people who run it.
11. **Get together in a dedicated room.** Ian James [reports](http://theprocessconsultant.com/infographic-process-improvement-preparations/) that projects where the team collaborates in a physical space have a 200% higher success rate.

We’ve also put together a process specifically for [process improvement](https://www.process.st/process-improvement/):

## Running your IT processes with Process Street

[Process Street](http://process.st/) is a workflow  documentation platform that lets you document your processes and then  track progress each time the process is run. Insert form fields,  automation, and supporting files into your process documents, and then  assign them to members of your team.

Process Street’s folder structure lends itself well to IT runbooks,  and we’ve also got plenty of pre-made processes for IT teams, and  integration with [ITGlue](http://itglue.com/).

### Using pre-made process templates

We’ve put together three process packs for IT businesses:

- [12 IT Processes to Solve Your Computer Woes](http://process.st/it-processes)
- [8 IT Security Processes to Protect and Manage Company Data ](https://www.process.st/it-security-processes/)
- [7 Documented Processes for IT, MSPs and System Administrators ](https://www.process.st/processes-for-it-msps/)

These packs collect the following templates:

- [Naming Convention Design (Servers, Computers, IT Assets)](https://www.process.st/checklist/naming-convention-design-servers-computers-it-assets/)
- [Cisco Router Setup](https://www.process.st/checklist/cisco-router-setup/)
- [Vendor Management: Supplier Evaluation](https://www.process.st/checklist/vendor-management-supplier-evaluation/)
- [Vendor Management: Contract Negotiation](https://www.process.st/checklist/vendor-management-contract-negotiation/)
- [IT Service Call Process](https://www.process.st/checklist/it-service-call-process/)
- [Scheduled Maintenance Notification](https://www.process.st/checklist/scheduled-maintenance-notification/)
- [Patch Management](https://www.process.st/checklist/patch-management/)
- [Network Security Management](https://www.process.st/checklist/network-security-management/)
- [Client Data Backup Best Practices](https://www.process.st/checklist/client-data-backup-best-practices/)
- [Computer Maintenance Guide](https://www.process.st/checklist/computer-maintenance-guide/)
- [Inventory Management Process](https://www.process.st/checklist/inventory-management-process)
- [Server Setup Process](https://www.process.st/checklist/ubuntu-server-setup-process/)
- [Virtual Private Server Setup](https://www.process.st/checklist/virtual-private-server-setup/)
- [IT Support Process](https://www.process.st/checklist/it-support-process/)
- [Helpdesk Management](https://www.process.st/checklist/helpdesk-management/)
- [Server Maintenance Checklist](https://www.process.st/checklist/server-maintenance-checklist/)
- [Server Security Checklist](https://www.process.st/checklist/server-security-checklist/)
- [Information Security Incident Response](https://www.process.st/checklist/information-security-incident-response/)
- [SQL Server Audit Checklist](https://www.process.st/checklist/sql-server-audit-checklist/)
- [Privileged Password Management](https://www.process.st/checklist/privileged-password-management/)
- [Network Administrator Daily Tasks](https://www.process.st/checklist/network-administrator-daily-tasks/)
- [Network Security Audit Checklist](https://www.process.st/checklist/network-security-audit-checklist/)
- [Firewall Audit Checklist](https://www.process.st/checklist/firewall-audit-checklist/)
- [VPN Configuration](https://www.process.st/checklist/vpn-configuration/)
- [Apache Server Setup](https://www.process.st/checklist/setup-apache-server/)
- [Email Server Security](https://www.process.st/checklist/email-server-security/)
- [Penetration Testing](https://www.process.st/checklist/penetration-testing/)

To add a template to your Process Street organization, just click the  “I want this for my business” button, and it’ll be automatically copied  in.

![img](https://www.process.st/wp-content/uploads/2017/09/Add-Template-to-Process-Street-Org.png)

Whether you copy and modify our pre-made templates or make your own  from scratch, you’ll want to create a folder structure so you can easily  filter the processes and control access.

### Structuring your IT processes

Process Street has folders, sub-folders, and tags. This gives you a  lot of control over the way you structure processes in your  organization. For example, an organization for multiple departments  might have a different folders on their home screen for each department.

In the gif below, I go through the layers of an example structure for  IT processes, with the home screen divided up by department and then  the IT folder divided into folders such as hardware setup, maintenance,  security, etc.

![img](https://www.process.st/wp-content/uploads/2017/09/IT-Folder-Structure-Process-Street.gif)

You can create new folders with the green ‘New’ button on the left sidebar. Go inside your IT folder to create subfolders:

![img](https://www.process.st/wp-content/uploads/2017/09/Subfolder-IT-Folder-Structure-Process-Street.gif)

You can use the same ‘New’ button on the sidebar to add a template to  the folder. For example, you might want to use one of our VPN  processes:

![img](https://www.process.st/wp-content/uploads/2017/09/Pre-Made-IT-Folder-Structure-Process-Street.gif)

It makes sense to organize files into their proper folders, but you can also use folders to [control access management](https://www.process.st/help/docs/folder-permissions/). Read more about [folders in our help documentation](https://www.process.st/help/docs/folders/).

With Process Street, you can use and optimize your processes in one  central place. This even means you can integrate with tools like ITGlue.

### Integrating Process Street with ITGlue

ITGlue lets you set up notifications when key events happen on your  systems that need dealing with: SSL renewal, licenses, maintenance,  audits, etc. These are linked to your ITGlue documentation, and live  alongside the rest of your key IT knowledge such as network structure  and inventory.
 ![img](https://www.process.st/wp-content/uploads/2017/09/Create-ITGlue-Notification.png)
 Process Street can be integrated into this notification system to act as  a runbook. For example, whenever your SSL certificate is running out,  ITGlue will notify Process Street which will then run a checklist from  our SSL renewal checklist and email the person in charge of getting the  job done.
 ![img](https://s3-us-west-2.amazonaws.com/bolin/wp-content/uploads/2017/08/Configure-Process-Street-checklist-in-Zapier.png)
 Read more about setting up this integration [here](https://www.process.st/help/docs/itglue/).

## Get started with your runbook

Runbooks make it easier for you to remember the ideal methods you  come up with, and to delegate work to a team. You can manage your IT  documentation with Process Street, and use documentation templates  created specifically for IT.

**Get your free Process Street account to start systemizing and scaling your IT operations.**

​            