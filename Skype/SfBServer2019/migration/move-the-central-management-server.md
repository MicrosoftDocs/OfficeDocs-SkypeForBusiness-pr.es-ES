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
description: Después de migrar a Skype empresarial Server 2019, debe mover el servidor de administración central al servidor o grupo de servidores front-end de Skype empresarial Server 2019, antes de que pueda quitar el servidor heredado.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752472"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover el servidor de administración central heredado a Skype empresarial Server 2019

Después de migrar a Skype empresarial Server 2019, y antes de poder quitar el servidor heredado, debe mover el servidor de administración central al servidor o grupo de servidores front-end de Skype empresarial Server 2019. 
  
El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos está retenida por el servidor front-end que contiene el servidor de administración central. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la configuración y la implementación. La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Skype empresarial Server que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está formado por los archivos XDS. MDF y XDS. ldf. Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Skype empresarial Server usan el SCP para localizar el almacén de administración central.
  
Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original. Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el shell de administración de Skype empresarial Server para mover la base de datos de la instalación heredada de SQL Server a la base de datos de sql server 2019 de Skype empresarial Server y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de Skype empresarial Server 2019. 
  
Use los procedimientos de esta sección para preparar los servidores front-end de Skype empresarial Server 2019 antes de mover el servidor de administración central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar un grupo de servidores front-end Enterprise Edition

1. En el grupo de servidores front-end de Skype empresarial Server 2019 Enterprise Edition donde desea reubicar el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener derechos y permisos de usuario sysadmin de base de datos de SQL Server en la base de datos en la que desea instalar el almacén de administración central. 
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. Para crear el nuevo almacén de administración central en la base de datos de SQL Server de Skype empresarial Server 2019, en el shell de administración de Skype empresarial Server, escriba:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme que el estado del servicio **front-end de Skype empresarial Server** se **ha iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar un servidor front-end Standard Edition

1. En el servidor front-end de Skype empresarial Server 2019 Standard Edition donde desea reubicar el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . 
    
2. Abra el Asistente para la implementación de Skype empresarial Server.
    
3. En el Asistente para la implementación de Skype empresarial Server, haga clic en **preparar el primer servidor Standard Edition**.
    
4. En la página **ejecución de comandos** , SQL Server Express está instalado como servidor de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  **Finalizar **.
    
    > [!NOTE]
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo. 
  
5. Para crear el nuevo almacén de administración central en el servidor front-end de Skype empresarial Server 2019 Standard Edition, en el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme que el estado del servicio **front-end de Skype empresarial Server** se **ha iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover el servidor de administración central de instalaciones heredadas a Skype empresarial Server 2019

1. En el servidor de Skype empresarial Server 2019 que será el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abra el shell de administración de Skype empresarial Server (ejecutar como administrador).
    
3. En el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` no se realiza correctamente, solucione el problema para evitar que el comando se complete antes de continuar. Si **enable-CsTopology** no se realiza correctamente, se producirá un error en el movimiento y puede dejar la topología en un estado en el que no haya almacén de administración central. 
  
4. En el servidor front-end de Skype empresarial Server 2019 o en el grupo de servidores front-end, en el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. El shell de administración de Skype empresarial Server muestra los servidores, los almacenes de archivos, los almacenes de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados. Escriba **S** para continuar o **N** para detener la migración. 
    
6. Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos. 
    
7. En el servidor de Skype empresarial Server 2019, abra el Asistente para la implementación de Skype empresarial Server. 
    
8. En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**. 
    
9. En el servidor de instalación heredado, abra el Asistente para la implementación. 
    
10. En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**. 
    
11. Reinicie el servidor de Skype empresarial Server 2019. Esto es necesario debido a un cambio de pertenencia a grupo para obtener acceso a la base de datos del servidor de administración central.
    
12. Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el shell de administración de Skype empresarial Server, escriba: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para quitar los archivos de almacén de administración central de instalación heredados después de un movimiento

1. En el servidor de instalación heredado, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abrir Shell de administración de Skype empresarial Server
    
    > [!CAUTION]
    > No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y esté estable. Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y dejará el servidor de administración central recién movido en un estado desconocido. Utilice el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de la replicación. 
  
3. Para quitar los archivos de la base de datos de almacén de administración central del servidor de administración central de instalación heredada, escriba:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por ejemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Donde _\<FQDN of SQL Server\>_ es el servidor back-end de instalación heredado de una implementación de Enterprise Edition o el FQDN del servidor Standard Edition. 
    

