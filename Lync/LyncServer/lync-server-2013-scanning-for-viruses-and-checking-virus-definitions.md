---
title: 'Lync Server 2013: Scanning for viruses and checking virus definitions'
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720909(v=OCS.15)
ms:contentKeyID: 62246703
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Scanning for viruses and checking virus definitions in Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

We highly recommend installing an IM-level antivirus product. IM is a well-known source for quickly spreading both virus and malicious software throughout an organization. Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.

In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.

Keeping scanner engines and virus definitions updated is very important. Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.

> [!IMPORTANT]  
> When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption. For the full list of exclusions, see <a href="https://support.microsoft.com/kb/943620" class="uri">https://support.microsoft.com/kb/943620</a>.


