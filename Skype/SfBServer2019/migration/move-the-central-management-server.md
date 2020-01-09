---
title: Mover el servidor de administración central
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Skype empresarial Server 2019, tendrá que mover el servidor de administración central al servidor o grupo de servidores front-end de Skype empresarial 2019 antes de poder quitar el servidor heredado.
ms.openlocfilehash: b6a2dd08949b5b15370f27e1da936009048982f6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990935"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover el servidor de administración central heredado a Skype empresarial Server 2019

Después de migrar a Skype empresarial Server 2019, y antes de poder quitar el servidor heredado, debe mover el servidor de administración central al servidor o grupo de aplicaciones para el usuario de Skype empresarial Server 2019. 
  
El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos es retenida por el servidor front-end que contiene el servidor de administración central. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén central de administración en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y implementación. La base de datos local recibe actualizaciones de réplica por medio del agente duplicador de réplicas de Skype empresarial Server que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está compuesto de los archivos XDS. MDF y XDS. ldf. Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Skype empresarial Server usan el SCP para localizar el almacén de administración central.
  
Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original. Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [quitar la base de datos de SQL Server de un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el shell de administración de Skype empresarial Server para mover la base de datos de la instalación heredada de SQL Server a la base de datos de Skype empresarial Server 2019 SQL Server y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de Skype empresarial Server 2019. 
  
Use los procedimientos de esta sección para preparar los servidores front-end de Skype empresarial Server 2019 antes de mover el servidor de administración central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Preparar un grupo de servidores front-end Enterprise Edition

1. En el grupo de servidores front-end de Skype empresarial Server 2019 Enterprise Edition donde quiere reubicar el servidor de administración central, inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener permisos y derechos de usuario de la base de datos sysadmin de SQL Server en la base de datos donde desee instalar el almacén de administración central. 
    
2. Abra el shell de administración de Skype empresarial Server.
    
3. Para crear el nuevo almacén central de administración en la base de datos de Skype empresarial Server 2019 de SQL Server, en el shell de administración de Skype empresarial Server, escriba:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme que se **ha iniciado**el estado del servicio **front-end de Skype empresarial Server** .
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar un servidor front-end Standard Edition

1. En el servidor front-end Standard Edition de Skype empresarial Server 2019, donde quiere reubicar el servidor de administración central, inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . 
    
2. Abra el Asistente para la implementación de Skype empresarial Server.
    
3. En el Asistente para la implementación de Skype empresarial Server, haga clic en **preparar el primer servidor Standard Edition**.
    
4. En la página **comandos en ejecución** , SQL Server Express está instalado como servidor de administración central. Se crean las reglas de Firewall necesarias. Cuando haya finalizado la instalación de la base de datos y el software necesario, haga clic en **Finalizar**.
    
    > [!NOTE]
    > La instalación inicial puede llevar algún tiempo sin actualizaciones visibles en la pantalla Resumen de salida del comando. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el administrador de tareas para supervisar la configuración. 
  
5. Para crear el nuevo almacén central de administración en el servidor front-end de Skype empresarial Server 2019 Standard Edition, en el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme que se **ha iniciado**el estado del servicio **front-end de Skype empresarial Server** .
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover el servidor de administración central instalaciones heredadas a Skype empresarial Server 2019

1. En el servidor de Skype empresarial Server 2019 que será el servidor de administración central, inicie sesión en el equipo donde el shell de administración de Skype empresarial Server está instalado como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario y permisos de administrador de bases de datos de SQL Server. 
    
2. Abra el shell de administración de Skype empresarial Server (ejecutar como administrador).
    
3. En el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` no es satisfactorio, solucione el problema evitando que se complete el comando antes de continuar. Si **enable-CsTopology** no se realiza correctamente, el movimiento no se realizará y puede dejar la topología en un estado en el que no haya ningún almacén de administración central. 
  
4. En el servidor front-end de Skype empresarial Server 2019 o en el grupo front-end, en el shell de administración de Skype empresarial Server, escriba: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. El shell de administración de Skype empresarial Server muestra los servidores, los almacenes de archivos, las tiendas de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información detenidamente y confirme que este es el origen y el destino previstos. Escriba **Y** para continuar o **N** para detener el movimiento. 
    
6. Revise las advertencias o errores generados por el comando **Move-CsManagementServer** y resuélvalos. 
    
7. En el servidor de Skype empresarial Server 2019, abra el Asistente para la implementación de Skype empresarial Server. 
    
8. En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar los componentes de Skype**empresarial Server, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**. 
    
9. En el servidor de instalación heredado, abra el Asistente para la implementación. 
    
10. En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar los componentes de Skype**empresarial Server, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**. 
    
11. Reinicie el servidor de Skype empresarial Server 2019. Esto se debe a un cambio de pertenencia a grupos para tener acceso a la base de datos del servidor de administración central.
    
12. Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el shell de administración de Skype empresarial Server, escriba: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La replicación puede tardar algún tiempo en actualizar todas las réplicas actuales. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para quitar los archivos heredados de la tienda de administración central después de un movimiento

1. En el servidor de instalación heredado, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario y permisos de administrador de bases de datos de SQL Server. 
    
2. Abrir el shell de administración de Skype empresarial
    
    > [!CAUTION]
    > No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y sea estable. Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y dejará el servidor de administración central que acaba de mover en un estado desconocido. Use el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de replicación. 
  
3. Para quitar los archivos de base de datos de la tienda de administración central del servidor de administración central de instalación heredada, escriba:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por ejemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Donde el _ \<FQDN de SQL Server\> _ es el servidor back-end de instalación heredado en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition. 
    

