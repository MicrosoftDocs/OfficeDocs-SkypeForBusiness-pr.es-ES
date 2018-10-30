---
title: Información general sobre la conferencia web en Lync Server 2013
TOCTitle: Información general sobre la conferencia web en Lync Server 2013
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48275079
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre la conferencia web en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Con la conferencia web, los usuarios pueden compartir y colaborar en documentos, como presentaciones PowerPoint, durante las conferencias. Además, los usuarios pueden compartir total o parcialmente el escritorio entre sí en tiempo real, haciendo que parezca como si las personas de la conferencia estuvieran juntas alrededor de la misma mesa en la reunión.

## Pizarra y anotaciones

Una pizarra es un lienzo en blanco que se puede usar para la colaboración con texto, lápiz, dibujos e imágenes. Las anotaciones hechas en las pizarras pueden verlas todos los participantes en la reunión. La característica de pizarra mejora la colaboración porque permite a los participantes de la reunión debatir, intercambiar ideas, tomar notas, etc.

## Sondeo

La característica de sondeo mejora la colaboración porque permite a los moderadores averiguar rápidamente las preferencias de los participantes. Durante las conversaciones y reuniones en línea, los moderadores pueden usar el sondeo para recabar respuestas anónimas de los participantes. Todos los moderadores pueden ver los resultados y elegir entre ocultarlos o mostrarlos a todos los asistentes.

## Uso compartido de aplicaciones y escritorios

Durante una conferencia puede compartir todo el escritorio, una aplicación individual o monitores individuales en un entorno con varios monitores. Aparte de solo ver el contenido, otros participantes en la conferencia también pueden solicitar el control de la pantalla y, con permiso, interactuar con el contenido (incluido el desplazamiento y la modificación).


> [!NOTE]
> Los participantes que están viendo la conferencia también pueden asumir el control y empezar a compartir contenido durante la reunión



## Uso compartido de PowerPoint

En Lync 2010, las presentaciones de PowerPoint se veían en una de dos maneras. Para los usuarios que ejecutaban Lync 2010, las presentaciones de PowerPoint aparecían con el formato PowerPoint 97-2003 y se veían usando una copia incrustada del visor de PowerPoint. Para los usuarios que ejecutaban Lync Web App, las presentaciones de PowerPoint se convertían a archivos HTML dinámicos y luego se veían usando una combinación de esos archivos DHTML personalizados y Silverlight. Aunque generalmente era eficaz, este enfoque tenía algunas limitaciones:

  - El visor de PowerPoint incrustado (que proporciona la experiencia de visualización óptima) solo está disponible en la plataforma de Windows.

  - Muchos dispositivos móviles (incluidos algunos de los teléfonos móviles más populares) no son compatibles con Silverlight.

  - El visor de PowerPoint y el enfoque DHTML/Silverlight no es compatible con todas las características (como las transiciones de diapositivas y el vídeo incrustado) que se encuentran en las versiones más recientes de PowerPoint.

Para ayudar a abordar estas cuestiones y mejorar la experiencia global de los usuarios al presentar o ver presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps y Servidor Office Web Apps para controlar las presentaciones de PowerPoint. Entre otras ventajas, este nuevo enfoque permite:

  - Pantallas de mayor resolución y mayor compatibilidad con las capacidades de PowerPoint, como animaciones, transiciones de diapositivas y vídeo incrustado.

  - Que más dispositivos móviles obtengan acceso a estas presentaciones. Eso es porque Lync Server 2013 usa DHTML estándar y JavaScript para difundir presentaciones de PowerPoint en vez de DHTML personalizado y Silverlight.

  - Que usuarios con los privilegios adecuados se desplacen a través de una presentación de PowerPoint independiente de la propia presentación. Por ejemplo, mientras que Ken Myer realiza su presentación, Pilar Ackerman puede ver cualquier diapositiva que quiera, sin que esto afecte a la presentación de Ken.

