---
title: Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumen: revise este tema al planear la integración de Skype Empresarial Server con dispositivos de teleconferencia de terceros.'
ms.openlocfilehash: 34afa051513ea2ebef60213fbc8c1a650bfec199
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749919"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server
 
**Resumen:** Revise este tema mientras planea integrar Skype Empresarial Server con dispositivos de teleconferencia de terceros.
  
Skype Empresarial Server permite integrar con determinadas soluciones VTC (Sistema de teleconferencia de vídeo) de terceros. El nuevo rol de servidor que habilita esta interoperabilidad de videoconferencia es el servidor de interoperabilidad de vídeo (VIS), que actualmente se implementa como un rol de servidor independiente disponible solo para instalaciones locales. Un VIS actúa como intermediario entre un sistema de teleconferencia de terceros y una Skype Empresarial Server implementación. Para esta versión, VIS se centra en la interoperabilidad con sistemas de vídeo de Cisco/Tandberg. Revise este artículo para determinar si se va a usar esta característica en la Skype Empresarial Server instalación.
  
## <a name="device-interoperability"></a>Interoperabilidad de dispositivos

La interoperación se prueba y admite con los VTC de Cisco que se registran con los troncos SIP TCP y CUCM del Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM) configurados entre CUCM y el VIS.
  
Los VTC compatibles actualmente son:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  La versión de software de Cisco TC7.0.0 o posterior es necesaria en estos sistemas para que la integración con Skype Empresarial Server funcione según lo esperado.
  
## <a name="sip-trunks"></a>Troncos SIP

El servidor de interoperabilidad de vídeo funciona en modo troncal SIP, donde los VTC siguen registrándose con la infraestructura de Cisco existente, por ejemplo, Cisco Call Manager (CUCM). Se define un tronco SIP de vídeo entre CUCM y el VIS para que las llamadas se puedan enrutar entre los dos sistemas. Solo se admiten llamadas a través del tronco SIP desde VTC al VIS. Por lo tanto, los VTC pueden llamar a una conferencia de Skype Empresarial (marcando el número de teléfono asociado con el operador automatizado de llamadas), pero no se pueden arrastrar y dejar caer en la conferencia.
  
![Diagrama de VIS en SfB.](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Características

Este rol de servidor proporciona:
  
- Conversión entre los formatos H.264 usados por los sistemas de vídeo de terceros y la implementación Skype Empresarial Server terceros.
    
- Conversión de una única secuencia de vídeo a una resolución determinada de un VTC en varias secuencias de difusión simultánea de diferentes resoluciones para su uso en la Skype Empresarial Server implementación. Estas secuencias se pueden enviar a la AVMCU y, a continuación, a Skype Empresarial Server extremos y otros sistemas de vídeo que han solicitado diferentes resoluciones. Esta conversión también se usa cuando el sistema de vídeo de terceros está implicado en una Skype Empresarial conferencia A/V. Una vez alcanzado el límite de transcodificación en un servidor VIS determinado, las solicitudes siguientes para diferentes resoluciones solo recibirán una secuencia con la resolución más baja. 
    
- Compatibilidad con un tronco SIP de vídeo entre la puerta de enlace CUCM y un servidor Skype Empresarial Server interoperabilidad de vídeo; Los VTC siguen registrándose con la puerta de enlace de Cisco e iniciando llamadas a la Skype Empresarial a través de la puerta de enlace. Las llamadas se enrutan desde la puerta de enlace al servidor Skype Empresarial interoperabilidad de vídeo a través del tronco SIP de vídeo.
    
- Compatibilidad para que un usuario de una sala de conferencias con un sistema de vídeo compatible marque desde ese sistema para unirse a una conferencia abierta o cerrada. Esta llamada atravesará el tronco SIP de vídeo.
    
- Compatibilidad con un usuario en una sala de conferencias con un sistema de vídeo compatible para llamar a un Skype Empresarial cliente. La llamada atravesará el tronco SIP.
    
- Compatibilidad con el control de llamadas medias desde el lado Skype Empresarial Server o desde el sistema VTC compatible para llamadas de punto a punto y multipunto, incluido el audio mudo/no silenciado, el vídeo de pausa/reanudación, el vídeo de bloqueo y la llamada de retención y desuso.
    
## <a name="known-limitations"></a>Limitaciones conocidas

Este rol de servidor tiene las siguientes limitaciones:
  
- No se admiten nuevas llamadas Skype Empresarial implementación a los VTC a través del tronco SIP de vídeo. . Esto significa que solo se admiten llamadas nuevas de los VTC en la implementación Skype Empresarial a través del tronco SIP de vídeo. La presencia del sistema de vídeo compatible no estará disponible en el tronco SIP de vídeo en el VIS. 
    
- Solo se admite un grupo de servidores VIS independiente para el modo de tronco SIP de vídeo.
    
-  TLS + SRTP o TCP + RTP se admiten para las comunicaciones entre VTC y VIS a través del tronco SIP de vídeo.
    
- No se admite el uso compartido de aplicaciones. Un usuario Skype Empresarial en la sala de conferencias debe unirse a la conferencia de Skype Empresarial (por ejemplo, a través de un portátil) y mostrar las pantallas de uso compartido de aplicaciones en uno de los monitores gratuitos de la sala de conferencias que no están asociados con VTC.
    
- No se admite la posibilidad de que un VTC se una a una reunión federada a través de VIS.
    
- No se admite la posibilidad de que un VTC se una a una reunión en línea a través de VIS.
    
- No se admiten llamadas desde un VTC a la RTC a través de VIS.
    
- No se admiten llamadas desde la RTC a un VTC a través de VIS.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resistencia
<a name="resiliency"> </a>

El VIS admite llamadas entrantes de un CUCM que se llevan a través de un tronco SIP de vídeo. Es posible perder la conectividad en sentido ascendente o descendente, por lo que para una resistencia sólida, tenga en cuenta ambas posibilidades:
  
1. **Conmutación por error del grupo vis** Si el grupo de VIS principal al que apunta la puerta de enlace de vídeo está abajo, la recuperación es posible si la puerta de enlace de vídeo ha definido troncos en dos (o más) grupos de servidores VIS. Si la puerta de enlace de vídeo determina que no puede realizar llamadas al grupo vis principal, simplemente enruta las llamadas a un grupo de VIS secundario.
    
     ![Diagrama de conmutación por error del grupo vis.](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un grupo de vis determinado puede tener troncos para varias puertas de enlace, pero normalmente una puerta de enlace determinada no puede tener troncos en varios grupos de servidores VIS, por lo que es necesario realizar un truco para admitir esta conmutación por error: definir 2 FDQN en DNS que se resuelven en la misma dirección IP de una puerta de enlace de vídeo. Represente cada FQDN como una puerta de enlace de vídeo independiente en el documento de topología donde cada puerta de enlace de vídeo tiene un tronco a un grupo de VIS diferente y ahora es posible la recuperación. (Si se usa TLS, los varios nombres tendrán que estar en el SAN del certificado de puerta de enlace de vídeo).
    
    > [!NOTE]
    > VIS solo permite llamadas entrantes desde puertas de enlace configuradas en el documento de topología. 
  
2. **Conmutación por error front-end** Si un grupo de servidores VIS recibe una llamada de CUCM pero no puede llegar a su registrador de próximo salto principal o grupo de servidores front-end, las llamadas se enruta a un grupo de servidores front-end de copia de seguridad.
    
     ![Diagrama de conmutación por error front-end.](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    El VIS realizará un seguimiento del estado de su grupo de servidores front-end principal y su grupo de servidores front-end de copia de seguridad (la configuración se encuentra en la configuración de copia de seguridad del servicio registrador en el documento de topología). Envía sondeos de opciones una vez al minuto a ambos grupos de servidores y, si hay cinco errores consecutivos, el VIS supone que un grupo de servidores front-end determinado está abajo. Si el grupo de servidores front-end principal está marcado como hacia abajo y hay una copia de seguridad configurada disponible, el VIS envía nuevas llamadas desde la puerta de enlace al grupo de servidores front-end de copia de seguridad. Una vez que vuelva el grupo de servidores front-end principal, el VIS se reanudará con el grupo de servidores front-end principal para las llamadas nuevas.
    
    El VIS también implementará un temporizador de 10 segundos para llamadas desde el tronco SIP de vídeo. Si el grupo de servidores front-end principal del próximo salto se usó para una llamada desde el tronco SIP de vídeo y el grupo de servidores front-end principal del próximo salto no respondió con algún mensaje SIP (incluido 100 Trying) a la invitación que se le envió dentro de este valor del temporizador, el proxy de copia de seguridad del próximo salto de la llamada debe probarse si está configurado. 
    
    > [!NOTE]
    > Si la copia de seguridad del próximo salto se intentó primero, la principal no se probará a continuación. 
  
    El administrador también podría usar el comando de conmutación por error Windows PowerShell para forzar a VIS a usar el grupo de servidores front-end de copia de seguridad, por ejemplo, cuando el mantenimiento debe realizarse en el grupo de servidores front-end principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistencia de troncos de voz y vídeo en el mismo punto de puerta de enlace
<a name="resiliency"> </a>

Skype Empresarial Server admite que los troncos SIP de voz y vídeo usen el mismo punto de puerta de enlace. Por lo tanto, la misma implementación CUCM podría tener troncos SIP de voz en el servidor de mediación y troncos SIP de vídeo a VIS.
  
- Una puerta de enlace RTC tendrá que definirse con un FQDN determinado en el documento de topología para los troncos SIP de voz.
    
- El punto de la puerta de enlace RTC será el servidor de mediación.
    
- Se pueden definir varios troncos de voz que abarcan desde una puerta de enlace RTC a varios grupos de servidores de mediación si es necesario.
    
- Una puerta de enlace de vídeo tendrá que definirse en el documento de topología para el tronco SIP de vídeo con el mismo FQDN que para la puerta de enlace RTC.
    
- El punto de la puerta de enlace de vídeo será VIS.
    
- Un único tronco de vídeo se puede definir desde una puerta de enlace de vídeo a un grupo vis determinado.
    
- CUCM tendrá que configurarse para enrutar correctamente las llamadas a través del tronco de voz frente al tronco de vídeo. Por ejemplo, se podría usar un prefijo de marcado especial al marcar desde VTC; CUCM podría asociar este prefijo de marcado con llamadas a VIS y las reglas de traducción apropiadas quitarían este prefijo del SIP Invite to VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistencia de VIS en la versión Skype Empresarial con versiones anteriores de Lync
<a name="resiliency"> </a>

Vis solo se puede implementar como parte de Skype Empresarial implementación. Puede interoperar con conferencias y clientes de Lync 2013 que forman parte de una implementación existente; En esos casos, el grupo de VIS tendrá que formar parte de una implementación de Skype Empresarial que incluya un grupo de registradores/FE que sea el próximo salto para el grupo vis.
  
VIS no admite la transcodificación entre RTV y H.264. No hay interoperabilidad de vídeo entre clientes anteriores a Lync 2013 y participantes de VTC en una conferencia.
  
Tener clientes anteriores a Lync 2013 en una conferencia hará que los clientes móviles envíen con RTV, lo que provocará que los VTC no reciban ningún vídeo cuando el cliente móvil se convierta en el altavoz dominante.
  
Para que Lync 2013 funcione correctamente con VIS que forma parte de una implementación de Skype Empresarial, Lync 2013 necesita que se aplique la CU adecuada que actualice el cliente de Lync 2013, CAA y AVMCU para trabajar con VIS.
  
La interoperabilidad de VIS con Lync 2013 y Skype Empresarial de escritorio se ha probado y se admite.
  
Interoperabilidad de VIS con dispositivos que no son de escritorio (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype Empresarial clientes disponibles en la Tienda de aplicaciones aplicable en el momento de la versión vis se ha probado y se admite.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperación de pérdida de paquetes a través de FEC
<a name="resiliency"> </a>

FEC puede estar activado para ayudar en la recuperación de la pérdida de paquetes. Si está activado, se usará un 50 % más de ancho de banda de vídeo en la dirección VIS a VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costos de tamaño y transcodificación de VIS
<a name="resiliency"> </a>

La transcodificación de las secuencias de vídeo únicas desde Cisco VTC a varias secuencias de difusión simultánea usa capacidad de CPU. Aproximadamente 16 VTC pueden tener su vídeo transcodificado (suponiendo que una secuencia de vídeo de 720p de cada VTC se transcodifice en 3 secuencias de difusión simultánea independientes a 720p, 360p y 180p) en un único VIS que se ejecute en el equivalente de la plataforma FE recomendada de Lync 2013. Si transcodificación está desactivada, se ahorrará en la CPU VIS. Sin embargo, la imagen de vídeo solicitada por VIS desde VTC será la resolución común más baja para satisfacer todos los receptores del Skype Empresarial lado. Tenga en cuenta que incluso con la transcodificación desactivada, la transcodificación puede activarse cuando los Skype Empresarial solicitan determinadas resoluciones bajas que los VTC no pueden enviar.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribución de llamadas desde la puerta de enlace de vídeo a VIS
<a name="resiliency"> </a>

La distribución se realiza a través de uno de los mecanismos de distribución CUCM:
  
- Uso dinámico de DNS.
    
- En el lado CUCM, puede definir troncos individuales, donde cada tronco termina en un servidor diferente en el grupo vis. CUCM enruta las llamadas a través de los distintos troncos.
    
## <a name="no-hybrid-interoperability"></a>Sin interoperabilidad híbrida
<a name="resiliency"> </a>

La compatibilidad con VTC que se unen a reuniones en línea a través del VIS local no forma parte de Skype Empresarial.
  
## <a name="no-federation-support"></a>Sin compatibilidad con federación
<a name="resiliency"> </a>

La compatibilidad con VTC que se unen a reuniones federadas a través de VIS no forma parte de Skype Empresarial.
  
## <a name="see-also"></a>Consulte también
<a name="resiliency"> </a>

[Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
