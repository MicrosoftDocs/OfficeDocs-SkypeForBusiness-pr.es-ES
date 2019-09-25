---
title: Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
description: En este artículo se describe la administración remota de la configuración predeterminada usada por un dispositivo de salas de Microsoft Teams, incluida la aplicación de un tema personalizado.
ms.openlocfilehash: 7f895e90a585c350f2b746fcc88296f09007b64b
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142069"
---
# <a name="content-cameras"></a>Cámaras de contenido

Ahora puede usar una cámara de contenido con un sistema de salas de Microsoft Teams. Una cámara de contenido interactúa con un software de procesamiento de imágenes especial y una pizarra para permitir que un moderador dibuje en una pizarra analógica y comparta el contenido con los participantes remotos.

Vea el siguiente vídeo para obtener ejemplos de funcionalidad de cámara de contenido.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurar una cámara de contenido

> [!NOTE]
> Adherirse siempre al código de construcción de tu país o área, que puede definir una distancia mínima desde el piso o un requisito que garantice que el equipo se asegure a un balsa u otra estructura. Siga las instrucciones de montaje del hardware proporcionado con la cámara que ha seleccionado. Los kits de montaje de cámaras OEM incluyen una cámara, prolongadores USB 2,0 y un cable necesario.

El tamaño de la pizarra que se usa para compartir afecta a la colocación de la cámara. Las recomendaciones de tamaño del panel son:

- 3-6 m (0,9-1,8 m) de anchura: compatible
- 6 – 9 m (1,8-2,7 m) de ancho: recomendado
- 9 – 12 m (2,7 – 3,6 m) de anchura: compatibles
- Por encima de la 3,6 m (12 pies) de anchura, la cámara cubre 9 – 12 ft (2,7 – 3.6 m) y recorta el resto.

## <a name="camera-location"></a>Ubicación de la cámara

La colocación ideal de una cámara de contenido está centrada vertical y horizontalmente en la pizarra. Los códigos de construcción locales pueden tener restricciones de alto que requieren que la cámara se eleva más allá de la parte superior del panel blanco.

Puedes instalar la cámara hasta 6 en. (152 mm) más allá de la parte superior de la pizarra y se centra en la pizarra, tal y como se muestra. Asegúrate de que la imagen de la cámara incluya al menos un 6 en. (152 mm) borde horizontal en ambas caras. Puede usar la vista previa de la cámara en la aplicación salas de Microsoft Teams para determinar la colocación final de la cámara.

![Diagrama de colocación de cámara de contenido](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distancias de la cámara

Con los marcadores de pizarra típicos, la experiencia de usuario remota óptima es compartir trazos de lápiz en el intervalo de 1 a 2 mm por píxel en la imagen de la cámara de contenido y los mejores resultados usan 1,5 mm por píxel. Todas las cámaras compatibles proporcionan una resolución de 1920 x 1080 y otras pueden exceder esa resolución.

La distancia entre la cámara y la pizarra se combina con la resolución de la cámara y HFoV para determinar la distancia desde la pizarra. En la tabla siguiente se muestran ejemplos de distancias para varios tamaños de pizarra. Puede usar estos valores como puntos de partida para determinar la ubicación final de la cámara de contenido.

**Distancia de la cámara desde la pizarra**

| Cámara HFoV |3 m (0,91 m)     | 6 ft (1,8 m)    | 2,74 m (9 ft)        |12 m.  (3,65 m)         | Distancia máxima desde pizarra  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80 °         | 1,79 ft (0,54 m) | 3,58 ft (1,09 m)  | 5,36 ft (1,6 m)    |7,15 ft (2,17 m) |7,51 ft (2,28 m) |
| 90 °         | 1,5 ft (0,45 m) | 3,00 ft (0,91 m)   | 4,5 ft (1,37 m)    |6,0 ft (1,82 m)    |6,3 ft (1,92 m) |
| 100 °        | 1,26 ft (0,38 m)| 2,52 ft (0,77 m)   | 3,78 ft (1,15 m)   |5,03 ft (1,53 m)   |5,29 ft (1,61 m) |
| 110 °        | 1,05 ft (0,32 m)| 2,10 ft (0,64 m)   | 3,15 ft (0,96 m)   |4,2 ft (1,28 m)    |4,41 ft (1,31 m) |
| 120 °        | 0,87 ft (0,26 m)| 1,73 ft (0,52 m)   | 2,60 ft (0,79 m)   |3,46 ft (1,05 m)   |3,64 ft (1,10 m) |
|             |               |                  |                  |        |                    |                  |

La distancia entre la cámara de contenido y el muro en el que se monta la pizarra depende de la HFoV para ese modelo de cámara, que varía. Instala cámaras con un HFoV más grande (por ejemplo, 120 grados) cerca de la pared y cámaras con un HFoV más estrecho lejos de la pared. Comprueba el HFoV antes de empezar a instalar la cámara elegida.

Si hay pizarras de más de 12 m (3,65 m) o sin esquinas (como pizarras de pared completa), puedes colocar la cámara en cualquier lugar del medio. El software de mejora selecciona un área en el medio si no encuentra las esquinas de la pizarra.

> [!NOTE]
> Puede usar cinta de color oscuro u otros elementos para crear un área de cámara de contenido definida en un panel blanco de pared completa.
>
> Puede optar por montar la cámara en un trípode móvil en lugar de montarla de manera permanente. Coloca el trípode en el centro de la pizarra. Esta configuración puede ser temporal o utilizarse en caso de que haya pocas posibilidades de derribar el equipo. Si usa un montaje temporal, recuerde que la mejora del contenido se verá afectada si mueve la cámara después del uso compartido inicial y necesitará volver a compartirla para corregir el movimiento.
>
> No se admite un panel de escritura que no sea blanco.

## <a name="supported-cameras"></a>Cámaras compatibles

Para determinar si puede usar una cámara como cámara de contenido, consulte [versiones de firmware certificadas para periféricos de audio y vídeo USB](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

O bien, consulte los kits de cámaras de contenido admitidos en Microsoft Teams Devices en [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Configuración de la cámara

Una vez instalada la cámara en la sala, configúrelo en la consola de salas de Microsoft Teams de la sala:

1. ![](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)Seleccione **configuración de configuración,** inicie sesión como administrador y seleccione **configuración del dispositivo**.
2. En la sección **valores predeterminados de cámara** , seleccione la cámara de contenido y asegúrese de que esté seleccionada la opción **mejoras de contenido** .
3. Faculta Si la cámara se instaló al revés porque la cámara se montó desde el techo, active la opción **rotar la cámara de contenido 180 °** .
4. Seleccione **Guardar y salir**.

![Configuración de cámara de contenido](../media/content-camera.png)

También puede ajustar esta configuración de forma remota con un [archivo de configuración XML](xml-config-file.md).

## <a name="see-also"></a>Vea también

[Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md)

[Requisitos de salas de Microsoft Teams](requirements.md)

> [!NOTE]
> Algunos dispositivos de la sala Microsoft teams que tienen consolas basadas en Microsoft Surface Pro (como Logitech SmartDock y Crestron SR) aún no son compatibles con la cámara de contenido. La compatibilidad con estos dispositivos se agregará más adelante en CY2019. 
>
