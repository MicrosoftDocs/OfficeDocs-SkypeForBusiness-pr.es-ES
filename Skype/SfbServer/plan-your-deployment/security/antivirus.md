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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general sobre la interoperación del escáner antivirus con Skype Empresarial Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832270"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusiones de análisis antivirus para Skype Empresarial Server

Información general sobre la interoperación del escáner antivirus con Skype Empresarial Server.

Para asegurarse de que el antivirus no interfiera con el funcionamiento de Skype Empresarial Server, debe excluir procesos y directorios específicos para cada servidor o rol de servidor de Skype Empresarial Server en el que ejecute un antivirus. Estos son los procesos y directorios en cuestión:

> [!NOTE]
> Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas de Skype Empresarial Server. En el caso de haya ubicaciones especificadas para la organización que no sean las predeterminadas, exclúyalas en lugar de las ubicaciones predeterminadas mencionadas en este tema.

> [!IMPORTANT]
> Tenga en cuenta que algunos programas antivirus pueden necesitar rutas absolutas, no relativas, para su lista de exclusión.

- Procesos de Skype Empresarial Server:

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

- Procesos del servicio host de Windows Fabric:

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

  - Instancia RTC de instalación standard edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Directorios y archivos:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Tenga en cuenta que estas rutas de acceso son específicas de la versión de Skype Empresarial Server.

  - %programfiles%\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.

  - Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener información detallada sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.

  - SQL Server datos y archivos de registro, incluidos los de la base de datos front-end, el almacén de Skype Empresarial y el almacén RtcDatabase. Normalmente se encuentran en %localdrive%\CSData.


