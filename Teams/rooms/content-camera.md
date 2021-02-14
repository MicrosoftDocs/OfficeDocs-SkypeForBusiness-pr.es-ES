---
title: 'Aprenda a configurar cámaras de contenido: Microsoft Teams'
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Use una cámara de contenido en una sala de Microsoft Teams, que interactúa con software de procesamiento de imágenes para permitir a los presentadores dibujar en una pizarra analógica.
ms.openlocfilehash: ced0a65c0c1fab25bd1b244aea7301d654c44a9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508317"
---
# <a name="content-cameras"></a>Cámaras de contenido

Ahora puede usar una cámara de contenido con un sistema de sala de Microsoft Teams. Una cámara de contenido interactúa con un software especial de procesamiento de imágenes y una pizarra para permitir que un moderador dibuje en una pizarra analógica y comparta el contenido con participantes remotos.

Vea el siguiente vídeo para ver ejemplos de funcionalidad de cámara de contenido.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurar una cámara de contenido

> [!NOTE]
> Siga siempre el código de construcción de su país o área, lo que puede definir una distancia mínima desde el piso o un requisito de asegurar el equipo montado en techo a una parte posterior u otra estructura. Sigue las instrucciones de montaje para el hardware que se proporciona con la cámara que has seleccionado. Los kits de montaje de cámara OEM incluyen una cámara, extenderes USB 2.0 y cableado obligatorio.

El tamaño de la pizarra que se usa para compartir afecta a la colocación de la cámara. Las recomendaciones de tamaño de placa son:

- 3-6 pies de ancho (0,9–1,8 m) de ancho: compatible
- 6-9 pies de ancho (1,8-2,7 m) de ancho: recomendado
- 9-12 pies de ancho (2,7–3,6 m) de ancho: compatible
- Por encima de 12 pies de ancho (3,6 m), la cámara cubre de 9 a 12 pies (2,7-3,6 m) y recorta el resto.

## <a name="camera-location"></a>Ubicación de la cámara

La colocación ideal de una cámara de contenido se centra vertical y horizontalmente en la pizarra. Los códigos de construcción locales pueden tener restricciones de altura que requieran que la cámara se elevado más arriba que la parte superior de la pizarra.

Puede instalar la cámara hasta 6". (152 mm) más arriba que la parte superior de la pizarra y centrado en la pizarra, como se muestra. Asegúrese de que la imagen de la cámara incluya al menos un 6". (152 mm) borde a ambos lados horizontalmente. Puede usar la vista previa de la cámara en la aplicación Salas de Microsoft Teams para determinar la ubicación final de la cámara.

![Diagrama de ubicación de cámara de contenido](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distancias de la cámara

Con los marcadores típicos de pizarra, la experiencia de usuario remoto óptima es compartir trazos de lápiz en el rango de 1 a 2 mm por píxel en la imagen de la cámara de contenido y los mejores resultados usan 1,5 mm por píxel. Todas las cámaras compatibles proporcionan una resolución de 1920 x 1080, y algunas pueden superar esa resolución.

La distancia de la cámara desde la pizarra se combina con la resolución de la cámara y el HFoV para determinar la distancia desde la pizarra. En la tabla siguiente se muestran ejemplos de distancias para varios tamaños de pizarra. Puede usar estos valores como puntos de partida para determinar la ubicación final de la cámara de contenido.

**Distancia de la cámara desde la pizarra**

| HFoV de la cámara |3 pies (0,91 m)     | 6 pies (1,8 m)    | 9 pies (2,74 m)        |12 pies.  (3,65 m)         | Distancia máxima desde Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1,79 pies (0,54 m) | 3,58 pies (1,09 m)  | 5,36 pies (1,6 m)    |7,15 pies (2,17 m) |7,51 pies (2,28 m) |
| 90°         | 1,5 pies (0,45 m) | 3,00 pies (0,91 m)   | 4,5 pies (1,37 m)    |6,0 pies (1,82 m)    |6,3 pies (1,92 m) |
| 100°        | 1,26 pies (0,38 m)| 2,52 pies (0,77 m)   | 3,78 pies (1,15 m)   |5,03 pies (1,53 m)   |5,29 pies (1,61 m) |
| 110°        | 1,05 pies (0,32 m)| 2,10 pies (0,64 m)   | 3,15 pies (0,96 m)   |4,2 pies (1,28 m)    |4,41 pies (1,31 m) |
| 120°        | 0,87 pies (0,26 m)| 1,73 pies (0,52 m)   | 2,60 pies (0,79 m)   |3,46 pies (1,05 m)   |3,64 pies (1,10 m) |
|             |               |                  |                  |        |                    |                  |

La distancia entre la cámara de contenido y la pared en la que está instalada la pizarra depende del HFoV para ese modelo de cámara, que varía. Instale cámaras con un HFoV más grande (por ejemplo, 120 grados) más cerca de la pared y cámaras con un HFoV más estrecho, más lejos de la pared. Compruebe el HFoV antes de empezar a instalar la cámara elegida.

Si tiene pizarras de más de 12 pies (3,65 m) o sin esquinas (como pizarras de pared completa), puede colocar la cámara en cualquier lugar del medio. El software de mejoras selecciona un área en la parte central si no encuentra las esquinas de la pizarra interactiva.

> [!NOTE]
> Puede usar cinta de color oscuro u otros elementos para crear un área de cámara de contenido definida en una pizarra de pared completa.
>
> Puede elegir que la cámara se instale en un trípo móvil en lugar de en un montaje permanente. Coloque el trípodo centrado en la pizarra. Esta configuración puede ser temporal o usarse cuando hay pocas probabilidades de que toque el equipo. Si usas un montaje temporal, recuerda que las mejoras de contenido se verán afectadas si mueves la cámara después del recurso compartido inicial y deberás volver a compartir para corregir el movimiento.
>
> No se admite un tablero de escritura que no sea blanco.

## <a name="supported-cameras"></a>Cámaras compatibles

Para determinar si puede usar una cámara como cámara de contenido, consulte Versiones de firmware certificadas para [periféricos de audio y vídeo USB.](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)

O bien, consulte el catálogo de dispositivos de Microsoft Teams para obtener kits de cámara de contenido [admitidos en aka.ms/teamsdevices.](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>Configuración de la cámara

Una vez instalada la cámara en la sala, esta se configura en la consola de salas de Microsoft Teams de esa sala:

1. Seleccione **el icono** ![ Configuración, inicie sesión como administrador y seleccione Configuración del ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) **dispositivo.**
2. En la **sección Valores predeterminados de** la cámara, seleccione la cámara de contenido y asegúrese de que la opción Mejoras **de** contenido está seleccionada.
3. (Opcional) Si la cámara se instaló al revés porque la cámara estaba instalada desde el techo, compruebe la opción Girar el contenido de la cámara **180°.**
4. Seleccione **Guardar y salir.**

![Configuración de la cámara de contenido](../media/content-camera.png)

También puede ajustar esta configuración de forma remota mediante un [archivo de configuración XML.](xml-config-file.md)

## <a name="see-also"></a>Consulte también

[Administrar de forma remota la configuración de una consola de Salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md)

[Requisitos de la sala de Microsoft Teams](requirements.md)


