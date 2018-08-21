## DFS Namespace
- [DFS Server and Storage Question](https://www.reddit.com/r/sysadmin/comments/8zf8v9/dfs_server_and_storage_question/)
- [Storage in Windows Server](https://docs.microsoft.com/en-us/windows-server/storage/storage)
- [DFS Namespaces overview](https://docs.microsoft.com/en-us/windows-server/storage/dfs-namespaces/dfs-overview)
- [Tuning replication performance in DFSR - especially on Win2008 R2](https://blogs.technet.microsoft.com/askds/2010/03/31/tuning-replication-performance-in-dfsr-especially-on-win2008-r2/)
- [Five ways to check your DFS-Namespaces DFS-N configuration with the DFSDIAG.EXE tool](https://blogs.technet.microsoft.com/josebda/2009/07/15/five-ways-to-check-your-dfs-namespaces-dfs-n-configuration-with-the-dfsdiag-exe-tool/)
- [Three ways to design your DFS Namespaces](https://blogs.technet.microsoft.com/josebda/2009/08/21/three-ways-to-design-your-dfs-namespaces/)
- [Common DFSN Configuration Mistakes and Oversights](https://blogs.technet.microsoft.com/askds/2012/07/24/common-dfsn-configuration-mistakes-and-oversights/).
- [Help with DFS-N](https://www.reddit.com/r/sysadmin/comments/951fdj/help_with_dfsn/)


## DFS Replication
- [DFS Replication in Windows Server 2012 R2: If You Only Knew the Power of the Dark Shell](https://blogs.technet.microsoft.com/filecab/2013/08/20/dfs-replication-in-windows-server-2012-r2-if-you-only-knew-the-power-of-the-dark-shell/)
- [Having DFSR issues, need suggestions on how to fix this](https://www.reddit.com/r/sysadmin/comments/7we7hs/having_dfsr_issues_need_suggestions_on_how_to_fix/)
- [Common DFSR Configuration Mistakes and Oversights](https://blogs.technet.microsoft.com/askds/2010/11/01/common-dfsr-configuration-mistakes-and-oversights/)
- [Understanding (the Lack of) Distributed File Locking in DFSR](https://blogs.technet.microsoft.com/askds/2009/02/20/understanding-the-lack-of-distributed-file-locking-in-dfsr/)

## Others
- [You need this: Organize, share, and manage files with Microsoft DFS](http://webcache.googleusercontent.com/search?q=cache:oiSJg_WD8_QJ:techgenix.com/microsoft-dfs/+&cd=1&hl=nl&ct=clnk&gl=nl)
- [Access-Based Enumeration ABE Concepts part 1](https://blogs.technet.microsoft.com/askds/2016/09/01/access-based-enumeration-abe-concepts-part-1-of-2/)
- [Access-Based Enumeration ABE Concepts part 2](https://blogs.technet.microsoft.com/askds/2016/09/21/access-based-enumeration-abe-troubleshooting-part-2-of-2/)
- [Microsoft File Server Migration Toolkit 1.2](https://www.microsoft.com/en-us/download/details.aspx?id=10268)
- [NTFSSecurity Tutorial 1 – Getting, adding and removing permissions](https://blogs.technet.microsoft.com/fieldcoding/2014/12/05/ntfssecurity-tutorial-1-getting-adding-and-removing-permissions/)
- [NTFSSecurity Tutorial 2 – Managing NTFS Inheritance and Using Privileges](https://blogs.technet.microsoft.com/fieldcoding/2014/12/05/ntfssecurity-tutorial-2-managing-ntfs-inheritance-and-using-privileges/)
- [Windows Server: Deleting ISOs (and .vhd/.vhdx) does not actually free up space..? (mostly a curiosity)](https://www.reddit.com/r/sysadmin/comments/8vhmlz/windows_server_deleting_isos_and_vhdvhdx_does_not/)

## Youtube
- [Techdays 2011 - Role-Based Management Extreme Makeover](https://www.youtube.com/watch?v=IKzokBgCp60)

## Tools
- [NTFS Permissions Reporter Free Edition](http://cjwdev.co.uk/Software/NtfsReports/Info.html)
- [Access Enum](https://docs.microsoft.com/en-us/sysinternals/downloads/accessenum)
- [Powershell Export Folder Permissions to CSV file](https://community.spiceworks.com/scripts/show/1070-export-folder-permissions-to-csv-file)
- [Forensics: Active Directory ACL investigation](https://blogs.technet.microsoft.com/pfesweplat/2017/01/28/forensics-active-directory-acl-investigation/)

## Information
1. Give authenticated users share permission and control access with NTFS permissions
1. Enable deduplication on both servers if there are multi
1. DFS Info
  1. DFS Namespaces (DFS-N) does not require DFS Replication (DFS-R) to work.
  1. If you choose to use DFS-R, don't enable it for all shares right off the bat - test with one.
  1. If you do use DFS-N with multiple targets (assuming you are using DFS-R to keep the targets in sync) - do NOT allow round-robin. Always set one target to primary, and the other as failover (unless you have some branch locations but you probably want to start looking into Branch Cache at that point)
