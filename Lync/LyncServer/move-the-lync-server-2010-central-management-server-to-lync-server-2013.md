---
title: Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-25_

Después de migrar de Lync Server 2010 a Lync Server 2013, debe mover el servidor de administración central de Lync Server 2010 al servidor o grupo de servidores front-end de Lync Server 2013 para poder quitar el servidor de Lync Server 2010 heredado.

El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos es retenida por el servidor front-end que contiene el servidor de administración central. Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén central de administración en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y implementación. La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Lync Server que se ejecuta como un servicio en todos los equipos. El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está compuesto de los archivos XDS. MDF y XDS. ldf. Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory. Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para localizar el almacén de administración central.

Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original. Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [quitar la base de datos de SQL Server de un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).

Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el shell de administración de Lync Server para mover la base de datos de la base de datos de lync Server 2010 de SQL Server a la base de datos de sql server 2013 de Lync Server y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de lync Server 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Preparar servidores front-end de Lync Server 2013 antes de mover el servidor de administración central

Use los procedimientos de esta sección para preparar los servidores front-end de Lync Server 2013 antes de mover el servidor de administración central de Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Preparar un grupo de servidores front-end Enterprise Edition

1.  En el grupo de servidores front-end de Lync Server 2013 Enterprise Edition donde quiere reubicar el servidor de administración central: inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener permisos y derechos de usuario de la base de datos sysadmin de SQL Server en la base de datos donde desee instalar el almacén de administración central.

2.  Abra el shell de administración de Lync Server.

3.  Para crear el nuevo almacén central de administración en la base de datos de Lync Server 2013 de SQL Server, en el shell de administración de Lync Server, escriba:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Confirme que el estado del servicio **front-end de Lync Server** se ha **iniciado**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar un servidor front-end Standard Edition

1.  En el servidor front-end de Lync Server 2013 Standard Edition en el que desea reubicar el servidor de administración central: inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** .

2.  Abra el Asistente para la implementación de Lync Server.

3.  En el Asistente para la implementación de Lync Server, haga clic en **preparar el primer servidor Standard Edition**.

4.  En la página **comandos en ejecución** , SQL Server Express está instalado como servidor de administración central. Se crean las reglas de Firewall necesarias. Cuando haya finalizado la instalación de la base de datos y el software necesario, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > La instalación inicial puede llevar algún tiempo sin actualizaciones visibles en la pantalla Resumen de salida del comando. Esto se debe a la instalación de SQL Server Express. Si necesita supervisar la instalación de la base de datos, use el administrador de tareas para supervisar la configuración.

    
    </div>

5.  Para crear el nuevo almacén central de administración en el servidor front-end de Lync Server 2013 Standard Edition, en el shell de administración de Lync Server, escriba:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Confirme que el estado del servicio **front-end de Lync Server** se ha **iniciado**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Para mover el servidor de administración central de Lync Server 2010 a Lync Server 2013

1.  En el servidor de Lync Server 2013 que será el servidor de administración central: inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario y permisos de administrador de bases de datos de SQL Server.

2.  Abra el Shell de administración de Lync Server.

3.  En el shell de administración de Lync Server, escriba:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Si <CODE>Enable-CsTopology</CODE> no es satisfactorio, solucione el problema evitando que se complete el comando antes de continuar. Si <STRONG>enable-CsTopology</STRONG> no se realiza correctamente, el movimiento no se realizará y puede dejar la topología en un estado en el que no haya ningún almacén de administración central.

    
    </div>

4.  En el servidor front-end de Lync Server 2013 o en el grupo de servidores front-end, en el shell de administración de Lync Server, escriba:
    
        Move-CsManagementServer

5.  El shell de administración de Lync Server muestra los servidores, los almacenes de archivos, las tiendas de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto. Lea la información detenidamente y confirme que este es el origen y el destino previstos. Escriba **Y** para continuar o **N** para detener el movimiento.

6.  Revise las advertencias o errores generados por el comando **Move-CsManagementServer** y resuélvalos.

7.  En el servidor de Lync Server 2013, abra el Asistente para la implementación de Lync Server.

8.  En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server**, haga clic en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.

9.  En el servidor de Lync Server 2010, abra el Asistente para la implementación de Lync Server.

10. En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server**, haga clic en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.

11. Reinicie el servidor de Lync Server 2013. Esto se debe a un cambio de pertenencia a grupos para tener acceso a la base de datos del servidor de administración central.

12. Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el shell de administración de Lync Server, escriba:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > La replicación puede tardar algún tiempo en actualizar todas las réplicas actuales.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Para quitar los archivos del almacén central de administración de Lync Server 2010 después de un movimiento

1.  En el servidor de Lync Server 2010: inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** . También debe tener los derechos de usuario y permisos de administrador de bases de datos de SQL Server.

2.  Abrir el shell de administración de Lync Server
    
    <div>
    

    > [!WARNING]  
    > No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y sea estable. Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y dejará el servidor de administración central que acaba de mover en un estado desconocido. Use el cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> para confirmar el estado de replicación.

    
    </div>

3.  Para quitar los archivos de la base de datos del almacén central de administración del servidor de administración central de Lync Server 2010, escriba:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Por ejemplo:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Donde el \<FQDN de SQL Server\> es el servidor Back-End de Lync Server 2010 en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

