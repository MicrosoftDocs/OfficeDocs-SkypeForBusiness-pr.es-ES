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
ms.localizationpriority: medium
description: Después de migrar a Skype Empresarial Server 2019, debe mover el servidor de administración central al servidor front-end o grupo de servidores de Skype Empresarial Server 2019, antes de poder quitar el servidor heredado.
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618286"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover el servidor de administración central heredado a Skype Empresarial Server 2019

Después de migrar a Skype Empresarial Server 2019 y antes de poder quitar el servidor heredado, debe mover el servidor de administración central al servidor front-end o grupo de servidores de Skype Empresarial Server 2019. 
  
El servidor de administración central es un único sistema de réplica principal o múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación. La base de datos local recibe actualizaciones de réplicas mediante el agente de replicador Skype Empresarial Server que se ejecuta como servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está hecho de los archivos xds.mdf y xds.ldf. Se hace referencia a la ubicación de la base de datos maestra mediante un punto de control de servicio (SCP) en Servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Skype Empresarial Server el SCP para localizar el almacén de administración central.
  
Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original. Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el Shell de administración de Skype Empresarial Server para mover la base de datos de la base de datos SQL Server de instalación heredada a la base de datos SQL Server de Skype Empresarial Server 2019 y, a continuación, actualice el SCP para que apunte Skype Empresarial Server la ubicación del servidor de administración central de Skype Empresarial Server 2019. 
  
Use los procedimientos descritos en esta sección para preparar el Skype Empresarial Server front-end de 2019 antes de mover el servidor de administración central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar un grupo Enterprise Edition front-end

1. En el grupo front-end de Enterprise Edition de Skype Empresarial Server de Skype Empresarial Server donde desea reubicar el servidor de administración central, inicie sesión en el equipo donde se instala el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** También debe tener permisos y SQL Server de usuario sysadmin de base de datos en la base de datos en la que desea instalar el almacén de administración central. 
    
2. Abra el Shell Skype Empresarial Server administración.
    
3. Para crear el nuevo almacén de administración central en la base Skype Empresarial Server de datos de SQL Server 2019, en el Shell de administración Skype Empresarial Server, escriba:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme que el estado del servicio **Skype Empresarial Server front-end** es **Iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar un servidor Standard Edition front-end

1. En el servidor front-end de Skype Empresarial Server Standard Edition de Skype Empresarial Server donde desea reubicar el servidor de administración central, inicie sesión en el equipo donde se instala el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** 
    
2. Abra el Asistente Skype Empresarial Server implementación.
    
3. En el Asistente Skype Empresarial Server implementación, haga clic **en Preparar primero Standard Edition servidor**.
    
4. En la **página Ejecutar comandos,** SQL Server Express se instala como servidor de administración central. Se crean las reglas de firewall necesarias. Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  **Finalizar**.
    
    > [!NOTE]
    > Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo. 
  
5. Para crear el nuevo almacén de administración central en Skype Empresarial Server 2019 Standard Edition servidor front-end, en el Shell de administración Skype Empresarial Server, escriba: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme que el estado del servicio **Skype Empresarial Server front-end** es **Iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover el servidor de administración central heredado a Skype Empresarial Server 2019

1. En el servidor Skype Empresarial Server 2019 que será el servidor de administración central, inicie sesión en el equipo donde se instala el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abra Skype Empresarial Server Shell de administración (ejecutar como administrador).
    
3. En el Shell Skype Empresarial Server administración, escriba: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` no se realiza correctamente, resuelva el problema que impide que el comando se complete antes de continuar. Si **Enable-CsTopology** no se realiza correctamente, el movimiento producirá un error y puede dejar la topología en un estado en el que no hay ningún almacén de administración central. 
  
4. En el Skype Empresarial Server front-end de 2019 o en el grupo de servidores front-end, en el Shell Skype Empresarial Server administración, escriba: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype Empresarial Server El Shell de administración muestra los servidores, los almacenes de archivos, los almacenes de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados. Escriba **S** para continuar o **N** para detener la migración. 
    
6. Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos. 
    
7. En el Skype Empresarial Server 2019, abra el Asistente para Skype Empresarial Server implementación. 
    
8. En el Asistente Skype Empresarial Server implementación, haga clic en Instalar o actualizar el sistema Skype Empresarial Server , haga clic en Paso **2:** Configurar o quitar componentes de Skype Empresarial Server , haga clic en Siguiente **,** revise el resumen y, **a** continuación, haga clic en Finalizar **.** 
    
9. En el servidor de instalación heredado, abra el Asistente para implementación. 
    
10. En el Asistente Skype Empresarial Server implementación, haga clic en Instalar o actualizar el sistema Skype Empresarial Server , haga clic en Paso **2:** Configurar o quitar componentes de Skype Empresarial Server , haga clic en Siguiente **,** revise el resumen y, **a** continuación, haga clic en Finalizar **.** 
    
11. Reinicie el Skype Empresarial Server 2019. Esto es necesario debido a un cambio de pertenencia a grupos para tener acceso a la base de datos del servidor de administración central.
    
12. Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el Shell Skype Empresarial Server administración, escriba: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para quitar archivos del almacén de administración central de instalación heredados después de un movimiento

1. En el servidor de instalación heredado, inicie sesión en el equipo donde se instala el Shell de administración de Skype Empresarial Server como miembro del grupo **RTCUniversalServerAdmins.** También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server. 
    
2. Abrir Skype Empresarial Server Shell de administración
    
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

    Donde se encuentra el servidor back-end de instalación heredado en una implementación Enterprise Edition o el FQDN del _\<FQDN of SQL Server\>_ servidor Standard Edition servidor. 
    

