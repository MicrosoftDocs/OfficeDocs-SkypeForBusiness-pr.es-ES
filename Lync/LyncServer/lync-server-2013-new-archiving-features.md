---
title: 'Lync Server 2013: Nuevas características de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nuevas características de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

El archivado en Lync Server 2013 puede archivar los siguientes tipos de contenido:

  - Mensajes instantáneos de punto a punto

  - Conferencias (reuniones) que son mensajes instantáneos de varios participantes

  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)

Además, el archivado en Lync Server 2013 ofrece nuevas características que mejoran la implementación y la eficacia de las operaciones. Estas nuevas características constan de:

  - **Collocation de archivo en los servidores frontales.**    Lync Server 2013 no tiene un rol de servidor de archivado independiente. El archivado es una característica opcional disponible en todos los servidores front-end de una implementación de Enterprise Edition, y en servidores Standard Edition, que se puede implementar en un grupo o sitio.

  - **Integración con Microsoft Exchange.**    Al implementar el archivado, puede integrar el almacenamiento de datos para archivar con el almacenamiento existente de Exchange 2013 para todos los usuarios alojados en Exchange 2013 y para que sus buzones se coloquen en la retención local, por lo que no es necesario implementar SQL Server independiente. bases de datos para archivar datos de Lync. Si no tiene una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync 2013 que no está alojado en Exchange 2013 y sus buzones se colocan en conservación local, puede implementar bases de datos de archivado independientes con SQL Server a Stor e datos archivados de Lync Communications. Puede usar las bases de datos de integración de Microsoft Exchange y de archivo de Lync Server 2013 si desea usar la integración de Microsoft Exchange para algunos, pero no todos los usuarios de su implementación. Para obtener más información sobre la conservación local, vea "conservación local" en [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Reflejo de la tienda SQL.**    Al implementar el archivado, puede habilitar la creación de reflejo de la base de datos de SQL Server para la base de datos de archivado.

  - **Archivo de pizarras y sondeos.**    El contenido de conferencia archivado ahora incluye pizarras y sondeos compartidos durante la reunión.

Los siguientes tipos de contenido no se archivan:

  - Transferencias de archivos de punto a punto

  - Audio o vídeo para conferencias y mensajes instantáneos de punto a punto

  - Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

<div>

## <a name="see-also"></a>Vea también


[Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

