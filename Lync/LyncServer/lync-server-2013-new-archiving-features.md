---
title: 'Lync Server 2013: nuevas características de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a8969924acdf8268f059ae3b3660b70ca1dca7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nuevas características de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

El archivado en Lync Server 2013 puede archivar los siguientes tipos de contenido:

  - Mensajes instantáneos de punto a punto.

  - Conferencias (reuniones) que incluyen mensajes instantáneos de varios participantes.

  - Contenido de conferencias, incluido el contenido que se ha cargado (por ejemplo, documentos) y el contenido relacionado con los eventos (por ejemplo, usuarios que se unen o abandonan la conferencia, la carga de recursos compartidos y los cambios de visibilidad).

Además, el archivado en Lync Server 2013 proporciona nuevas características que mejoran la eficacia de la implementación y las operaciones. Estas nuevas características son:

  - **Combinación de archivado en los servidores front-end.**    Lync Server 2013 no tiene un rol de servidor de archivado independiente. El archivado es una característica opcional disponible en todos los servidores front-end de una implementación Enterprise Edition y en servidores Standard Edition, que pueden implementarse configurados para un grupo o un sitio.

  - **Integración de Microsoft Exchange.**    Al implementar el archivado, puede integrar el almacenamiento de datos para archivado con el almacenamiento de Exchange 2013 existente para todos los usuarios hospedados en Exchange 2013 y cuyos buzones se colocan en conservación local, por lo que no es necesario implementar bases de datos de SQL Server independientes para archivar datos de Lync. Si no dispone de una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync 2013 que no esté hospedado en Exchange 2013 con sus buzones en conservación local, puede implementar bases de datos de archivado independientes mediante SQL Server para Stor e datos archivados desde comunicaciones de Lync. Puede usar las bases de datos de archivado de Microsoft Exchange Integration y Lync Server 2013 si desea usar la integración de Microsoft Exchange para algunos, pero no para todos los usuarios de la implementación. Para obtener más información sobre la conservación local, vea "conservación local" en [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Creación de reflejo del almacén de SQL.**    Al implementar el archivado, puede habilitar la creación de reflejo de la base de datos de SQL Server para la base de datos de archivado.

  - **Archivado de pizarras y sondeos.**    El contenido de conferencia archivado ahora incluye pizarras y sondeos compartidos durante la reunión.

No se archivan los tipos de contenido siguientes:

  - Transferencias de archivos de punto a punto

  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto

  - Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

<div>

## <a name="see-also"></a>Consulta también


[Planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

