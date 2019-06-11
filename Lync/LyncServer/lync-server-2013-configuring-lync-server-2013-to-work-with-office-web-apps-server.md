---
title: Configuración de Lync Server 2013 para que funcione con Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configuración de Lync Server 2013 para que funcione con Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-22_

Antes de poder configurar Lync Server 2013 para usar Office Web Apps Server, debe implementar y configurar Office Web Apps Server. Consulte la guía de documentos sobre la **implementación de Office Web Apps Server y Office Web Apps** para obtener información detallada sobre cómo instalar y configurar un único servidor de Office Web Apps, o bien para obtener información sobre cómo instalar y configurar una granja de servidores de Office Web Apps para alta ofrecer.

Después de instalar Office Web Apps Server correctamente y de que su granja de servidores Web se haya configurado correctamente, debe configurar Lync Server para que se comunique con el nuevo servidor; Esto se realiza agregando la dirección URL de detección de Office Web Apps Server a su topología de Lync Server. Realice lo siguiente para agregar Office Web Apps Server a su topología:

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.

3.  En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.

4.  En el generador de topologías, expanda **Lync Server 2013**, expanda el nombre de su sitio, expanda **agrupaciones front end de Enterprise Edition**, haga clic con el botón secundario en el nombre de uno de sus grupos y, a continuación, haga clic en **Editar propiedades**.

5.  En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).

6.  En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
    Si Office Web Apps Server está instalado en local y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (es decir,** no se debe seleccionar el perímetro o la Internet).
    
    Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.

7.  Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo servidor de Office Web Apps** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. La dirección URL de detección de Office Web Apps aparecerá como una de las asociaciones de la agrupación.

Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.

Después de agregar la dirección URL de detección a la topología, debe publicar esta topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:

1.  Haga clic en **Acción** y, después, en **Publicar topología**.

2.  En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.

3.  En la página **Asistente para publicación completado**, haga clic en **Finalizar**.

4.  Cierre el Generador de topologías.

</div>

<span> </span>

</div>

</div>

</div>

