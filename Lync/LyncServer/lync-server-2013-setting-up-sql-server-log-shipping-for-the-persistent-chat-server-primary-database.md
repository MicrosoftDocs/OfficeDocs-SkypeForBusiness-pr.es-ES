---
title: 'Lync Server 2013: configuración del trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ff5f403329c430e18767d9b334982ecccc3898b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521807"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configurar el trasvase de registros de SQL Server en Lync Server 2013 para la base de datos principal del servidor de chat persistente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

Mediante SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que el Agente SQL Server se está ejecutando.

Mediante SQL Server Management Studio conectado a la instancia de base de datos principal de chat persistente, siga estos pasos:

1.  Asegúrese de que el Agente SQL Server se está ejecutando.

2.  Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.

3.  En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.

4.  Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.

5.  En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.

6.  En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad de registro de las transacciones.

7.  Si la carpeta de copia de seguridad se encuentra en el servidor principal, escriba la ruta de acceso local a la carpeta de copia de seguridad en el cuadro **si la carpeta de copia de seguridad se encuentra en el servidor principal, escriba una ruta de acceso local a la carpeta (ejemplo: c: \\ copia de seguridad)** . (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    <div>
    

    > [!IMPORTANT]  
    > Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta con la cuenta de sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.

    
    </div>

8.  Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.

9.  Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.

10. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.

11. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.

12. Haga clic en **conectar** y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.

13. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.

14. En la pestaña **inicializar base de datos secundaria** , elija la opción **sí, genere una copia de seguridad completa de la base de datos principal y restáurela en la base de datos secundaria (y cree la base de datos secundaria si no existe)**.

15. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados **, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.

16. Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.

17. En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.

18. En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.

19. Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.

20. Observe la programación de copia de seguridad incluido en el cuadro **Programación** en **Trabajo de restauración**. Para personalizar la programación de la instalación, haga clic en **programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.

21. En el cuadro de diálogo **Propiedades de base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.

</div>

<span> </span>

</div>

</div>

</div>

