---
title: Requisitos de la sala de Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Este artículo resume los requisitos para auxiliar las Salas de Microsoft Teams.
ms.openlocfilehash: 2496fcb1af7d85a3d1c3ba755a2431aff40d5a70
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521606"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de la sala de Microsoft Teams

Microsoft Teams escala a diferentes tamaños de sala al usar una amplia variedad de periféricos de audio y vídeo certificados según el tamaño y el uso de la sala. Seleccionando el dispositivo y la consola principal adecuada, combinados con micrófonos, altavoces, cámaras y pantallas apropiadas para el espacio, puede implementar las salas de Microsoft Teams en espacios de cualquier tamaño, desde espacios muy pequeños para reuniones hasta espacios muy grandes para conferencias y salas de juntas.  El conjunto completo de todos los periféricos de audio y vídeo certificados disponibles que pueden ser utilizados para configurar su sala está disponible en la [Escaparate de dispositivos](https://products.office.com/microsoft-teams/across-devices).

Este artículo resume los requisitos de implementación y configuración de los dispositivos para auxiliar a las salas de Microsoft Teams.

Su implementación implica la creación de cuentas como se describe en [Implementar salas de Microsoft Teams](rooms-deploy.md) y la configuración de consolas de reunión como se describe en [Configurar una consola de salas de equipos Microsoft](console.md).

Asimismo, vea:

- [Licencias de complemento de Skype Empresarial](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opciones de licencias en función de su plan: Salas de Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Las salas de Microsoft Teams inician sesión en Microsoft Teams, Skype Empresarial Server 2019, Skype Empresarial Server 2015 o Skype Empresarial en línea, y puede unirse a reuniones hospedadas por cualquiera de estos servicios.
>
> Las plataformas anteriores como Lync Server 2013 no son compatibles con las Salas de Microsoft Teams. Las salas de Microsoft Teams no son compatibles con Office 365 operado por 21Vianet, ni con los entornos GCC-High o DoD.
>
> Si tiene un servidor de Exchange local, las salas de Microsoft Teams requieren el uso de Exchange Server 2013 SP1 o posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Una implementación de hardware incluye una selección de un sistema de sala de Microsoft Teams, combinada con periféricos de audio y vídeo certificados, y una solución de cableado para integrar estos dispositivos.  A continuación se describen todas las opciones.

**Sistemas de sala de Microsoft Teams compatibles**

Todos los dispositivos y paquetes actuales de la Sala de Microsoft Teams están disponibles en el [escaparate de productos de los sistemas de la Sala](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Consola|Procesador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/es-ES/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[HP Elite Slice para salas de reuniones G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 con audio preparado para Salas de Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Logitech Tap](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  ||||||

> [!NOTE]
> - Los procesadores M3 no son compatibles.
> - Necesita una unidad USB de 32 GB o superior configurada como medio de instalación de arranque Windows para Windows 10 Enterprise.

**Tabletas Surface Pro compatibles para sistemas de estilo de acoplamiento**

  |Tableta|Procesador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB o 8 GB |128 GB o más |
  |Surface Pro </br>(quinta gen.) |Core i5 |8 GB o 4 GB |128 GB o más |
  |Surface Pro 4 |Core i5 |8 GB o 4 GB |128 GB o más |

- Los dispositivos Surface Pro requieren una de las siguientes opciones de estación de acoplamiento para asegurar una tableta a la mesa de la sala de reuniones.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versiones de firmware certificadas para periféricos de vídeo y audio USB

Estos dispositivos se encuentran disponibles en el [escaparate del sistema de la sala ](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) y [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periféricos de la sala de Microsoft Teams|Versión de firmware certificada | La cámara admite el uso de cámara de contenido|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio: 1.0.172 <br/> Video: 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Cámara Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/es-ES/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/es-ES/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/es-ES/products/mixers/p300) + </br></br> [Shure MXA 910 con micrófono de techo Intellimix](https://www.shure.com/es-ES/products/microphones/mxa910) | 4.1|
|[Biamp Tesira Fore AVB VT4 audio fijo DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Micrófono de techo 2 Sennheiser TeamConnect](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink amplificador +</br> Micrófono de techo Sennheiser TCC2 + </br> Altavoz de techo Bose EdgeMax EM180](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
||||||

&Dagger; Los clientes pueden elegir la interfaz Dante o el conmutador de red recomendado por Biamp/Sennheiser para este paquete.

#### <a name="usb-extenders"></a>Extensor USB

- Los puertos USB de las bases de acoplamiento de las tabletas son compatibles con USB 3.0. Puede usar un extensor USB 2.x, pero esto le limita a las velocidades USB 2.x en el otro extremo. Los extensores no se recomiendan para los periféricos con USB 3.0.
- Un extensor debe cumplir con las especificaciones USB 2.0 o posteriores.
  - Las bases de acoplamiento son compatibles con un mínimo de dos fases de extensión de concentrador USB externo. Si conectas más de dos concentradores USB en serie, comprueba con el fabricante del acoplamiento si admiten la conexión en serie.
  - Conexión GbE cableada en la sala. Cable de Ethernet de longitud apropiada.
  - Hasta dos pantallas de 1080-p con conexiones HDMI. Cable HDMI de longitud adecuada.

> [!NOTE]
> Si se usa un televisor como pantalla, debe ser compatible con la característica Control de electrónica de consumidor (CEC) de HDMI o habilitarla para que puede cambiar automáticamente a un origen de vídeo activo desde el modo de espera. Esta característica no es compatible con todos los televisores.
>
> Las salas de Microsoft Teams no usan un teclado. Si es necesario, el administrador debe usar el teclado en pantalla. Se necesitará un teclado o un mouse USB al realizar una imagen del dispositivo de salas de Microsoft Teams.

En las tablas siguientes se ofrecen recomendaciones para los periféricos basados en el tamaño de la sala:

**Periféricos de audio certificados de las salas de Microsoft Teams**

|Tipo de sala|Cantidad de personas|La distancia máxima recomendada entre el micrófono y el altavoz|Dispositivo por tamaño máximo de la sala|Comentarios|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'   |2 a 4  |1,5 m  |Logitech Connect  |Los dispositivos de Logitech Connect incluyen una cámara que debe colocarse en la parte delantera de la sala (no en el centro de la mesa) para captar a los asistentes locales de la reunión. |
|**Pequeño** <br/> 16' x 16'  |4 a 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |El volumen de reproducción puede ser limitado para salas más grandes.  |
|**Mediano** <br/> 18' x 20'  |6 a 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Los dispositivos de Logitech MeetUp incluyen una cámara que debe colocarse en la parte delantera de la sala (no en el centro de la mesa para captar a los asistentes locales de la reunión.). <br/> En general, las salas con mesas largas rectangulares o en forma de U pueden aprovechar los micrófonos satelitales. <br/> Debe usarse el SP 220 MS en una configuración de cadena margarita.  |
|**Grande** <br/> 15' x 32'  |12 a 16  |3 m <br/> Esta distancia se aplica también al área cubierta por cada micrófono de satélite conectado.  |Logitech Group + micrófonos de satélite <br/> Polycom trío + micrófonos de satélite <br/> Polycom CX5100 + micrófonos de satélite <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + micrófonos de satélite  |Todos los dispositivos de audio que aparecen en esta fila son compatibles con las opciones de micrófono de satélite. <br/> CX5100 incluye una cámara integrada de 360 grados de manera que el dispositivo pueda colocarse en el centro de la mesa. <br/> Debe usarse el SP 220 MS en una configuración de cadena margarita.  |

**Periféricos de video certificados de las salas de Microsoft Teams**

|Tipo de sala|Cantidad de personas|Dispositivo por tamaño de sala óptimo|Comentarios|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  |2 a 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Pequeño** <br/> 16' x 16'  |4 a 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro generalmente se combina con Logitech Group  |
|**Mediano** <br/> 18' x 20'  |6 a 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Grande** <br/> 15' x 32'  |12 a 16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > La resolución de la pantalla de la parte delantera de la sala no debe ser mayor de 1920 x 1080p.

## <a name="required-software-downloads"></a>Descargas de software necesarias

Para crear sus propias imágenes de sala de Microsoft Teams, siga las instrucciones que se indican en [Configurar una consola de sala de Microsoft Teams](console.md). Esas instrucciones le guiarán a través de la descarga de todo el software necesario para la instalación.

> [!NOTE]
> Los profesionales de IT necesitarán acceso a los archivos ISO de Windows 10 Enterprise a través de su acuerdo de licencia por volumen.

[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) es una descarga opcional que puede utilizar para aprovisionar cuentas de las salas de Microsoft Teams.

## <a name="see-also"></a>Vea también

[Examinar todos los paquetes](https://products.office.com/microsoft-teams/across-devices/devices)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias de complemento de Skype Empresarial](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
