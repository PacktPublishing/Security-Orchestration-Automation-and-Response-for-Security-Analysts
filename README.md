# Security Orchestration, Automation, and Response for Security Analysts

<a href="https://www.packtpub.com/product/Security-Orchestration-Automation-and-Response-for-Security-Analysts/9781803242910"><img src="https://m.media-amazon.com/images/I/41TMVPSVEzL.jpg" alt="Book Name" height="256px" align="right"></a>

This is the code repository for [Security Orchestration, Automation, and Response for Security Analysts](https://www.packtpub.com/product/Security-Orchestration-Automation-and-Response-for-Security-Analysts/9781803242910), published by Packt.

**Learn the secrets of SOAR to improve MTTA and MTTR and strengthen your organization's security posture**

## What is this book about?
What your journey will look like With the help of this expert-led book, you’ll become well versed with SOAR, acquire new skills, and make your organization's security posture more robust.You’ll start with a refresher on the importance of understanding cyber security, diving into why traditional tools are no longer helpful and how SOAR can help.Next, you’ll learn how SOAR works and what its benefits are, including optimized threat intelligence, incident response, and utilizing threat hunting in investigations.
You’ll also get to grips with advanced automated scenarios and explore useful tools such as Microsoft Sentinel, Splunk SOAR, and Google Chronicle SOAR. The final portion of this book will guide you through best practices and case studies that you can implement in real-world scenarios.By the end of this book, you will be able to successfully automate security tasks, overcome challenges, and stay ahead of threats.
This book covers the following exciting features: 
* How to reap the general benefits of using the SOAR platform
* Transforming manual investigations into automated scenarios
* How to manage known false positives and low-severity incidents for faster resolution
* Tips and tricks for using various Microsoft Sentinel playbook actions
* All you need to know about tools such as Google Chronicle SOAR, Microsoft Sentinel, and Splunk SOAR

If you feel this book is for you, get your [copy](https://www.amazon.com/Security-Orchestration-Automation-Response-Analysts-ebook/dp/B0BMLZW114) today!

<a href="https://www.packtpub.com/?utm_source=github&utm_medium=banner&utm_campaign=GitHubBanner"><img src="https://raw.githubusercontent.com/PacktPublishing/GitHub/master/GitHub.png" alt="https://www.packtpub.com/" border="5" /></a>

## Instructions and Navigations
All of the code is organized into folders. For example, Chapter05.

The commands will look like the following:
```
SentinelHealth
| where SentinelResourceType == "Automation rule"
| mv-expand TriggeredPlaybooks = ExtendedProperties.TriggeredPlaybooks
| extend runId = tostring(TriggeredPlaybooks.RunId)
| join (AzureDiagnostics
   | where OperationName == "Microsoft.Logic/workflows/workflowRunCompleted"
   | project
       resource_runId_s,
       playbookName = resource_workflowName_s,
       playbookRunStatus = status_s)
    on $left.runId == $right.resource_runId_s
   | project
       RecordId,
       TimeGenerated,
       AutomationRuleName= SentinelResourceName,
       AutomationRuleStatus = Status,Description,
       workflowRunId = runId,
       playbookName,playbookRunStatus

```

**Following is what you need for this book:**
You'll get the most out of this book if You're a junior SOC engineer, junior SOC analyst, a DevSecOps professional, or anyone working in the security ecosystem who wants to upskill toward automating security tasks
You often feel overwhelmed with security events and incidents you have general knowledge of SIEM and SOAR, which is a prerequisite you’re a beginner, in which case this book will give you a head start
You’ve been working in the field for a while, in which case you’ll add new tools to your arsenal. 

With the following software and hardware list you can run all code files present in the book (Chapter 1-9).

### Software and Hardware List

| Chapter  | Software required                                         | OS required                       |
| -------- | ----------------------------------------------------------| ----------------------------------|
| 1-9      | Microsoft Azure Account, Microsft Excel                   | Windows, Mac OS X, and Linux (Any)|


We also provide a PDF file that has color images of the screenshots/diagrams used in this book. [Click here to download it](https://packt.link/Uz9ge).

### Related products <Other books you may enjoy>
* Agile Security Operations [[Packt]](https://www.packtpub.com/product/agile-security-operations/9781801815512) [[Amazon]](https://www.amazon.com/Agile-Security-Operations-Engineering-detection/dp/1801815518)

* Aligning Security Operations with the MITRE ATT Framework [[Packt]](https://www.packtpub.com/product/aligning-security-operations-with-the-mitre-attck-framework/9781804614266) [[Amazon]](https://www.amazon.com/Aligning-Security-Operations-MITRE-Framework/dp/1804614262)

## Get to Know the Author
**Benjamin Kovacevic**
He is a cyber-security enthusiast with hands-on experience with Microsoft XDR and SIEM platforms. Currently working with Microsoft Sentinel as a Product Manager, he is focusing on the SOAR component of the solution and working on new capabilities that will help SOCs improve their investigation and response. Benjamin is constantly working to improve his knowledge about cyber-security, as well as to share knowledge about Microsoft SOAR. He is the author of Microsoft Sentinel Automation training, as well as blog posts around tips and tricks to jump-start with Microsoft Sentinel Automation.
