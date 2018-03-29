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
description: Este artículo resume los requisitos para admitir un v2 de sistemas de salas de Skype.
ms.openlocfilehash: ca922efa719b956da5516958ce6f684b013ddc62
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Requisitos de Sistemas de salas de Skype v2
 
Este artículo resume los requisitos para admitir un v2 de sistemas de salas de Skype. 
  
La implementación implicará la creación de cuentas tal como se describe en [implementar sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) y configurar una consola de reunión como se describe en [Configurar una consola de sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md). También debe hacer referencia a [Skype para Business licensing del complemento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>Requisitos de hardware

Sistemas de salas de Skype v2 puede escalar a tamaños de sala diferente a través de accesorios dependiendo de periféricos de audio y vídeo. Periféricos de audio y vídeo conectan con sistemas de salas de Skype v2 a través de una conexión USB o HDMI en el dispositivo de acoplamiento. También necesitará:
  
- Un 32GB o disco USB mayor que configurará como medio de instalación de Windows de arranque para Windows 10 Enterprise. 
    
- Una de las siguientes tablas:
    
**Tabletas compatibles**


|**Tablet PC**|**Procesador**|**MEMORIA RAM**|**Disco**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 & sup1;  <br/> |Core i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro 4 & sup1;  <br/> |Core i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro & sup1; <br/> |Core i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro & sup1; <br/> |Core i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |8GB  <br/> |128GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16GB  <br/> |512GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16GB  <br/> |1TB  <br/> |
   
& sup1; : No se admite M3 núcleo en este modelo.
    
 
    
- Una de las siguientes opciones de la estación de acoplamiento para proteger la tableta a la reunión sala de tabla. 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [SR de Crestron](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Serie Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)

  - [Concentrador de Lenovo 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**Certificado de las versiones de firmware de periféricos USB de audio y vídeo**
|**Periféricos de los sistemas de salas de Skype v2**|**Versión de firmware certificada para sistemas de salas de Skype v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Vídeo: 1.0.156  <br/> |
|[Conectar Logitech ConferenceCam](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Group](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Trío de Polycom RealPresence](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |c 100  <br/> |
   
- **Extensores USB**:
    
  - Puertos USB tablet muelles son USB 3.0 compatible. Puede utilizar un extensor de 2.x USB, pero al hacerlo así le limitarán a velocidades USB 2.x en el extremo y al hacerlo no se recomienda para periféricos USB 3.0.
    
  - Un extensor debe cumplir las especificaciones más recientes o USB 2.0.
    
  - Muelles de Tablet PC admiten al menos dos etapas de extensión de concentrador USB externo. Si necesita conectar más de dos concentradores USB en serie, debe consultar con el fabricante de dock para confirmar que al hacerlo así se admite.
    
- Conexión GbE por cable en la sala. Cable Ethernet de una longitud adecuada.
    
- Hasta dos pantallas 1080p con conexiones HDMI. Cables HDMI de longitud adecuada.
    
    > [!NOTE]
    > Una televisión de consumo que se utiliza como un frente de las necesidades de visualización de sala para soporte o habilitar la característica de Control de electrónica de consumo (CEC) de HDMI por lo que puede cambiar automáticamente a un origen de vídeo activo en modo de espera. Esta característica no se admite en todos los televisores. 
  
> [!NOTE]
> Sistemas de salas de Skype v2 no utiliza un teclado. En caso de necesitarlo, el administrador debe usar el teclado en pantalla. A USB keyboard or mouse will be required when imaging the Skype Room Systems v2 device. 
  
Las siguientes tablas ofrecen recomendaciones para periféricos basados en el tamaño de la sala:
  
**Sala de Skype v2 de sistemas certificados de periféricos de Audio**

|**Room Type**|**Number of People**|**Distancia máxima recomendada de micrófono a la persona que habla**|**Device by maximum room size**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2-4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |The Logitech Connect devices include a camera so it must be positioned at the front of the room (not center of table) to capture local meeting attendees.  <br/> |
|**Small** <br/> 16' x 16'  <br/> |4-6  <br/> |2,0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |El volumen de reproducción puede estar limitado para salas más grandes.  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |The Logitech MeetUp includes a camera so it must be positioned at the front of room (not center of table to capture local meeting attendees).  <br/> In general, rooms with long rectangular or u-shaped tables may benefit from additional satellite microphones.  <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  <br/> |
|**Large** <br/> 15' x 20'  <br/> |12-16  <br/> |3m  <br/> Esta distancia también se aplica al área cubierta por cada micrófono satelital adicional conectado al dispositivo de audio en cuestión.   <br/> |Logitech Group + satellite mics  <br/> Polycom Trio+ satellite mics  <br/> Polycom CX5100 + satellite mics  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + satellite mics  <br/> |Todos los dispositivos de audio que se enumeran en esta fila admiten opciones de micrófono satelital.  <br/> CX5100 incluye una cámara integrada de 360 grados de manera que el dispositivo puede situarse en el centro de la mesa.  <br/> SP 220 MS se debe usar con la configuración de cadena de margarita.  <br/> |
   
**Skype Room Systems v2 Certified Video Peripherals**

|**Room Type**|**Number of People**|**Device by Optimal room size**|**Comentarios**|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Small** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro often bundled with Logitech Group  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Large** <br/> 15' x 20'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
   
## <a name="required-software-downloads"></a>Descargas de software necesarias

You will need the following downloads to build your own Skype Room Systems v2 image:
  
- The [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Obtain a copy of the 64-bit version of Windows 10 Enterprise Creator's Update (English language, build 1703). 
    
    > [!NOTE]
    > The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0 (update 3). 
  
- The supported [Surface Pro 4 drivers](https://go.microsoft.com/fwlink/?linkid=856887) or [Surface Pro drivers](https://go.microsoft.com/fwlink/?linkid=856888).
    
These downloads need to be combined into a bootable Windows installation media disk in a specific way, described further in [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md). 
  
In addition, you will probably want a copy of the [Powershell script](https://go.microsoft.com/fwlink/?linkid=870105) used to provision Skype Room Systems v2 accounts.
  
## <a name="see-also"></a>Vea también

#### 

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)
  
[Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)
  
[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Licencias complementarias de Skype Empresarial](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

