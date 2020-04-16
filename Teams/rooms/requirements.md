---
title: Requisitos de salas de Microsoft Teams
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
description: En este artículo se resumen los requisitos para admitir salas de Microsoft Teams.
ms.openlocfilehash: 2496fcb1af7d85a3d1c3ba755a2431aff40d5a70
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521606"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de salas de Microsoft Teams

Las salas de Microsoft Teams se adaptan a diferentes tamaños de sala mediante una amplia variedad de periféricos de audio y vídeo certificados basados en el tamaño y el uso del salón. Al seleccionar el dispositivo y la consola del núcleo de la derecha, combinadas con micrófonos, altavoces, cámaras y pantallas apropiadas para el espacio, puede implementar salas de Microsoft Teams en espacios de cualquier tamaño desde espacios muy pequeños de Huddle hasta espacios de conferencia y salas de juntas muy grandes.  El conjunto completo de todos los periféricos de audio y vídeo certificados disponibles que pueden usarse para configurar el salón está disponible en el [escaparate del dispositivo](https://products.office.com/microsoft-teams/across-devices).

En este artículo se resumen los requisitos de implementación y configuración del dispositivo para admitir salas de Microsoft Teams.

La implementación implica la creación de la cuenta según se describe en [implementar salas de Microsoft Teams](rooms-deploy.md) y configurar las consolas de reunión, tal como se describe en [configurar una consola de salas de Microsoft Teams](console.md).

Además, consulte:

- [Licencias de complemento de Skype Empresarial](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opciones de licencia basadas en su plan: salas de Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Las salas de Microsoft Teams inician sesión en Microsoft Teams, Skype empresarial Server 2019, Skype empresarial Server 2015 o Skype empresarial online, y pueden unirse a reuniones hospedadas por cualquiera de estos servicios.
>
> Las plataformas anteriores, como Lync Server 2013, no son compatibles con las salas de Microsoft Teams. Salas de Microsoft Teams no es compatible con Office 365 ofrecido por 21Vianet o en los entornos GCC-High o DoD.
>
> Si tiene un servidor de Exchange local, las salas de Microsoft Teams requieren el uso de Exchange Server 2013 SP1 o posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Una implementación de hardware incluye una selección de un sistema de salas de Microsoft Teams, combinado con periféricos de audio y vídeo certificados, y una solución de cableado para integrar estos dispositivos.  Estas opciones se describen aquí.

**Sistemas de salas de Microsoft Teams compatibles**

Todos los paquetes y paquetes de Microsoft Teams Room están disponibles en la [exhibición de productos de sistemas de salas](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Consola|Procesador|MEMORIAS|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Núcleo de i5|8 GB |128 GB |
  |[Crestron Flex UC-B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Núcleo de i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Núcleo de i5|8 GB |128 GB |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Núcleo de i7|8 GB |128 GB |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Núcleo de i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Núcleo de i7|8 GB|128 GB|
  |[HP Elite Slice para salas de reuniones G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Núcleo de i5 |8 GB |128 GB |
  |[HP Elite Slice G2 audio preparado con salas de Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Núcleo de i5 |8 GB |128 GB |
  |[Concentrador ThinkSmart de Lenovo 500](https://www3.lenovo.com/us/en/hub500) |Núcleo de i5 |8 GB |128 GB |
  |[Toque Logitech](https://www.logitech.com/product/microsoft-rooms)|Núcleo de i5|8 GB |128 GB |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Núcleo de i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Núcleo de i5|8 GB |128 GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Núcleo de i5|8 GB |128 GB |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Núcleo de i5|8 GB|128 GB|
  ||||||

> [!NOTE]
> - No se admiten los procesadores m3 principales.
> - Necesita una unidad USB de 32 GB o superior configurada como un medio de instalación de Windows 10 de arranque para Windows 10 Enterprise.

**Tabletas Surface Pro compatibles con sistemas de estilo Dock**

  |Lápiz|Procesador|MEMORIAS|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Núcleo de i5 |16 GB u 8 GB |128 GB o más |
  |Surface Pro </br>(quinta generación) |Núcleo de i5 |8 GB o 4 GB |128 GB o más |
  |Surface Pro 4 |Núcleo de i5 |8 GB o 4 GB |128 GB o más |

- Los dispositivos Surface Pro requieren una de las siguientes opciones de estación de acoplamiento para proteger una tableta de la tabla sala de reuniones.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Serie MSR MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versiones de firmware certificadas para periféricos de audio y vídeo USB

Estos dispositivos están disponibles en la [sala de productos](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) de los sistemas de [https://office.com/teamsdevices](https://office.com/teamsdevices)salas y.

|Periféricos de Microsoft Teams Rooms|Versión de firmware certificada | La cámara admite el uso de cámaras de contenido|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930E](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio: 1.0.172 <br/> Vídeo: 1.0.156  |
|[Conexión Logitech ConferenceCam](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Grupo Logitech](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Cámara de portaoculares de poli Eagle](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100 ](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   |  1.2.0.70232   |
|[Directora de ojos Eagle de Polycom II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Barra de medios Polycom Studio](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom trío 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 procesador de conferencia de audio](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Micrófono de matriz de tabla Shure MXA 310](https://www.shure.com/en-US/products/microphones/mxa310) | 4,1 |
|[Shure Intellimix P300 procesador de conferencia de audio](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 con Intellimix MIC de matriz de techo](https://www.shure.com/en-US/products/microphones/mxa910) | 4,1|
|[Biamp Tesira de AVB VT4 de audio fijo DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Micrófono SENNHEISER TeamConnect techo 2](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA ex-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  DSP Biamp: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink amplificador +</br> Sennheiser TCC2 de micrófono techo </br> + Bose EdgeMax altavoz de techo](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  DSP Bose: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
||||||

&Dagger;Los clientes pueden elegir la interfaz de Dante o el conmutador de red recomendado por Biamp/Sennheiser para este paquete.

#### <a name="usb-extenders"></a>Extensores de USB

- Los puertos USB de los acoplamientos de Tablet PC son compatibles con USB 3,0. Puede usar un extensor USB 2, pero si lo hace, se le limitará a las velocidades de USB 2. x en el extremo de la parte. Los extensores no se recomiendan para periféricos USB 3,0.
- Un extensor debe cumplir con las especificaciones de USB 2,0 o posterior.
  - Los acoplamientos de Tablet PC admiten al menos dos fases de extensión de concentrador USB externo. Si conecta más de dos concentradores USB en serie, consulte con el fabricante del Dock para confirmar si admiten la conexión de serie.
  - Conexión GbE por cable en el salón. Cable Ethernet de una longitud adecuada.
  - Se muestran hasta 2 1080-p con conexiones HDMI. Cables HDMI de longitud adecuada.

> [!NOTE]
> Si se usa un televisor como pantalla, debe ser compatible con la característica Control de electrónica de consumidor (CEC) de HDMI o habilitarla para que puede cambiar automáticamente a un origen de vídeo activo desde el modo de espera. Esta característica no es compatible con todos los televisores.
>
> Las salas de Microsoft Teams no usan un teclado. En caso de necesitarlo, el administrador debe usar el teclado en pantalla. Al crear imágenes del dispositivo de salas de Microsoft Teams, se necesitará un teclado o un mouse USB.

En las siguientes tablas se proporcionan recomendaciones para los periféricos basados en el tamaño de la sala:

**Microsoft Teams salones de audio certificados**

|Tipo de sala|Cantidad de personas|Distancia máxima recomendada desde el micrófono al altavoz|Dispositivo por tamaño máximo de la sala|Comentarios|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '   |2 a 4  |1,5 m  |Logitech Connect  |Los dispositivos Logitech Connect incluyen una cámara que debe estar situada en la parte delantera de la sala (no en el centro de la tabla) para capturar a los asistentes a una reunión local. |
|**Pequeña** <br/> 16 x 16  |4 a 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |El volumen de reproducción se puede limitar para salas más grandes.  |
|**Media** <br/> 18 ' x 20 '  |6 – 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000Md  |Logitech MeetUp incluye una cámara para que se coloque en la parte delantera del salón (no en el centro de la tabla para capturar asistentes de reunión locales). <br/> En general, los salones con tablas largas rectangulares o con forma de u pueden beneficiarse de micrófonos satélite. <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  |
|**Grande** <br/> 15 ' x 32 '  |de 12 a 16  |3 m <br/> Esta distancia también se aplica al área cubierta por cada micrófono satélite conectado.  |Grupo Logitech + satélite micrófonos <br/> Micrófonos de Polycom trío + satélite <br/> Micrófonos de Polycom CX5100 + satélite <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-y micrófonos satélite  |Todos los dispositivos de audio que se enumeran en esta fila admiten opciones de micrófono satelital. <br/> CX5100 incluye una cámara integrada de 360 grados para que el dispositivo pueda colocarse en el centro de la tabla. <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  |

**Microsoft Teams salones de video certificados**

|Tipo de sala|Cantidad de personas|Dispositivo con un tamaño de sala óptimo|Comentarios|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '  |2 a 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100   ||
|**Pequeña** <br/> 16 x 16  |4 a 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   |Logitech PTZ Pro suele estar incluido con Logitech Group  |
|**Media** <br/> 18 ' x 20 '  |6 – 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||
|**Grande** <br/> 15 ' x 32 '  |de 12 a 16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||

 > [!NOTE]
 > El anverso de la resolución de pantalla de la habitación debe ser mayor que 1920x1080p.

## <a name="required-software-downloads"></a>Descargas de software necesarias

Para crear su propia imagen de salones de Microsoft Teams, siga las instrucciones de [configurar una consola de salas de Microsoft Teams](console.md). Estas instrucciones le guiarán a través de la descarga de todo el software necesario para la instalación.

> [!NOTE]
> Los profesionales de ti necesitarán acceder a los archivos de ISO de Windows 10 Enterprise a través de su contrato de licencias por volumen.

[SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105) es una descarga opcional que puede usar para aprovisionar cuentas de salas de Microsoft Teams.

## <a name="see-also"></a>Consulte también

[Examinar todos los paquetes](https://products.office.com/microsoft-teams/across-devices/devices)

[Plan para salas de Microsoft Teams](rooms-plan.md)

[Implementar salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de salas de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias complementarias de Skype Empresarial](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
