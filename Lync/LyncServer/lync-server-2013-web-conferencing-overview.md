---
title: Introducción a las conferencias web de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b85bc97f5737f980c83c992a6a21eaeaca4e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Información general sobre las conferencias web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Con las conferencias web, los usuarios pueden compartir documentos y colaborar en ellos, como presentaciones de PowerPoint, durante las conferencias. Además, los usuarios pueden compartir todos los equipos de escritorio o parte de ellos en tiempo real, de modo que parezca que las personas de la Conferencia se han recopilado alrededor de la misma tabla de la reunión.

<div>

## <a name="whiteboard-and-annotations"></a>Pizarra y anotaciones

Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.

</div>

<div>

## <a name="polling"></a>Sondeo

La característica de sondeo mejora la colaboración porque permite a los moderadores averiguar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Uso compartido de aplicaciones y escritorio compartido

Durante una conferencia, puede compartir todo el escritorio, una aplicación individual o monitores individuales en un entorno de varios monitores. Aparte de ver el contenido, otros participantes de la Conferencia también pueden solicitar el control de su pantalla y, con el permiso, interactuar con el contenido (incluido el desplazamiento y la edición).

<div>


> [!NOTE]  
> Los participantes que ven la Conferencia también pueden tomar el control y empezar a compartir contenido durante la reunión.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Uso compartido de PowerPoint

En Lync 2010, las presentaciones de PowerPoint se visualizaban de una de dos maneras. Para los usuarios que ejecutan Lync 2010, las presentaciones de PowerPoint se mostraban con el formato de PowerPoint 97-2003 y se visualizaban con una copia incrustada de PowerPoint Viewer. Para los usuarios que ejecutan Lync Web App, las presentaciones de PowerPoint se convirtieron en archivos HTML dinámicos y, a continuación, se veían con una combinación de esos archivos DHTML personalizados y Silverlight. Aunque generalmente es eficaz, este enfoque tiene algunas limitaciones:

  - El visor de PowerPoint incrustado (que proporcionó la experiencia de visualización óptima) solo está disponible en la plataforma de Windows.

  - Muchos dispositivos móviles (incluidos algunos de los teléfonos móviles más populares) no admiten Silverlight.

  - El enfoque de PowerPoint Viewer y DHTML/Silverlight no admite todas las características (como las transiciones de diapositiva y el vídeo incrustado) que se encuentran en las versiones más recientes de PowerPoint.

Para ayudar a solucionar estos problemas y mejorar la experiencia general de los usuarios que presentan o ven presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps y el servidor de Office Web Apps para controlar presentaciones de PowerPoint. Entre otras ventajas, este nuevo enfoque permite:

  - Pantallas de mayor resolución y mejor compatibilidad con las características de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.

  - Dispositivos móviles adicionales para acceder a estas presentaciones. Esto se debe a que Lync Server 2013 usa DHTML y JavaScript estándar para difundir presentaciones de PowerPoint en lugar de DHTML y Silverlight personalizados.

  - Los usuarios con los privilegios adecuados para desplazarse por una presentación de PowerPoint independientemente de la presentación. Por ejemplo, si bien Ken Myer está presentando su presentación con diapositivas, Pilar Ackerman puede ver la diapositiva que quiere y sin afectar a la presentación de Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

