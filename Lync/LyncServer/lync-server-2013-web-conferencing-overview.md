---
title: Lync Server 2013 información general sobre conferencias web
description: 'Lync Server 2013: Introducción a las conferencias web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efeb9f12321cc28ea87f8672bbcf62aa49c6c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573586"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Información general sobre conferencias web en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Con la conferencia web, los usuarios pueden compartir y colaborar en documentos, como presentaciones PowerPoint, durante las conferencias. Además, los usuarios pueden compartir total o parcialmente el escritorio entre sí en tiempo real, haciendo que parezca como si las personas de la conferencia estuvieran juntas alrededor de la misma mesa en la reunión.

<div>

## <a name="whiteboard-and-annotations"></a>Pizarra y anotaciones

Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.

</div>

<div>

## <a name="polling"></a>Sondeo

La característica de sondeo mejora la colaboración porque permite a los moderadores averiguar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Uso compartido de aplicaciones y escritorios

Durante una conferencia, puede compartir todo el escritorio, una aplicación individual o monitores individuales en un entorno de varios monitores. Aparte de solo ver el contenido, otros participantes en la conferencia también pueden solicitar el control de la pantalla y, con permiso, interactuar con el contenido (incluido el desplazamiento y la modificación).

<div>


> [!NOTE]  
> Los participantes que están viendo la conferencia también pueden asumir el control y empezar a compartir contenido durante la reunión



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Uso compartido de PowerPoint

En Lync 2010 presentaciones de PowerPoint se visualizaron de una de dos maneras. Para los usuarios que ejecutan Lync 2010, las presentaciones de PowerPoint se mostraban con el formato de PowerPoint 97-2003 y se visualizaban con una copia incrustada de PowerPoint Viewer. Para los usuarios que ejecutan Lync Web App, las presentaciones de PowerPoint se han convertido en archivos HTML dinámicos y, a continuación, se han visto usando una combinación de los archivos DHTML personalizados y Silverlight. Aunque generalmente era eficaz, este enfoque tenía algunas limitaciones:

  - El visor de PowerPoint incrustado (que proporcionaba la experiencia de visualización óptima) solo está disponible en la plataforma de Windows.

  - Muchos dispositivos móviles (incluidos algunos de los teléfonos móviles más populares) no admiten Silverlight.

  - El enfoque DHTML/Silverlight y el visor de PowerPoint no admiten todas las características (por ejemplo, las transiciones de diapositivas y el vídeo incrustado) que se encuentran en las versiones más recientes de PowerPoint.

Para ayudar a solucionar estos problemas y mejorar la experiencia general de los usuarios que presentan o ven presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar las presentaciones de PowerPoint. Entre otras ventajas, este nuevo enfoque permite:

  - Pantallas de mayor resolución y mayor compatibilidad con las capacidades de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.

  - Que más dispositivos móviles obtengan acceso a estas presentaciones. Esto se debe a que Lync Server 2013 usa DHTML y JavaScript estándar para difundir presentaciones de PowerPoint en lugar de DHTML y Silverlight personalizados.

  - Que usuarios con los privilegios adecuados se desplacen a través de una presentación de PowerPoint independiente de la propia presentación. Por ejemplo, mientras que Ken Myer realiza su presentación, Pilar Ackerman puede ver cualquier diapositiva que quiera, sin que esto afecte a la presentación de Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

