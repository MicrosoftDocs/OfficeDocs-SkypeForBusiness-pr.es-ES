---
title: 'Lync Server 2013: información general sobre la aplicación de anuncios'
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
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Información general de la aplicación de anuncios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

Al implementar la aplicación de anuncios, debe configurar una tabla de números sin asignar que determine la acción que se realizará cuando alguien Marque un número sin asignar. La tabla de números sin asignar contiene rangos de números de teléfono que son válidos para la organización y especifica qué aplicación de la presentación controla cada rango. Cuando la persona que llama marca un número de teléfono que es válido para su organización pero que no está asignado a nadie, Lync Server busca el número en la tabla de enrutamiento de números no asignados, identifica el intervalo en el que cae el número y enruta la llamada al anuncio. aplicación especificada para ese intervalo. La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si lo ha configurado para ello) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como a un operador. Puede usar los cmdlets del shell de administración de Lync Server para configurar varios mensajes de audio o para transferir destinos.

La forma en que configures la tabla de números no asignados depende de cómo deseas usarla. Si dispones de números específicos que ya no están en uso y deseas reproducir mensajes personalizados para cada uno de los números, puedes introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de servicio de asistencia al cliente, puedes introducir el número antiguo del servicio de asistencia al cliente y asignarlo a un anuncio que comunique el número nuevo. Si deseas reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puedes introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

En Lync Server 2013, la aplicación de anuncio se instala automáticamente con la aplicación de grupo de respuesta. Las aplicaciones de grupos de presentación y respuesta son componentes estándar de una implementación de telefonía IP empresarial: cuando se implementa la telefonía IP empresarial, estas dos aplicaciones se implementan automáticamente.

</div>

<span> </span>

</div>

</div>

</div>

