---
title: 'Lync Server 2013: Exclusiones de la detección de virus'
TOCTitle: Exclusiones de la detección de virus para Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn440138(v=OCS.15)
ms:contentKeyID: 59602838
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exclusiones de la detección de virus para Lync Server 2013

 

_**Última modificación del tema:** 2015-11-02_

Para asegurarse de que el detector de virus no interfiera en el funcionamiento de Lync Server 2013, deberá excluir determinados procesos y directorios de cada servidor o rol de servidor de Lync Server 2013 en los que ejecute un detector de virus. Los siguientes procesos y directorios deben excluirse:


> [!NOTE]
> La ubicación de las carpetas y los archivos indicados a continuación es la ubicación predeterminada para Lync Server 2013. En el caso de que haya ubicaciones especificadas para la organización que no sean las predeterminadas, excluya esas en lugar de las ubicaciones predeterminadas mencionadas en este tema.



  - Procesos de Lync Server 2013:
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
      - IMMCUSvc.exe
    
      - LysSvc.exe
    
      - MasterReplicatorAgent.exe
    
      - MediaRelaySvc.exe
    
      - MediationServerSvc.exe
    
      - MRASSvc.exe
    
      - OcsAppServerHost.exe
    
      - ReplicaReplicatorAgent.exe
    
      - ReplicationApp.exe
    
      - RtcHost.exe
    
      - RTCSrv.exe
    
      - XmppProxy.exe
    
      - XmppTGW.exe

  - Procesos del servicio de host de Windows Fabric:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Procesos de IIS:
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - Procesos del back-end de SQL Server:
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - Procesos del front-end de SQL Server:
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSMQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSMQL\\Binn\\SQLServr.exe

  - Directorios y archivos:
    
      - %systemroot%\\System32\\LogFiles
    
      - %systemroot%\\SysWow64\\LogFiles
    
      - %systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %SystemDrive%\\RtcReplicaRoot
    
      - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.
    
      - Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener información detallada sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), consulte [Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) en la documentación de implementación.
    
      - Datos y archivos de registro de SQL Server, incluidos los de la base de datos front-end, el almacén de Lync y el almacén de RtcDatabase. Normalmente están en %localdrive%\\CSData.

