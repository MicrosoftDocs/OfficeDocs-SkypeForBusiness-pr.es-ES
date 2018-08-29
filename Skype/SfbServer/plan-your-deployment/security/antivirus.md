---
title: Análisis de exclusiones para Skype para Business Server del antivirus
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general de interoperación del detector de virus con Skype para Business Server.
ms.openlocfilehash: 1078b3c0a28573e84235cbd39a11a6aa84a58b47
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250027"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Análisis de exclusiones para Skype para Business Server del antivirus

Información general de interoperación del detector de virus con Skype para Business Server.

En este artículo se incluyen recomendaciones que pueden ayudar a un administrador a determinar la causa del potencial de inestabilidad en un equipo que está ejecutando una versión compatible de Microsoft Windows cuando se usa con el software antivirus en un dominio de Active Directory entorno o en un entorno empresarial administrada.

Se recomienda que aplicar temporalmente estos procedimientos para evaluar un sistema. Si el rendimiento del sistema o la estabilidad se ha mejorado por las recomendaciones que se realizan en este artículo, póngase en contacto con su proveedor de software antivirus para obtener instrucciones o para una versión actualizada del software antivirus.

Este artículo contiene información que muestra cómo ayudar a reducir la configuración de seguridad o cómo desactivar temporalmente las características de seguridad en un equipo. Puede realizar estos cambios para comprender la naturaleza de un problema específico. Antes de realizar estos cambios, le recomendamos que evalúe los riesgos asociados con la implementación de esta solución en su entorno concreto. Si decide implementar esta solución alternativa, tome las medidas adicionales oportunas para ayudar a proteger el equipo para los archivos que ya no se examina el software antivirus.

Para asegurarse de que el detector antivirus no interfiere con el funcionamiento de Skype para Business Server, debe excluir directorios y procesos específicos para cada Skype para un servidor Business Server o rol de servidor en el que ejecute un detector de virus. Es necesario excluir los siguientes procesos y directorios:

> [!NOTE]
> Las ubicaciones de archivos y carpetas enumeradas a continuación son las ubicaciones predeterminadas de Skype para Business Server. Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.

> [!IMPORTANT]
> Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.

- Skype para los procesos del servidor empresarial:

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

    > [!NOTE]
    > Tenga en cuenta que estas rutas de acceso son específicos de Skype para la versión de Business Server.

  - %programfiles%\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor

  - %programfiles%\Common Files\Skype Empresarial Server 2015

  - %programfiles%\Common Files\Skype Empresarial Online

  - %SystemDrive%\RtcReplicaRoot

  - Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.

  - Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para obtener información detallada acerca de los archivos de registro y datos para cada base de datos, incluidos los nombres de forma predeterminada, vea [datos de SQL Server y la ubicación del archivo de registro](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.

  - SQL Server datos y archivos de registro, los referentes a la base de datos front-end, Skype para almacén empresariales y almacén de RtcDatabase incluidos. Normalmente, se encuentran en %localdrive%\CSData.


