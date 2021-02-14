---
title: Mover el servidor de administración central
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de migrar a Skype Empresarial Server 2019, debe mover el servidor de administración central al servidor front-end o grupo de servidores de Skype Empresarial Server 2019 para poder quitar el servidor heredado.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752472"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover el servidor de administración central heredado a Skype Empresarial Server 2019

Después de migrar a Skype Empresarial Server 2019 y antes de quitar el servidor heredado, debe mover el servidor de administración central al servidor front-end o grupo de servidores front-end de Skype Empresarial Server 2019. 
  
El servidor de administración central es un único sistema maestro/réplica múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación. La base de datos local recibe actualizaciones de réplicas por medio del agente replicador de réplicas de Skype Empresarial Server que se ejecuta como servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que se incluye en los archivos xds.mdf y xds.ldf. Un punto de control de servicio (SCP) de los Servicios de dominio de Active Directory hace referencia a la ubicación de la base de datos maestra. Todas las herramientas que usan el servidor de administración central para administrar y configurar Skype Empresarial Server usan el SCP para localizar el almacén de administración central.
  
Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original. Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea Quitar la SQL Server base de datos de un grupo [de servidores front-end.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
Use el cmdlet Windows PowerShell **Move-CsManagementServer** en el Shell de administración de Skype Empresarial Server para mover la base de datos de la base de datos SQL Server de instalación heredada a la base de datos de SQL Server de Skype Empresarial Server 2019 y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de Skype Empresarial Server 2019. 
  
Use los procedimientos descritos en esta sección para preparar los servidores front-end de Skype Empresarial Server 2019 antes de mover el servidor de administración central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar un grupo de servidores front-end Enterprise Edition

1. En el grupo de servidores front-end de Skype Empresarial Server 2019 Enterprise Edition en el que desea reubicar el servidor de administración central, inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** También debe tener permisos y derechos SQL Server usuario sysadmin de base de datos en la base de datos donde desea instalar el almacén de administración central. 
    
2. Abra el Shell de administración de Skype Empresarial Server.
    
3. Para crear el nuevo almacén de administración central en la base de datos de SQL Server de Skype Empresarial Server 2019, en el Shell de administración de Skype Empresarial Server, escriba:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme que se ha iniciado el estado del servicio **front-end** de Skype **Empresarial Server.**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar un servidor front-end Standard Edition

1. En el servidor front-end Standard Edition de Skype Empresarial Server 2019 donde desea reubicar el servidor de administración central, inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** 
    
2. Abra el Asistente para la implementación de Skype Empresarial Server.
    
3. En el Asistente para la implementación de Skype Empresarial Server, haga clic **en Preparar el primer servidor Standard Edition**.
    
4. En la **página Ejecutar comandos,** SQL Server Express se instala como el servidor de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  **Finalizar**.
    
    > [!NOTE]
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo. 
  
5. Para crear el nuevo almacén de administración central en el servidor front-end Standard Edition de Skype Empresarial Server 2019, en el Shell de administración de Skype Empresarial Server, escriba: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme que se ha iniciado el estado del servicio **front-end** de Skype **Empresarial Server.**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover el servidor de administración central instalado heredado a Skype Empresarial Server 2019

1. On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group. También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abra el Shell de administración de Skype Empresarial Server (ejecutar como administrador).
    
3. En el Shell de administración de Skype Empresarial Server, escriba: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` no se realiza correctamente, resuelva el problema evitando que el comando se complete antes de continuar. Si **Enable-CsTopology** no se realiza correctamente, se producirá un error en el movimiento y puede dejar la topología en un estado en el que no haya ningún almacén de administración central. 
  
4. En el servidor front-end o grupo de servidores front-end de Skype Empresarial Server 2019, en el Shell de administración de Skype Empresarial Server, escriba: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. El Shell de administración de Skype Empresarial Server muestra los servidores, los almacenes de archivos, los almacenes de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados. Escriba **S** para continuar o **N** para detener la migración. 
    
6. Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos. 
    
7. En el servidor de Skype Empresarial Server 2019, abra el Asistente para la implementación de Skype Empresarial Server. 
    
8. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**. 
    
9. En el servidor de instalación heredado, abra el Asistente para la implementación. 
    
10. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**. 
    
11. Reinicie el servidor de Skype Empresarial Server 2019. Esto es necesario debido a un cambio de pertenencia a grupos para tener acceso a la base de datos del servidor de administración central.
    
12. Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el Shell de administración de Skype Empresarial Server, escriba: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para quitar archivos heredados del almacén de administración central después de un movimiento

1. En el servidor de instalación heredado, inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abrir shell de administración de Skype Empresarial Server
    
    > [!CAUTION]
    > No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y esté estable. Si quita los archivos antes de completar la replicación, interrumpirá el proceso de replicación y dejará el servidor de administración central recién movido en un estado desconocido. Utilice el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de la replicación. 
  
3. Para quitar los archivos de base de datos del almacén de administración central del servidor de administración central de instalación heredado, escriba:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por ejemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Donde se encuentra el servidor back-end de instalación heredado en una implementación Enterprise Edition o el  _\<FQDN of SQL Server\>_ FQDN del servidor Standard Edition. 
    

