---
title: 'Lync Server 2013: asociar un almacén de supervisión a un grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfdff8863c0e629c99d0e64aca0b7f84dcb63a43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Asociar un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-22_

En Microsoft Lync Server 2013 los datos de supervisión solo pueden recopilarse en grupos de servidores front-end que se hayan asociado a un almacén de supervisión, una tarea que normalmente lleva a cabo define un grupo de servidores front-end en el generador de topologías. Para asociar un almacén de supervisión a un nuevo grupo de servidores front-end, asegúrese de seleccionar la opción supervisión de las **métricas registro detallado de llamadas y registro de la calidad de la experiencia** en la página **seleccionar características** del asistente definir nuevo grupo de servidores front-end. Tenga en cuenta que, si selecciona esta opción, también debe especificar un almacén de SQL para poder completar el asistente; sin embargo, este almacén no tiene que existir en el momento en que se ejecutó el asistente. Esto significa que puede asociar primero un grupo con un almacén de supervisión y, después, instalar y configurar dicho almacén.

O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **generador de topologías de Lync Server**.

2.  En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.

3.  En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.

4.  En el generador de topologías, expanda **Lync Server 2013**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en **grupos de servidores front-end Enterprise Edition**.

5.  Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.

6.  En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store**. (O bien, haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar el reflejo, seleccione **Esta instancia de SQL está en una relación de reflejo** y escriba el número de puerto del servidor de reflejo en el cuadro **Número de puerto de reflejo**.

7.  En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.

Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar la nueva topología, ejecute los pasos siguientes en el Generador de topologías:

1.  Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.

2.  En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.

3.  En la página **Asistente de publicación completado**, haga clic en **Finalizar**.

Después de publicar la topología, instale la base de datos de supervisión en el PC que hospedará el almacén de supervisión. La base de datos de supervisión se puede instalar mediante el shell de administración de Lync Server y Windows PowerShell. Para instalar la base de datos de forma local (es decir, para instalar la base de datos en el mismo equipo en el que se ejecuta el shell de administración de Lync Server), inicie el shell de administración en el equipo apropiado, escriba el siguiente comando y presione ENTRAR:

    Install-CsDatabase -LocalDatabases

Al ejecutar el comando anterior, install-CsDatabase leerá la topología actual de Lync Server, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de estas bases de datos.

Para instalar la base de datos en un PC remoto (es decir, en un PC que no sea el PC en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros indican al cmdlet install-CsDatabase que recupere la topología de Lync Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn debe usar un valor que represente el nombre de dominio completo del PC donde se vayan a instalar las bases de datos.

Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Lync Server en el equipo en el que se va a hospedar el almacén de supervisión. Para ello, inicie sesión en el PC pertinente y ejecute el procedimiento siguiente:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.

3.  En la página **Implementar**, en **Paso 2: configuración o supresión de componentes de Lync Server**, haga clic en **Ejecutar de nuevo**.

4.  En el Asistente de instalación de los componentes de Lync Server, en la página **Instalar componentes de Lync Server**, haga clic en **Siguiente**.

5.  En la página **especificar la ruta de acceso a** los archivos MSI, escriba la ruta de acceso al archivo Ocscore. msi (un archivo incluido en los medios de instalación de Lync Server) y, a continuación, haga clic en **siguiente**.

6.  En la página **Ejecución de comandos**, haga clic en **Finalizar**.

Para asegurarse de que se han iniciado todos los servicios necesarios de Lync Server, haga clic en **Ejecutar** en el encabezado **paso 4: iniciar servicios** en la página **implementar**

</div>

<span> </span>

</div>

</div>

</div>

