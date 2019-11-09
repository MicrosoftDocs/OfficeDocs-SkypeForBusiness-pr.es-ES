---
title: Exclusiones de detección antivirus para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general sobre la interacción del escáner antivirus con Skype empresarial Server.
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074632"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusiones de detección antivirus para Skype empresarial Server

Información general sobre la interacción del escáner antivirus con Skype empresarial Server.

Para asegurarse de que el detector antivirus no interfiera con el funcionamiento de Skype empresarial Server, debe excluir los procesos y directorios específicos de cada rol de servidor o servidor de Skype empresarial Server en el que ejecute un detector de virus. Es necesario excluir los siguientes procesos y directorios:

> [!NOTE]
> Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas de Skype empresarial Server. Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.

> [!IMPORTANT]
> Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.

- Procesos de Skype empresarial Server:

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
  
  - LyncBackupService. exe

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

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- Procesos del back-end de SQL Server:

    > [!NOTE]
    > Tenga en cuenta que estas rutas dependen de la versión de SQL Server.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- Procesos del front-end de SQL Server:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Instancia RTC de instalación Standard Edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Directorios y archivos:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Tenga en cuenta que estas rutas son específicas de la versión de Skype empresarial Server.

  - %programfiles%\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor

  - %programfiles%\Common Files\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Online

  - %SystemDrive%\RtcReplicaRoot

  - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.

  - Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para más información sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), vea [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.

  - Archivos de datos y de registro de SQL Server, incluidos los de la base de datos front-end, la tienda de Skype empresarial y la tienda RtcDatabase. Normalmente, se encuentran en %localdrive%\CSData.


