---
title: Mover el servidor de Administración Central
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Skype para Business Server 2019, debe mover el servidor de Administración Central para la Skype para profesionales de 2019 Front-End Server o grupo de servidores, para poder quitar el servidor heredado.
ms.openlocfilehash: 6a358b11d7d319d5dafbb82f4391cdc3d0ae1562
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373446"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover el servidor de Administración Central heredado a Skype para Business Server 2019

Después de migrar a Skype para Business Server 2019 y poder quitar el servidor heredado, debe mover el servidor de Administración Central para la Skype para profesionales de 2019 Front-End Server o grupo de servidores. 
  
El servidor de Administración Central es un sistema de única réplica maestro o varios, donde se mantiene la copia de lectura y escritura de la base de datos por el servidor Front-End que contiene el servidor de Administración Central. Cada equipo en la topología, incluido el servidor Front-End que contiene el servidor de Administración Central, tiene una copia de solo lectura de los datos del almacén de Administración Central en la base de datos de SQL (denominado RTCLOCAL de forma predeterminada) instalado en el equipo durante el programa de instalación y implementación. La base de datos local recibe actualizaciones de réplica mediante el Skype para profesionales agente de Replicador de réplica de servidor que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de Administración Central y la réplica local es XDS, que se compone de los archivos xds.mdf y xds.ldf. Un punto de control de servicio (SCP) en servicios de dominio de Active Directory al que hace referencia la ubicación de la base de datos maestra. Todas las herramientas que use el servidor de Administración Central para administrar y configurar Skype para Business Server usa el SCP para encontrar el almacén de Administración Central.
  
Una vez que haya movido correctamente el servidor de Administración Central, debe quitar las bases de datos del servidor de Administración Central desde el servidor original de Front-End. Para obtener información acerca de cómo quitar las bases de datos del servidor de Administración Central, vea [quitar la base de datos de SQL Server para un grupo de servidores Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Use el cmdlet de Windows PowerShell **Move-CsManagementServer** en el Skype para Shell de administración de servidor empresarial para mover la base de datos de la base de datos de SQL Server install heredado para la Skype para la base de datos de Business Server 2019 SQL Server y, a continuación, actualice el SCP para que apunte a la Skype para la ubicación del servidor de Administración Central de Business Server 2019. 
  
Use los procedimientos de esta sección para preparar el Skype para servidores Front-End de Business Server 2019 antes de mover el servidor de Administración Central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar un grupo de servidores Front-End de Enterprise Edition

1. En Skype para el grupo de servidores Front-End de Business Server 2019 Enterprise Edition donde desea reubicar el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro de la **RTCUniversalServerAdmins **grupo. También debe tener permisos y derechos de usuario de sysadmin de base de datos de SQL Server en la base de datos donde desea instalar el almacén de Administración Central. 
    
2. Abra el Skype para Shell de administración de servidor empresarial.
    
3. Para crear el nuevo almacén de Administración Central en el Skype para base de datos de Business Server 2019 SQL Server, en el Skype para Shell de administración de servidor empresarial, escriba:
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme que el estado del servicio de **Skype para Business Server front-end** es **iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar una edición Standard servidor Front-End

1. En Skype para profesionales de 2019 Standard Edition Front-End Server donde desea reubicar el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro de la **RTCUniversalServerAdmins **grupo. 
    
2. Abra el Skype para el Asistente para la implementación de servidor de negocio.
    
3. Skype para el Asistente para la implementación de Business Server, haga clic en **Preparar el primer servidor Standard Edition**.
    
4. En la página **Ejecución de comandos** , SQL Server Express está instalado como el servidor de Administración Central. Se crean las reglas de firewall necesarias. Una vez completada la instalación de la base de datos y el software necesario como requisito previo, haga clic en **Finalizar**.
    
    > [!NOTE]
    > La instalación inicial puede tardar algún tiempo sin actualizaciones visible a la pantalla de resumen de resultados de comando. Esto es debido a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para supervisar el programa de instalación. 
  
5. Para crear el nuevo almacén de Administración Central en el Skype para profesionales 2019 servidor Standard Edition Server Front-End, en la Skype para Shell de administración de servidor empresarial, escriba: 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme que el estado del servicio de **Skype para Business Server front-end** es **iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover que el heredado instala el servidor de Administración Central en Skype para Business Server 2019

1. En Skype para servidor Business Server 2019 que será el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario de administrador de base de datos de SQL Server y los permisos. 
    
2. Abra Skype para Shell de administración de servidor empresarial.
    
3. En Skype para Shell de administración de servidor empresarial, escriba: 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` no es correcta, resolver el problema que impide que el comando completar antes de continuar. Si **Enable-CsTopology** no se realiza correctamente, el movimiento se producirá un error y puede dejar la topología en un estado donde no hay ningún almacén de Administración Central. 
  
4. En el Skype para grupo de negocio 2019 Front-End Server o Front-End, de la Skype para Shell de administración de servidor empresarial, escriba: 
    
   ```
   Move-CsManagementServer
   ```

5. Skype para Shell de administración de servidor empresarial muestra los servidores, almacenes de archivos, los almacenes de base de datos y los puntos de conexión de servicio de estado actual y el estado propuesto. Lea detenidamente la información y confirmar que esta es la prevista origen y destino. Escriba **Y** para continuar, o **N** para detener el movimiento. 
    
6. Revise las advertencias o errores generados por el comando **Move-CsManagementServer** y resolverlos. 
    
7. En Skype para Business Server 2019 server, abra el Skype para el Asistente para la implementación de servidor de negocio. 
    
8. En Skype para el Asistente para la implementación de Business Server, haga clic en **instalar o actualización de Skype para el sistema de servidor empresarial**, haga clic en **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **siguiente**, revise el resumen y, a continuación, haga clic en Finalizar ** **. 
    
9. En el heredado instalar el servidor, abra el Asistente para la implementación. 
    
10. En Skype para el Asistente para la implementación de Business Server, haga clic en **instalar o actualización de Skype para el sistema de servidor empresarial**, haga clic en **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **siguiente**, revise el resumen y, a continuación, haga clic en Finalizar ** **. 
    
11. Reinicie el Skype para server Business Server 2019. Esto es necesario debido a un cambio de pertenencia a grupo para tener acceso a la base de datos del servidor de Administración Central.
    
12. Para confirmar que la replicación con la nueva Administración Central se está produciendo almacén, en la Skype para Shell de administración de servidor empresarial, escriba: 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La replicación puede tardar algún tiempo en actualizar todas las réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para quitar archivos de almacén de Administración Central de instalación heredados después de un movimiento

1. En el heredado instalar el servidor, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario de administrador de base de datos de SQL Server y los permisos. 
    
2. Abra Skype para Shell de administración de servidor empresarial
    
    > [!CAUTION]
    > No continúe con la eliminación de los archivos de base de datos anterior hasta que la replicación está completa y es estable. Si quita los archivos antes de completar la replicación, se interrumpen el proceso de replicación y dejar el servidor de Administración Central que se movió recientemente en un estado desconocido. Use el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de replicación. 
  
3. Para quitar los archivos de base de datos del almacén de Administración Central de la instalación heredada servidor de Administración Central, escriba:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por ejemplo:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Donde la _ \<FQDN de SQL Server\> _ es puede ser el heredado instalar servidor Back-End en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition. 
    

