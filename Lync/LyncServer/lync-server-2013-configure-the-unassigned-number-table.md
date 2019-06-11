---
title: 'Lync Server 2013: Configurar la tabla de números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59b44b31eececd002434b74085be85eaec9cbec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configurar la tabla de números sin asignar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En Lync Server 2013, puede especificar lo que pasa a las llamadas entrantes a números de teléfono que son válidos para su organización, pero que no están asignados a un usuario o teléfono. Las personas que llaman pueden oír un mensaje o se pueden enrutar a otro destino, o ambas cosas.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

<div>


> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, el sistema ya debe tener anuncios definidos o un operador automático de mensajería unificada (UM) de Exchange configurado.



</div>

<div>


> [!TIP]  
> Cuando alguien llama a un número no asignado, Lync Server busca la tabla de números sin asignar de arriba abajo y usa el primer intervalo coincidente. Por consiguiente, si quiere que se lleve a cabo una acción determinada como último recurso, deberá especificarla para el último intervalo en la tabla.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Crear un anuncio en Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

