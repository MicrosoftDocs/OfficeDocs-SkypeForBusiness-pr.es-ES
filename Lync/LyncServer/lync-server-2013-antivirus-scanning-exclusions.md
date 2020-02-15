---
title: 'Lync Server 2013: exclusiones de detección de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8faeba1d3b661110bcaf633d3c780dc2c2ad2b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Exclusiones de detección de virus para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-02_

Para asegurarse de que el detector de virus no interfiera con el funcionamiento de Lync Server 2013, debe excluir procesos y directorios específicos para cada rol de servidor o servidor de Lync Server 2013 en el que ejecute un detector de virus. Estos son los procesos y directorios en cuestión:

<div>


> [!NOTE]  
> Las ubicaciones de archivos y carpetas que se enumeran a continuación son las ubicaciones predeterminadas de Lync Server 2013. En el caso de haya ubicaciones especificadas para la organización que no sean las predeterminadas, exclúyalas en lugar de las ubicaciones predeterminadas mencionadas en este tema.



</div>

<div>


> [!IMPORTANT]  
> Tenga en cuenta que algunos programas antivirus pueden necesitar rutas de ruta absolutas, no relativas para la lista de exclusión.



</div>

  - Lync Server 2013 procesos de:
    
      - Abel. exe
    
      - AcpMcuSvc. exe
    
      - ASMCUSvc. exe
    
      - AVMCUSvc. exe
    
      - ChannelService. exe
    
      - ClsAgent. exe
    
      - ComplianceService. exe
    
      - DataMCUSvc. exe
    
      - Inproxy. exe
    
      - FileTransferAgent. exe
    
      - IMMCUSvc. exe
    
      - LysSvc. exe
    
      - MasterReplicatorAgent. exe
    
      - MediaRelaySvc. exe
    
      - MediationServerSvc. exe
    
      - MRASSvc. exe
    
      - OcsAppServerHost. exe
    
      - ReplicaReplicatorAgent. exe
    
      - ReplicationApp. exe
    
      - RtcHost. exe
    
      - RTCSrv. exe
    
      - XmppProxy. exe
    
      - XmppTGW. exe

  - Procesos del servicio host de Windows Fabric:
    
      - Fabric. exe
    
      - FabricDCA. exe
    
      - FabricHost. exe

  - Procesos de IIS:
    
      - % SystemRoot%\\system32\\Inetsrv\\, w3wp. exe
    
      - % SystemRoot%\\SysWOW64\\Inetsrv\\. exe

  - Procesos back-end de SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. Papelera\\de Reporting Services\\ReportServer\\bin\\ReportingServicesService. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. Papelera\\\\OLAP\\de MSSQLServer MSMDSrv. exe

  - Procesos front-end de SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\SQLServr. exe

  - Directorios y archivos:
    
      - archivos de registro\\de\\% SystemRoot% system32
    
      - % SystemRoot%\\archivos\\de registro SysWow64
    
      - % SystemRoot%\\Microsoft.net\\\\ensamblado\_GAC MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - Archivos\\\\comunes de% ProgramFiles% nodo de monitor\\de Microsoft Lync Server 2013
    
      - Archivos\\comunes de\\% ProgramFiles% Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.
    
      - Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener información detallada sobre los archivos de datos y de registro de cada base de datos, incluidos los nombres predeterminados, consulte [SQL Server Data and log file Placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) en la documentación referente a la implementación.
    
      - Archivos de registro y datos de SQL Server, incluidos los de la base de datos front-end, la tienda Lync y el almacén RtcDatabase. Normalmente se encuentran en% UnidadLocal%\\CSData.

</div>

<span> </span>

</div>

</div>

</div>

