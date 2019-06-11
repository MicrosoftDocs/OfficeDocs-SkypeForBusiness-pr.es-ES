---
title: 'Lync Server 2013: asociar un almacén de supervisión con un grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-22_

En Microsoft Lync Server 2013 los datos de supervisión solo se pueden recopilar en grupos front-end que se hayan asociado a un almacén de supervisión, una tarea que normalmente se lleva a cabo define un grupo de servidores front-end en el generador de topología. Para asociar un almacén de supervisión con un nuevo grupo de servidores front-end, asegúrese de seleccionar la opción **supervisión (registrar detalles de llamadas y registro de métricas de la calidad de la experiencia)** en la página **seleccionar características** del Asistente para definir un nuevo grupo front-end. Tenga en cuenta que, si selecciona esta opción, también debe especificar un almacén SQL para poder completar el asistente; sin embargo, este almacén no tiene que existir en el momento en que se ejecutó el asistente. Eso significa que puede primero asociar un grupo con una tienda de supervisión y, después, configurar y configurar ese almacén.

O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.

3.  En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.

4.  En el generador de topologías, expanda **Lync Server 2013**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en expandir **agrupaciones front-end de Enterprise Edition**.

5.  Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.

6.  En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store** (o bien haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar el reflejo, seleccione **Esta instancia de SQL está en una relación de reflejo** y escriba el número de puerto del servidor de reflejo en el cuadro **Número de puerto de reflejo**.

7.  En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.

Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar su nueva topología, siga los pasos que se indican en el generador de topología:

1.  Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.

2.  En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.

3.  En la página **Asistente para publicación completado**, haga clic en **Finalizar**.

Después de publicar la topología, instale la base de datos de supervisión en el equipo que hospedará el almacén de supervisión. La base de datos de supervisión se puede instalar mediante el shell de administración de Lync Server y Windows PowerShell. Para instalar la base de datos de forma local (es decir, para instalar la base de datos en el mismo equipo en el que se ejecuta el shell de administración de Lync Server), inicie el shell de administración en el equipo adecuado, escriba el siguiente comando y presione ENTRAR:

    Install-CsDatabase -LocalDatabases

Al ejecutar el comando anterior, install-CsDatabase leerá la topología actual de Lync Server, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de esas bases de datos.

Para instalar la base de datos en un equipo remoto (es decir, en un equipo que no sea el equipo en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros indican al cmdlet install-CsDatabase para que recupere la topología de Lync Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn necesita usar un valor que represente el nombre de dominio completo del equipo donde se vayan a instalar las bases de datos.

Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Lync Server en el equipo que hospedará el almacén de supervisión. Para ello, inicie sesión en el equipo pertinente y ejecute el procedimiento siguiente:

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.

3.  En la página **implementar** , en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar de nuevo**.

4.  En el Asistente para la configuración de componentes del servidor de Lync, en la página **Configurar componentes de Lync Server** , haga clic en **siguiente**.

5.  En la página **especificar la ruta de acceso a los MSI** , escriba la ruta de acceso al archivo Ocscore. msi (un archivo incluido con los medios de instalación de Lync Server) y, a continuación, haga clic en **siguiente**.

6.  En la página **Ejecutar comandos**, haga clic en **Finalizar**.

Para asegurarse de que todos los servicios de Lync Server requeridos se hayan iniciado, haga clic en **Ejecutar** en el título **4: iniciar servicios** de la página **implementar**

</div>

<span> </span>

</div>

</div>

</div>

