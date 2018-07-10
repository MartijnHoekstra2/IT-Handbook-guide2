## System Center Configuration Manager

#### Info
* [System Center Dudes](https://www.systemcenterdudes.com/)
* [System Center ConfigMgr](http://www.scconfigmgr.com/)
* [PrajwalDesai Blog](https://prajwaldesai.com/system-center/)
* [SMS, SCCM, SCCM Current Branch, SCCM Technical Preview](https://www.windows-noob.com/forums/forum/121-sms-sccm-sccm-current-branch-sccm-technical-preview/)
* [Installing and Configuring SCCM 2016 – Stage 1 Prerequisites](https://dailysysadmin.com/KB/Article/578/installing-and-configuring-sccm-2016-stage-1-prerequisites/)
* [SCCM and MDT – List of variables](http://www.hayesjupe.com/sccm-and-mdt-list-of-variables/)
* [Five things to not screw up with SCCM](https://blog.aksysadmin.org/2017/09/07/five-things-to-not-screw-up-with-sccm)

#### Youtube
* [SCCM Tutorial for Beginners - Walkthrough and Configuration for Post Installation](https://www.youtube.com/watch?v=3-2qhfvt8vo&list=PL60ejEuI_nxuFw3eWRCxmffag_nYUz4PZ&app=desktop)
* [OSD with Configuration Manager Video Tutorial Series Overview](https://blogs.technet.microsoft.com/configurationmgr/2018/07/09/osd-with-configuration-manager-video-tutorial-series-overview/)
* [System Center Configuration Manager OSD Video Tutorial: Part I – Introduction and Basics](https://blogs.technet.microsoft.com/configurationmgr/2018/07/09/osd-video-tutorial-part-i-introduction-and-basics/)

#### Gotcha's
1. Make sure you have your AD under control
1. Without governance, SCCM can cause a great deal of chaos
1. No maintenance window = 24/7 maintenance window
  1. Establish a maintenance window from the beginning
  1. Ensure every machine has a maintenance window (unless it's not critical and user-facing)
1. Consider establishing an all-inclusive collection for the sole purpose of assigning a non-recurring maintenance window in the past
1. Don't house the DB on a shared SQL instance
1. Start with Current Branch to simplify your life
1. Never change the query of a dynamic collection that has active deployments
1. Think out your application detection rules, considering future upgrades to self-updating apps
1. Enable BranchCache
1. create Distribution Point Groups from the start (even if you only have 1 DP), and then deploy all content to that DP Group, this way if you ever grow and add a 2nd or 3rd DP it will automatically get all your content without any extra work once you add it to the group.
1. Take the time to design the solution you need and require which you can also use for the future. Spend the extra month on design considerations if you have to.
1. Attention should be paid to accounts used for the services, eg. the network access account is available in clear text in some places and some people make this an SCCM Admin account... and also, plan your RBAC and Limiting collections before you do anything. Think long and hard before you put an SCCM agent on domain controllers. The SCCM client runs on a computer under the SYSTEM account. That means anyone with access to deploy to the domain controllers in SCCM becomes effectively a domain admin.
1. I would recommend getting a consultant either from Microsoft or someone that specializes in SCCM, especially if you aren't as familiar with it. We upgraded our terrible SCCM 2012 environment to SCCM 2016 and it works SO much better because of the AWESOME consultant that we had.
1. A final tip is to do with creating master images for deployment, for this I would strongly recommend you don't use SCCM for image creation as it is so fiddly and not helpful at all, instead you should spin up a separate MDT deployment and use that for image creation and then copy the WIM files over to SCCM for deployment.
