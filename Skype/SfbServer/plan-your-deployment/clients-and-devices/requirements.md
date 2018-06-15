---
title: Requisitos de Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: En este artículo se resume los requisitos para la compatibilidad con sistemas de salas de Skype v2.
ms.openlocfilehash: 1d44178beb69cda78b72bb8d0e599af81be39321
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887880"
---
# <a name="skype-room-systems-v2-requirements"></a>Requisitos de Sistemas de salas de Skype v2
 
En este artículo se resume los requisitos para la compatibilidad con sistemas de salas de Skype v2. 
  
La implementación incluirá la creación de cuentas como se describe en [implementar sistemas de salón de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) y configurar una consola de reunión tal como se describe en [Configurar una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md). También es posible que necesita hacer referencia a [Skype para Business licensing del complemento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>Requisitos de hardware

Sistemas de salón de Skype v2 puede escalar a tamaños de sala diferente a través de accesorios según periféricos de audio y vídeos. Periféricos de audio y vídeos conectan a sistemas de salón de Skype v2 a través de una conexión USB o HDMI en el dispositivo de acoplamiento. También necesitará:
  
- Un 32GB o mayor disco USB que se configurará como medio de instalación de Windows de arranque para Windows 10 Enterprise. 
    
- Uno de los siguientes tabletas o consolas:
    
**Tabletas compatibles**
|Tablet PC|Procesador|MEMORIA RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface Pro 4    |I5 principales  |4GB  |128GB  |
|Surface Pro 4    |I5 principales  |8GB  |256GB  |    
|Surface Pro (2017)  |I5 principales  |4GB  |128GB  |
|Surface Pro (2017)  |I5 principales  |8GB  |256GB  |
|Surface Pro (2017)  |Core i7  |8GB  |128GB  |
|Surface Pro (2017)  |Core i7  |16GB  |512GB  |
|Surface Pro (2017) |Core i7  |16GB  |1TB  |
   
> [!NOTE]
> No se admiten los procesadores de núcleo M3.

**Consolas compatibles**
|Consola|Procesador|MEMORIA RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Concentrador de Lenovo 500](https://www3.lenovo.com/us/en/hub500) |I5 principales  |8GB  |128GB  |  
 <!-- HP dock is still pending  -->  
    
- Una de las siguientes opciones de estación de acoplamiento para proteger una tableta a la reunión de la sala tabla. 
    
  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)
    
  - [SR Crestron](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Serie de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


 
**Certificado de las versiones de firmware para periféricos USB de audio y vídeos**
|**Periféricos v2 de sistemas de salón de Skype**|**Versión de firmware certificada para sistemas de salón de Skype v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Vídeo - 1.0.156  <br/> |
|[Logitech ConferenceCam conectar](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Grupo de Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Polycom RealPresence trío](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[510 Jabra](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
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

|**Tipo de salón**|**Número de personas**|**Distancia máximo recomendado de micrófono a persona hablando**|**Dispositivo el tamaño máximo de salón**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Los dispositivos Logitech conectar incluyen una cámara de modo que deberá estar situado en la parte frontal de la sala (no el centro de la tabla) para capturar los asistentes a la reunión local.  <br/> |
|**Pequeña** <br/> 16' x 16'  <br/> |4-6  <br/> |m 2.0  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |El volumen de reproducción puede estar limitado para salas más grandes.  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000  <br/> |El Logitech MeetUp incluye una cámara por lo que deberá estar situado en la parte frontal de la sala (no el centro de la tabla para capturar los asistentes a la reunión local).  <br/> En general, salones con tablas durante cuánto tiempo rectangulares o en forma de u es posible que se benefician de micrófonos de satélite adicionales.  <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  <br/> |
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

Necesitará las siguientes descargas para crear su propia imagen de v2 de sistemas de salón de Skype:
  
- El [paquete de instalación de sistemas de salón de Skype v2](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Obtenga una copia de la versión de 64 bits de la actualización del creador de empresa de Windows 10 (en inglés, compilación 1703). 
    
    > [!NOTE]
    > Ya no se admite la versión de 64 bits de edición de Windows 10 Enterprise aniversario (en inglés, versión 1607) a partir de sistemas de salón de Skype v2 versión 3.0.12.0 (actualización 3). 
  
- El admitidos [Surface Pro 4 controladores](https://go.microsoft.com/fwlink/?linkid=856887) o los [controladores Surface Pro](https://go.microsoft.com/fwlink/?linkid=856888).
    
Estas descargas deben combinarse en un disco de medios de instalación de Windows arranque de una manera específica, describen más detalladamente en [Configure una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md). 
  
Además, deseará probablemente una copia de [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a menudo se usan para aprovisionar cuentas v2 de sistemas de salón de Skype.
  
## <a name="see-also"></a>Vea también

[Planeación de la sala de Skype v2 de sistemas](skype-room-systems-v2-0.md)
  
[Implementación de salón de Skype v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Licencias complementarias de Skype Empresarial](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)