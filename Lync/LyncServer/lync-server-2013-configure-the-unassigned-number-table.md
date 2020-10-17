---
title: 'Lync Server 2013: configurar la tabla de números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c73027511ec8798010f1d22fb9bd19eeab27a7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520257"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configurar la tabla de números sin asignar en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En Lync Server 2013, puede especificar lo que ocurre con las llamadas entrantes a números de teléfono que son válidos para su organización, pero que no están asignados a un usuario o teléfono. El autor de la llamada puede oír un mensaje o ser enrutado a otro destino, o bien ambas opciones.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

<div>


> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, el sistema debe tener anuncios definidos o un operador automático de mensajería unificada (MU) de Exchange configurado.



</div>

<div>


> [!TIP]  
> Cuando alguien llama a un número sin asignar, Lync Server busca la tabla de números sin asignar de arriba abajo y usa el primer intervalo que coincide. Por tanto, si quiere que una determinada acción se realice como último recurso, deberá especificarla para el último intervalo en la tabla.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un intervalo numérico sin asignar en Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [crear un anuncio en Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

