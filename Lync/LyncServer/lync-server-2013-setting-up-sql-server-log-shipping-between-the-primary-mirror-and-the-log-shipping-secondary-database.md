---
title: 'Lync Server 2013: Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Siga estos pasos para que el trasvase de registros continúe si la base de datos de chat principal persistente se conmuta por error a su base de datos reflejada.

1.  Failover manual de la base de datos principal de chat persistente en el reflejo. Esto se realiza mediante el shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover** . Para obtener más información, consulte "uso de los cmdlets del shell de administración de Lync Server" en [implementar el reflejo SQL para back-end servidor de alta disponibilidad en Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  Con SQL Server Management Studio, conéctese a la instancia principal de reflejo del servidor de chat persistente.

3.  Asegúrese de que el Agente SQL Server se esté ejecutando.

4.  Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.

5.  En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.

6.  Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.

7.  En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.

8.  En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.

9.  Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    <div>
    

    > [!IMPORTANT]  
    > Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.

    
    </div>

10. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.

11. Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server, según sea necesario.
    
    <div>
    

    > [!IMPORTANT]  
    > Use la misma configuración que usa para la base de datos principal.

    
    </div>

12. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.

13. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.

14. Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.

15. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.

16. En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.

17. En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.

18. Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.

19. En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.

20. Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea:-- \* \* \* \* \* \* end: script \* \* \* \* \* \*que se ejecutará en Primary:.
    
    <div>
    

    > [!IMPORTANT]  
    > La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.

    
    </div>

21. Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). 

22. Failback manual de la base de datos principal de chat persistente al principal. Esto se realiza mediante el shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover** . Para obtener más información, consulte "uso de los cmdlets del shell de administración de Lync Server" en [implementar el reflejo SQL para back-end servidor de alta disponibilidad en Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

<div>

## <a name="see-also"></a>Vea también


[Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

