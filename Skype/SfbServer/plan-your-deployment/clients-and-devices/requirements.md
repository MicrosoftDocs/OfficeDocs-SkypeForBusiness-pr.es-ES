---
title: Requisitos de Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: En este artículo se resume los requisitos para la compatibilidad con sistemas de salas de Skype v2.
ms.openlocfilehash: 8cadbed89be0301071c2c8a30c715f786b549d36
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716454"
---
# <a name="skype-room-systems-v2-requirements"></a>Requisitos de Sistemas de salas de Skype v2

En este artículo se resume los requisitos para la compatibilidad con sistemas de salas de Skype v2. 

La implementación incluirá la creación de cuentas como se describe en [implementar sistemas de salón de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) y configurar una consola de reunión tal como se describe en [Configurar una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md). 

También es posible que necesite hacer referencia a:

- [Licencias complementarias de Skype Empresarial](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [En función del plan de opciones de licencia: v2 de sistemas de salón de Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Sistemas de salón de Skype v2 está pensada para su uso con Skype para Business Server 2019, Skype Business Server 2015, Microsoft Teams o Skype para profesionales en línea. <br><br>No se espera plataformas anteriores al igual que Lync Server 2013 para trabajar con sistemas de salas de Skype v2.

> [!NOTE]
> Si usa un servidor de Exchange en prem, sistemas de salón de Skype v2 requiere el uso de Exchange Server 2013 SP1 o posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware

Sistemas de salón de Skype v2 puede escalar a tamaños de sala diferente a través de accesorios según periféricos de audio y vídeos. El hardware que aparecen en este artículo es compatible con los modos de reunión de Skype y los equipos.  Periféricos de audio y vídeos conectan a sistemas de salón de Skype v2 a través de una conexión USB o HDMI en el dispositivo de acoplamiento. También necesitará:

- Un 32GB o mayor disco USB que se configurará como medio de instalación de Windows de arranque para Windows 10 Enterprise. 

- Uno de los siguientes tabletas o consolas:

**Tabletas compatibles**

|Tablet PC|Procesador|MEMORIA RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface Pro (2017)  |I5 principales  |8GB  |256GB  |
|Surface Pro (2017)  |I5 principales  |8GB  |128GB  |
|Surface Pro (2017)  |I5 principales  |4GB  |128GB  |
|Surface Pro 4       |I5 principales  |8GB  |256GB  |
|Surface Pro 4       |I5 principales  |4GB  |128GB  |

> [!NOTE]
> No se admiten los procesadores de núcleo M3.

**Consolas compatibles**

|Consola|Procesador|MEMORIA RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Lenovo ThinkSmart concentrador 500](https://www3.lenovo.com/us/en/hub500) |I5 principales  |8GB  |128GB  |  
|[HP sector Elite para G2 de salas de reuniones](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |I5 principales  |8GB  |128GB  |  

- Una de las siguientes opciones de estación de acoplamiento para proteger una tableta a la reunión de la sala tabla. 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [SR Crestron](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Serie de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**Certificado de las versiones de firmware para periféricos USB de audio y vídeos**

|Periféricos v2 de sistemas de salón de Skype|Versión de firmware certificada para sistemas de salón de Skype v2|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Vídeo - 1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Group](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ 2 Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4,7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> |  1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **Extender USB**:

  - Puertos USB en lo acopla tablet son 3.0 USB compatible. Puede utilizar un extensor de 2.x USB, pero al hacerlo por lo que le limitarán a velocidades de 2.x USB en el extremo y si lo hace por lo que no se recomienda para periféricos USB 3.0.

  - Un objeto extender debe cumplir con USB 2.0 o especificaciones más reciente.

  - Lo acopla Tablet admite al menos dos etapas de extensión de concentrador USB externo. Si necesidad de conectar más de dos concentradores USB en serie, deberá consultar con el fabricante de muelle para confirmar si lo hace por lo que es compatible.

- Conexión por cable de GbE en la sala. Cable Ethernet de una longitud adecuada.

- Hasta dos pantallas 1080p con conexiones de HDMI. Cables HDMI de longitud adecuada.

    > [!NOTE]
    > Una televisión de consumo usada como una parte delantera del salón de mostrar las necesidades de soporte técnico o habilitar la característica de Control de electrónica de consumidor (CEC) de HDMI para que puede cambiar automáticamente a un origen de vídeo activo de modo de espera. Esta característica no se admite en todos los televisores. 

> [!NOTE]
> Sistemas de salón de Skype v2 no utiliza un teclado. En caso de necesitarlo, el administrador debe usar el teclado en pantalla. Un teclado o mouse USB se requerirán cuando el dispositivo v2 de Skype salón sistemas de procesamiento de imágenes. 

En las tablas siguientes se proporcionan recomendaciones para periféricos según el tamaño de la sala:

**Sala de Skype sistemas v2 Certified periféricos de Audio**

|**Tipo de sala**|**Cantidad de personas**|**Distancia máxima recomendada desde el micrófono hasta la persona que habla**|**Dispositivo por tamaño máximo de la sala**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Los dispositivos Logitech conectar incluyen una cámara de modo que deberá estar situado en la parte frontal de la sala (no el centro de la tabla) para capturar los asistentes a la reunión local.  <br/> |
|**Pequeña** <br/> 16' x 16'  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |El volumen de reproducción puede estar limitado para salas más grandes.  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000  <br/> |El Logitech MeetUp incluye una cámara por lo que deberá estar situado en la parte frontal de la sala (no el centro de la tabla para capturar los asistentes a la reunión local).  <br/> En general, salones con tablas durante cuánto tiempo rectangulares o en forma de u es posible que se benefician de micrófonos de satélite adicionales.  <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  <br/> |
|**Grande** <br/> 15' x 32 º  <br/> |12-16  <br/> |3m  <br/> Esta distancia también se aplica al área cubierta por cada micrófono satelital adicional conectado al dispositivo de audio en cuestión.   <br/> |Grupo de Logitech + micrófonos de satélite  <br/> Micrófonos de satélite Polycom Trio +  <br/> Polycom CX5100 + micrófonos de satélite  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 + micrófonos de satélite  <br/> |Todos los dispositivos de audio que se enumeran en esta fila admiten opciones de micrófono satelital.  <br/> CX5100 incluye una cámara integrada de 360 grados de manera que el dispositivo puede situarse en el centro de la mesa.  <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  <br/> |

**Sala de Skype sistemas v2 Certified periféricos vídeo**

|Tipo de sala|Cantidad de personas|Dispositivo por el tamaño de la sala óptimo|Comentarios|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Pequeña** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro suele incluirse con grupo de Logitech  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> ||
|**Grande** <br/> 15' x 32 º  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> MSR de Polycom  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > Parte frontal de la resolución de pantalla de la sala debe establecerse en no superior a 1920x1080p.

## <a name="required-software-downloads"></a>Descargas de software necesarias

Para crear su propia imagen de v2 de sistemas de salón de Skype, siga las instrucciones de [Configurar una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md). Las instrucciones le guiará por el proceso de descarga de todo el software necesario para el proceso de instalación. 

> [!NOTE]
> LOS profesionales de TI tendrá acceso a los archivos de Windows 10 Enterprise ISO a través de su contrato de licencia por volumen.

Además, deseará probablemente una copia de [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a menudo se usan para aprovisionar cuentas v2 de sistemas de salón de Skype.


## <a name="see-also"></a>Vea también

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)

[Implementar Sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar una consola de Sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)

[Administrar Sistemas de salas de Skype v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Licencias complementarias de Skype Empresarial](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
