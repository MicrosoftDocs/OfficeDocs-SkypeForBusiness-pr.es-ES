---
title: Exclusiones de análisis antivirus para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Resumen de interoperación de escáner antivirus con Skype para Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Exclusiones de análisis antivirus para Skype Empresarial Server 2015
 
Resumen de interoperación de escáner antivirus con Skype para Business Server 2015. 
  
Para asegurarse de que el programa antivirus no interfiere con el funcionamiento de Skype para Business Server 2015, debe excluir los directorios y procesos específicos para cada Skype para servidor Business Server 2015 o rol de servidor en el que se ejecuta un programa antivirus. Es necesario excluir los siguientes procesos y directorios:
  
> [!NOTE]
> Ubicaciones de archivos y carpetas enumerados a continuación son las ubicaciones predeterminadas para Skype para Business Server 2015. Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema. 
  
> [!IMPORTANT]
> Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión. 
  
- Skype para los procesos de negocio servidor 2015:
    
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
    
  - %systemroot%\system32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %SystemRoot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype Empresarial Server 2015
    
  - %programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor
    
  - %programfiles%\Common Files\Skype Empresarial Server 2015
    
  - %programfiles%\Common Files\Skype Empresarial Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.
    
  - Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener más información acerca de los archivos de datos y de registro para cada base de datos, incluidos los nombres predeterminados, consulte [la ubicación del archivo de registro y datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.
    
  - SQL Server datos y registro de archivos, los de la base de datos front-end de Skype para almacén de negocios y almacén de RtcDatabase incluidos. Normalmente, se encuentran en %localdrive%\CSData.
    

