---
title: Requisitos de la sala de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Obtén información sobre los requisitos para admitir Salas de Microsoft Teams, incluida la elección del dispositivo, micrófonos, altavoces, cámaras y pantallas adecuados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3d8084c1136ef462dcced10b73879d2de2a48671
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789765"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de la sala de Microsoft Teams

Salas de Microsoft Teams escala a diferentes tamaños de sala. Salas de Teams usar una amplia variedad de periféricos de audio y vídeo certificados según el tamaño y el uso de la sala. Al seleccionar el dispositivo y la consola del núcleo derecho, combinados con micrófonos, altavoces, cámaras y pantallas adecuadas para el espacio, puedes implementar Salas de Microsoft Teams en espacios de cualquier tamaño, desde pequeños espacios de reunión hasta grandes espacios de conferencia y salas de juntas.  El conjunto completo de todos los periféricos de audio y vídeo certificados disponibles que pueden ser utilizados para configurar su sala está disponible en la [Escaparate de dispositivos](https://products.office.com/microsoft-teams/across-devices).

Este artículo resume los requisitos de implementación y configuración de los dispositivos para auxiliar a las salas de Microsoft Teams.

La implementación implica la creación de cuentas de recursos y la configuración de Salas de Teams como se describe en [Implementar Salas de Microsoft Teams](rooms-deploy.md).

Consulte:

- [Opciones de licencias en función de su plan: Salas de Microsoft Teams](rooms-licensing.md)

> [!NOTE]
> Salas de Microsoft Teams iniciar sesión en Microsoft Teams, Skype Empresarial Server 2019 o Skype Empresarial Server 2015 y puede unirse a reuniones hospedadas por cualquiera de estos servicios.
>
> Las plataformas anteriores como Lync Server 2013 no son compatibles con las Salas de Microsoft Teams. Salas de Microsoft Teams no es compatible con Microsoft 365 o Office 365 a través de 21Vianet o entornos DoD.
>
> Si tiene un servidor de Exchange local, las salas de Microsoft Teams requieren el uso de Exchange Server 2013 SP1 o posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Una implementación de hardware incluye una selección de un sistema de sala de Microsoft Teams, combinada con periféricos de audio y vídeo certificados, y una solución de cableado para integrar estos dispositivos.  A continuación se describen todas las opciones.

**Sistemas de sala de Microsoft Teams compatibles**

Todos los dispositivos y paquetes actuales de la Sala de Microsoft Teams están disponibles en el [escaparate de productos de los sistemas de la Sala](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Consola|Procesador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex UC-C140-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-M150-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Crestron Flex UC-MMX30-T con transmisor de presentación UC (UC-PR) y PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-BX30-T con transmisor de presentación UC (UC-PR) y PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-CX100-T con transmisor de presentación UC (UC-PR) y PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-B30-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-C100-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M50-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M70-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 GB |128 GB |
   |Crestron FLEX UC-B30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-Bx30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MM30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MMX30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M50-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX50-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M70-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX70-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-C100-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-CX100-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 con Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice para salas de reuniones G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 con audio preparado para Salas de Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Partner de sector HP listo con Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[Logitech Tap con Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap e Intel Tiger Canyon NUC PC |Core i5|8 GB|128 GB|
  |Consola LOGITECH CON Lenovo Core Compute |Core i5|8 GB|128 GB|
  |[Logitech Tap y Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T con Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Kit Poly G40-T con USB Poly Studio, con Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g40) |Core i5| 8 GB | 128 GB|
  |[Kit Poly G85-T con Poly Eagle Eye Director II, con Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g85) |Core i5| 8 GB | 128 GB|
  |Consola Poly GC8 con Lenovo Thinksmart Core|Core i5|8 GB|128 GB|
  |Consola Poly GC8 con Dell Optiplex 7080|Core i5|8 GB|128 GB|
  |[Yealink MVC300 con Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 con Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 con Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 con Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - Los procesadores M3 no son compatibles.
> - Necesita una unidad USB de 32 GB o superior configurada como medio de instalación de arranque Windows para Windows 10 Enterprise.

**Tabletas Surface Pro compatibles para sistemas de estilo de acoplamiento**

  |Tableta|Procesador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB o 8 GB |128 GB o más |
  |Surface Pro </br>(quinta gen.) |Core i5 |8 GB o 4 GB |128 GB o más |
  |Surface Pro 4 |Core i5 |8 GB o 4 GB |128 GB o más |

- Surface Pro dispositivos requieren una de las siguientes opciones de la base de acoplamiento:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versiones de firmware certificadas para periféricos de vídeo y audio USB

Estos dispositivos se encuentran disponibles en el [escaparate del sistema de la sala ](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) y [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periféricos de la sala de Microsoft Teams|Versión de firmware certificada | La cámara admite el uso de cámara de contenido|
|:--- |:--- | :--- |
|[Cámara de Aver VC520 Pro + Manos libres](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Sistema de conferencias Aver VC520 PRO2](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ Barra de sonido de la cámara](https://www.averusa.com/products/conference-camera/vb342plus) | Barra de sonido: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Barra de sonido de la cámara de Aver VB130](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Audiocodes RXVCAM50L](https://www.audiocodes.com/solutions-products/products/room-experience-rx-suite/rxvcam50lm-video-camera) |1.0.5 |
|[Barra de vídeo Bose VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Centro de conferencias de Web-Based Biamp Devio SCR-20CX con micrófono de techo](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Centro de conferencias de Web-Based Biamp Devio SCR-20TX con micrófono de escritorio](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ Camera](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|Cámara Huddly L1 con kit [MTR Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) | Huddly L1 Cámara: 1.2.1 </br> Crestron UC-C100-T con ASUS Tek Computer INC 9934 computación 1.0.20.246 o superior |
|Cámara Huddly L1 con kit [Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W | Huddly L1 Cámara: 1.2.9 </br> Crestron UC-CX100-T con ASUS Tek Computer INC 9934 1.00.20.246 o superior |
|Cámara Huddly L1 con kit DE MTR Crestron UC-M70-T | Huddly L1 Cámara: 1.2.1 </br> Crestron UC-M70-T con ASUS Tek Computer INC 9934 computación 1.0.20.246 o superior |
|Cámara Huddly L1 con kit DE MTR Crestron UC-MX70-T | Huddly L1 Cámara: 1.2.1 </br> Crestron UC-MX70-T con ASUS Tek Computer INC 9934 computación 1.0.20.246 o superior |
|[Cámara Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 Video Bar](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|3.4.0| &#x2714; |
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio: 1.0.172 <br/> Video: 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Cámara Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.md)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://support.polycom.com/content/dam/polycom-support/products/peripherals/eagle-eye-director-ii/user/en/eagleeye-director-ii-admin-guide-2-0.pdf#:~:text=The%20Polycom%C2%AE%20EagleEye%E2%84%A2%20Director%20II%20camera%20is%20a,while%20the%20other%20camera%20tracks%20the%20second%20speaker.)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Barra de vídeo Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Cámara Poly Studio E70](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[Poly Studio R30](https://www.poly.com/us/en/products/video-conferencing/studio/studio-r30)|2.0.0.001096|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Manos libres: 4.6.55 <br/> Micrófono de extensión: 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT, DMP 128 Plus C AT, DMP 128 Plus C V, DMP 128 Plus C, DMP 128 Plus AT, DMP 128 Plus, DMP 128 FlexPlus C AT, DMP 128 FlexPlus C V AT)](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT, DMP 64 Plus C AT, DMP 64 Plus C V, DMP 64 Plus C)](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Solución de techo Yamaha ADECIA](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Solución yamaha ADECIA Tabletop](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 para el micrófono de tabla, D1.2.0 para el procesador (el mismo contenido que V1.5.1)|
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Barra de vídeo todo en uno Yealink UVC34](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Barra de vídeo todo en uno Yealink UVC40](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300) +</br>[Shure MXA 910 con micrófono de techo Intellimix](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br>[Altavoz de techo MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Micrófono de matriz de tabla MXA310: 4.1.41 </br> Altavoz MXN5W-C: 1.0.4 |
|[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300) + </br>[Shure MXA 920 con micrófono de matriz de techo Intellimix](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Altavoz de techo MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.7.7 </br> Micrófono de matriz de techo MXA920: 1.1.56 </br> Altavoz MXN5W-C: 1.5.6 |
|ANIUSB + </br> [Shure MXA 920 con micrófono de matriz de techo Intellimix](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Altavoz de techo MXN5](https://www.shure.com/en-US/products/loudspeakers/mxn5)| ANIUSB: 4.4.7 </br> MXA920: 1.1.56 </br> MXN5: 1.5.6|
|[Shure MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300) +</br>[Altavoz de techo MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altavoz MXN5-C: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 procesador de audioconferencia](https://www.shure.com/products/mixers/p300) +</br>[Altavoz de techo MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 Micrófono de matriz lineal de pared de 4ft: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altavoz MXN5-C: 1.1.1 |
|[Shure MXA 910 con micrófono intellimix de matriz de techo](https://www.shure.com/products/microphones/mxa910) + </br> [Software de sala Shure Intellimix](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Software de sala Shure Intellimix: 3.0.4.14 </br> Shure MXA 910 con micrófono intellimix de matriz de techo: 4.4.11 </br> Altavoces Shure MXN5-C: 1.2.1 </br> Crestron UC-C100-T con ASUS Tek Computer INC 9934 compute | 
|[Shure MXA 910 con micrófono intellimix de matriz de techo](https://www.shure.com/products/microphones/mxa910) + </br> [Software de sala Shure Intellimix](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Software de sala Shure Intellimix: 3.2.0.52 </br> Shure MXA 910 con micrófono intellimix de matriz de techo: 4.4.11 </br> Altavoces Shure MXN5-C: 1.2.1 </br> Lenovo ThinkSmart Core: versión del sistema operativo Windows IoT 19h2/20h2 |
|[Sennheiser TeamConnect Altavoz inteligente/TC ISP (T-Rock)](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 audio fijo DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Micrófono de techo 2 Sennheiser TeamConnect](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15 </br> TCC2: 1.3.3 </br>EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Micrófono de techo Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Altavoz montado en techo Biamp Desono C-IC6](https://www.biamp.com/products/tesira-speakers)| Versión de audio FW: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Parle TTM-X(Micrófono de tabla)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |Versión de audio FW: 3.15|
|Biamp Tesira FORTE X Series +</br>[Serie SCX de Devio](https://www.biamp.com/products/product-families/devio/medium-large-room-solutions#devio-scx-400)|Tesira FORTE X Series: 4.2.5 </br> Serie Devio SCX: 4.2.5|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink amplificador +</br> Micrófono de techo Sennheiser TCC2 + </br> Altavoz de techo Bose EdgeMax EM180](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Altavoz de techo](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier +</br> [Micrófono de techo Sennheiser TCC2](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Altavoz de techo DesignMax DM2C -LP](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Micrófono de techo Sennheiser TCC2](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Altavoz de techo EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |
|Núcleo Q-SYS QSC ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) o [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Micrófono de techo Sennheiser TCC2](https://en-us.sennheiser.com/tcc2) + </br> Amplificador QSC ([serie SPA](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) o [serie CX-Q](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Altavoces de la serie QSC AcousticDesign](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> Cámara IP QSC ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) opcional + </br> [Puente USB de E/S Q-SYS de QSC](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) opcional | QSC Q-SYS Core, cámara PTZ-IP y puente USB de E/S: QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Micrófono de techo: TCC2 - 1.5.1, Dante 1.2.0 </br> Amplificadores QSC: N/A </br> Altavoces de la serie QSC AcousticDesign: N/A | 


&Dagger; Los clientes pueden elegir la interfaz Dante o el conmutador de red recomendado por Biamp/Sennheiser para este paquete.

#### <a name="usb-extenders"></a>Extensor USB

- Los puertos USB de las bases de acoplamiento de las tabletas son compatibles con USB 3.0. Puedes usar un extensor USB 2.x, pero se te limitará a las velocidades de USB 2.x en el extremo lejano. Los extensores no se recomiendan para los periféricos con USB 3.0.
- Un extensor debe cumplir con las especificaciones USB 2.0 o posteriores.
  - Las bases de acoplamiento son compatibles con un mínimo de dos fases de extensión de concentrador USB externo. Si conectas más de dos concentradores USB en serie, comprueba con el fabricante del acoplamiento si admiten la conexión en serie.
  - Conexión GbE cableada en la sala. Cable de Ethernet de longitud apropiada.
  - Hasta dos pantallas de 1080p con conexiones HDMI. Cable HDMI de longitud adecuada.

> [!NOTE]
> Si se usa un televisor como pantalla, debe ser compatible con la característica Control de electrónica de consumidor (CEC) de HDMI o habilitarla para que puede cambiar automáticamente a un origen de vídeo activo desde el modo de espera. Esta característica no es compatible con todos los televisores.
>
> Las salas de Microsoft Teams no usan un teclado. Si es necesario, el administrador debe usar el teclado en pantalla. Se necesitará un teclado o un mouse USB al realizar una imagen del dispositivo de salas de Microsoft Teams.

En las tablas siguientes se ofrecen recomendaciones para los periféricos basados en el tamaño de la sala:

**Periféricos de audio certificados de las salas de Microsoft Teams**

|Tipo de sala|Cantidad de personas|La distancia máxima recomendada entre el micrófono y el altavoz|
|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'   |2 a 4  |1,5 m  |
|**Pequeño** <br/> 16' x 16'  |4 a 6  |2,0 m  |
|**Mediano** <br/> 18' x 20'  |6 a 12  |2,4 m  |
|**Grande** <br/> 15' x 32'  |12 a 16  |3 m <br/> Esta distancia se aplica también al área cubierta por cada micrófono de satélite conectado.  |

**Periféricos de video certificados de las salas de Microsoft Teams**

|Tipo de sala|Cantidad de personas|
|:-----|:-----|
|**Foco** <br/> 10' x 9'  |2 a 4  |
|**Pequeño** <br/> 16' x 16'  |4 a 6  |
|**Mediano** <br/> 18' x 20'  |6 a 12  |
|**Grande** <br/> 15' x 32'  |12 a 16  |

 > [!NOTE]
 > La resolución de la pantalla de la parte delantera de la sala no debe ser mayor de 1920 x 1080p.


## <a name="see-also"></a>Vea también

[Examinar todos los paquetes](https://products.office.com/microsoft-teams/across-devices/devices)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
