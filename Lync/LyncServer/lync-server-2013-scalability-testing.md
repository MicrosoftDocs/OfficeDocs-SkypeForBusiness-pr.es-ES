---
title: Pruebas de escalabilidad de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Pruebas de escalabilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 proporciona la infraestructura de servidor para todas las comunicaciones en tiempo real de Lync Server, incluidas la mensajería instantánea (mi) y la presencia, la Conferencia y la telefonía IP empresarial. Esto incluye todas las características que usan los recursos de hardware de un grupo de servidores de Lync Server 2013 y, por lo tanto, afectan al rendimiento y la escala. No todas las organizaciones usan todas las características del mismo modo.

Por ejemplo, algunas organizaciones pueden usar vídeo en las conferencias con mucha frecuencia mientras que otras apenas lo usan o no lo usan en absoluto. Algunas organizaciones prefieren compartir diapositivas de PowerPoint a realizar un uso compartido de las aplicaciones, mientras que otras prefieren lo contrario. Las organizaciones que implementan la telefonía IP empresarial podrían o no usar la aplicación de grupo de respuesta en gran medida. La mayoría de las organizaciones implementan servidores de supervisión, pero no muchos de ellos implementan servidores de archivado. Además, no todas las organizaciones tienen la misma infraestructura (por ejemplo, las capacidades de hardware y red, o el número y el tamaño de los grupos implementados). La diversidad de características e infraestructuras supone un desafío para las pruebas de escalabilidad, ya que no se pueden simular todas las combinaciones posibles de características e infraestructuras.

Para determinar la compatibilidad de escalabilidad para Lync Server, se realizan pruebas mediante el uso de todas las características de Lync Server a la vez, basadas en un modelo de uso medio (modelo de usuario). Para determinar un modelo de usuario adecuado para las cargas de trabajo de Lync Server, analizamos muchos puntos de datos, incluidos los estudios de clientes, los comentarios del programa para la mejora de la experiencia del usuario de Microsoft, los datos de uso de Lync Server del Departamento de TI interno de Microsoft. y los datos extraídos de nuestro servicio Live Meeting. En muchos casos, el modelo de usuario incluye una desviación hacia las cargas más pesadas para proporcionar un margen cómodo de uso a la organización.

En nuestras pruebas de escalabilidad, configuramos los grupos de servidores de Lync Server 2013 de acuerdo con las especificaciones de hardware y software recomendadas, incluidos los componentes de la infraestructura, como los servicios de dominio de Active Directory, los equilibradores de carga de hardware y los firewalls. Los entornos de Lync Server se configuran de la forma más parecida posible a los entornos típicos del mundo real. A continuación, usamos la herramienta stress and performance de Lync Server 2013 para simular las cargas de Lync Server 2013 (según nuestro modelo de usuario). .

Las pruebas de escalabilidad se repiten varias veces (incluidas varias ejecuciones de pruebas de tres semanas). Los resultados de todas las pruebas se usan para mejorar el ajuste del rendimiento y comprobar la compatibilidad de las cifras de escalabilidad del modelo de usuario.

</div>

<span> </span>

</div>

</div>

</div>

