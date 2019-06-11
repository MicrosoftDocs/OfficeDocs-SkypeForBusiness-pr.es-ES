---
title: 'Lync Server 2013: configurar números de teléfono sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22441573c22a932c383c7821cce16d79b9767a7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Configurar números de teléfono sin asignar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Lync Server le permite configurar lo que sucede con las llamadas entrantes a números de teléfono que son válidos para su organización, pero que no están asignados a un usuario o teléfono. Para configurar la administración de estas llamadas, debe configurar una tabla de números sin asignar. Puede usar la tabla para enrutar las llamadas a una aplicación de anuncio o a un servidor de mensajería unificada de Exchange.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar, o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en ese momento. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

<div>


> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, debe tener ya uno o más anuncios definidos o un operador automático de mensajería unificada de Exchange. Para obtener detalles sobre la creación de anuncios, consulte <A href="lync-server-2013-create-an-announcement.md">crear un anuncio en Lync Server 2013</A>. Para ver si ha configurado la configuración de mensajería unificada de Exchange, ejecute el cmdlet <STRONG>Get-CsExUmContact</STRONG> . Para obtener más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear o modificar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Eliminar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

