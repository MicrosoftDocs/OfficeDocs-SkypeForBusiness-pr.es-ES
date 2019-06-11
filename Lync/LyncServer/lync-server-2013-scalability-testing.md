---
title: Pruebas de escalabilidad de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Pruebas de escalabilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 proporciona la infraestructura de servidor para todas las comunicaciones en tiempo real de Lync Server, incluidas la mensajería instantánea (mi) y la presencia, Conferencia y telefonía IP empresarial. Esto incluye todas las características que usan los recursos de hardware de un grupo de 2013 de Lync Server y, por lo tanto, afectan al rendimiento y la escala. Todas las organizaciones no usan todas las características.

Por ejemplo, es posible que algunas organizaciones usen el vídeo en conferencias muy intensa, mientras que otras pueden tener poco o ningún uso de video. Algunas organizaciones prefieren el uso compartido de diapositivas de PowerPoint para compartir aplicaciones, mientras que otras prefieren lo opuesto. Las organizaciones que implementan la telefonía IP empresarial pueden o no usar en gran medida la aplicación de grupo de respuesta. La mayoría de las organizaciones implementan servidores de supervisión, pero no muchos de ellos implementan servidores de archivado. Además, las organizaciones no tienen las mismas infraestructuras, entre ellas, capacidades de hardware, capacidades de red y la cantidad de pools y el tamaño de los pools implementados. La diversidad de características e infraestructuras supone un reto para las pruebas de escalabilidad; no es posible simular todas las combinaciones posibles de las características y las infraestructuras.

Para determinar la compatibilidad de escalabilidad de Lync Server, realizamos pruebas con todas las características de Lync Server de forma simultánea, en función de un modelo de uso promedio (modelo de usuario). Para determinar un modelo de usuario adecuado para las cargas de trabajo de Lync Server, analizamos muchos puntos de datos, entre los que se incluyen encuestas de clientes, comentarios del programa para la mejora de la experiencia del usuario de Microsoft, datos de uso de Lync Server del Departamento de TI interno en Microsoft. y datos extraídos de nuestro servicio de Live Meeting. En muchos casos, el modelo de usuario tiene un sesgo hacia cargas más pesadas para proporcionar un margen cómodo para el uso dentro de una organización.

En nuestras pruebas de escalabilidad, configuramos los grupos de aplicaciones de Lync Server 2013 según las especificaciones de hardware y software recomendadas, incluidos los componentes de la infraestructura, como los servicios de dominio de Active Directory, los equilibradores de carga de hardware y los firewalls. La configuración de entornos de Lync Server es lo más parecida a la de los entornos reales típicos. A continuación, usamos la herramienta de estrés y rendimiento de Lync Server 2013 para simular las cargas de Lync Server 2013 (según nuestro modelo de usuario). .

Realizamos varias iteraciones de pruebas de escalabilidad (incluidas varias ejecuciones de prueba de tres semanas). Usamos los resultados de todas las pruebas para ayudar con el ajuste de rendimiento y para comprobar la compatibilidad con los números de escalabilidad en nuestro modelo de usuario.

</div>

<span> </span>

</div>

</div>

</div>

