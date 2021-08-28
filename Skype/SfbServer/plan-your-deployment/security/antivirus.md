---
title: Exclusiones de análisis antivirus para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general sobre la interoperación del antivirus con Skype Empresarial Server.
ms.openlocfilehash: e4016527937c7cfc3c39eb37d2a7b75202fad076
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588502"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusiones de análisis antivirus para Skype Empresarial Server

Información general sobre la interoperación del antivirus con Skype Empresarial Server.

Para asegurarse de que el analizador antivirus no interfiera con el funcionamiento de Skype Empresarial Server, debe excluir procesos y directorios específicos para cada rol de servidor o servidor de Skype Empresarial Server en el que ejecute un escáner antivirus. Estos son los procesos y directorios en cuestión:

> [!NOTE]
> Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas para Skype Empresarial Server. En el caso de haya ubicaciones especificadas para la organización que no sean las predeterminadas, exclúyalas en lugar de las ubicaciones predeterminadas mencionadas en este tema.

> [!IMPORTANT]
> Tenga en cuenta que algunos programas antivirus pueden necesitar rutas absolutas, no relativas, para su lista de exclusión.

- Skype Empresarial Server procesos:

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

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

- Windows Fabric Procesos de servicio de host:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Procesos de IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End procesos:

    > [!NOTE]
    > Tenga en cuenta que estas rutas de acceso son específicas SQL Server versión.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End procesos:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition Instancia RTC de instalación

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Directorios y archivos:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Tenga en cuenta que estas rutas de acceso son específicas Skype Empresarial Server versión.

  - %programfiles%\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Online

  - %SystemDrive%\RtcReplicaRoot

  - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.

  - Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener información detallada sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), consulte [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación.

  - SQL Server datos y archivos de registro, incluidos los de la base de datos front-end, el Skype Empresarial y el almacén RtcDatabase. Normalmente están en %localdrive%\CSData.