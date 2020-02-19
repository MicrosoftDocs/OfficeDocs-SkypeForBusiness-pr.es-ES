---
title: 'Lync Server 2013: información general sobre la aplicación de anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264fbf5faf3fbce830a8d55cd7626d1ff67c2d58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Información general sobre la aplicación de anuncio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

Cuando implemente la aplicación de anuncio, deberá configurar una tabla de números sin asignar que determine la acción que se realizará cuando alguien Marque un número sin asignar. La tabla de números sin asignar contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio administra cada intervalo. Cuando un autor de llamada marca un número de teléfono que es válido para su organización pero que no está asignado a nadie, Lync Server busca el número en la tabla de enrutamiento de números sin asignar, identifica el intervalo en el que se encuentra el número y enruta la llamada al anuncio. aplicación especificada para ese intervalo. La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si lo ha configurado para ello) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, por ejemplo, a un operador. Puede usar los cmdlets del shell de administración de Lync Server para configurar varios mensajes de audio o para transferir destinos.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

En Lync Server 2013, la aplicación de anuncio se instala automáticamente con la aplicación grupo de respuesta. Las aplicaciones de anuncios y grupos de respuesta son componentes estándar de una implementación de Enterprise Voice: al implementar la telefonía IP empresarial, ambas aplicaciones se implementan automáticamente.

</div>

<span> </span>

</div>

</div>

</div>

