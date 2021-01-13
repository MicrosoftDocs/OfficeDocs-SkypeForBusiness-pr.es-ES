---
title: Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumen: revise este tema al planear la integración de Skype Empresarial Server con dispositivos de teleconferencia de terceros.'
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831950"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server
 
**Resumen:** Revise este tema al planear la integración de Skype Empresarial Server con dispositivos de teleconferencia de terceros.
  
Skype Empresarial Server ahora le permite integrarse con determinadas soluciones VTC (Sistema de teleconferencia de vídeo) de terceros. El nuevo rol de servidor que habilita esta interoperabilidad de videoconferencia es el servidor de interoperabilidad de vídeo (VIS), que actualmente se implementa como un rol de servidor independiente disponible solo para instalaciones locales. Un VIS actúa como intermediario entre un sistema de teleconferencia de terceros y una implementación de Skype Empresarial Server. Para esta versión, VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco/Tandberg. Revise este artículo para determinar si va a usar esta característica en la instalación de Skype Empresarial Server.
  
## <a name="device-interoperability"></a>Interoperabilidad de dispositivos

La interoperación se prueba y admite con los VTC de Cisco que se registran con Cisco Unified Communications Manager (CallManager, o CUCM) versión 10.5 y con troncos TCP SIP configurados entre CUCM y el VIS.
  
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

El servidor de interoperabilidad de vídeo funciona en modo de tronco SIP, donde los VTC se siguen registrando con la infraestructura de Cisco existente, por ejemplo, Cisco Call Manager (CUCM). Un tronco SIP de vídeo se define entre CUCM y el VIS para que las llamadas se puedan enrutar entre los dos sistemas. Solo se admiten las llamadas a través del tronco SIP desde VTC al VIS. Por lo tanto, los VTC pueden llamar a una conferencia de Skype Empresarial (marcando el número de teléfono asociado con el operador automático de llamadas), pero no se pueden arrastrar ni descartar en la conferencia.
  
![Diagrama de VIS en SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Características

Este rol de servidor proporciona:
  
- Conversión entre los formatos H.264 usados por sistemas de vídeo de terceros y la implementación de Skype Empresarial Server.
    
- Conversión de una única secuencia de vídeo en una resolución determinada de un VTC en varias secuencias de difusión simultánea de diferentes resoluciones para su uso en la implementación de Skype Empresarial Server. Estas secuencias se pueden enviar a la AVMCU y, a continuación, a los puntos de conexión de Skype Empresarial Server y a otros sistemas de vídeo que han solicitado diferentes resoluciones. Esta conversión también se usa cuando el sistema de vídeo de terceros participa en una llamada de conferencia A/V de Skype Empresarial. Una vez que se alcanza el límite de transcodificación en un servidor VIS concreto, las solicitudes siguientes para diferentes resoluciones solo recibirán una secuencia con la resolución más baja. 
    
- Compatibilidad con un tronco SIP de vídeo entre la puerta de enlace CUCM y un servidor de interoperabilidad de vídeo de Skype Empresarial Server; Los VTC se siguen registrando con la puerta de enlace de Cisco e inician llamadas a la implementación de Skype Empresarial a través de la puerta de enlace. Las llamadas se enrutar desde la puerta de enlace al servidor de interoperabilidad de vídeo de Skype Empresarial a través del tronco SIP de vídeo.
    
- Compatibilidad para que un usuario de una sala de conferencias con un sistema de vídeo compatible marque desde ese sistema para unirse a una conferencia abierta o cerrada. Esta llamada atravesará el tronco SIP de vídeo.
    
- Soporte técnico para un usuario en una sala de conferencias con un sistema de vídeo compatible para llamar a un cliente de Skype Empresarial. La llamada atravesará el tronco SIP.
    
- Compatibilidad con el control de llamadas medias desde el lado de Skype Empresarial Server o desde el sistema VTC compatible para llamadas de punto a punto y multipunto, como audio de silenciar/desactivar, pausar/reanudar vídeo, bloquear vídeo y mantener/descontener la llamada.
    
## <a name="known-limitations"></a>Limitaciones conocidas

Este rol de servidor tiene las siguientes limitaciones:
  
- No se admiten nuevas llamadas desde la implementación de Skype Empresarial a los VTC a través del tronco SIP de vídeo. . Esto significa que solo se admiten llamadas nuevas desde los VTC a la implementación de Skype Empresarial a través del tronco SIP de vídeo. La presencia del sistema de vídeo compatible no estará disponible a través del tronco SIP de vídeo al VIS. 
    
- Solo se admite un grupo de servidores VIS independiente para el modo de tronco SIP de vídeo.
    
-  TLS + SRTP o TCP + RTP serán compatibles con las comunicaciones entre VTC y VIS a través del tronco SIP de vídeo.
    
- No se admite el uso compartido de aplicaciones. Un usuario de Skype Empresarial en la sala de conferencias debe unirse a la conferencia de Skype Empresarial (por ejemplo, a través de un portátil) y mostrar las pantallas de uso compartido de aplicaciones en uno de los monitores gratuitos de la sala de conferencias que no están asociados con los VTC.
    
- No se admite la capacidad de un VTC para unirse a una reunión federada a través de VIS.
    
- No se admite la capacidad de un VTC para unirse a una reunión en línea a través de VIS.
    
- No se admiten las llamadas desde un VTC a la RTC a través de VIS.
    
- No se admiten las llamadas desde la RTC a un VTC a través de VIS.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resistencia
<a name="resiliency"> </a>

El VIS admite llamadas entrantes de CUCM que se llevan a través de un tronco SIP de vídeo. Es posible perder la conectividad en sentido ascendente o descendente, por lo que para una resistencia sólida, tenga en cuenta ambas posibilidades:
  
1. **Conmutación por error del grupo vis** Si el grupo de servidores VIS principal al que apunta la puerta de enlace de vídeo está abajo, la recuperación es posible si la puerta de enlace de vídeo ha definido troncos a dos (o más) grupos de servidores VIS. Si la puerta de enlace de vídeo determina que no puede realizar llamadas al grupo de servidores VIS principal, simplemente enruta las llamadas a un grupo de servidores VIS secundario.
    
     ![Diagrama de conmutación por error del grupo vis](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un grupo de servidores VIS determinado puede tener troncos a varias puertas de enlace, pero normalmente una puerta de enlace determinada no puede tener troncos a varios grupos de servidores VIS, por lo que es necesario realizar un trucos para admitir esta conmutación por error: definir 2 FDQN en DNS que se resuelven en la misma dirección IP de una puerta de enlace de vídeo. Represente cada FQDN como una puerta de enlace de vídeo independiente en el documento de topología donde cada puerta de enlace de vídeo tiene un tronco a un grupo de VIS diferente y ahora es posible la recuperación. (Si se usa TLS, los nombres múltiples tendrán que estar en el SAN del certificado de puerta de enlace de vídeo).
    
    > [!NOTE]
    > VIS solo permite llamadas entrantes desde puertas de enlace configuradas en el documento de topología. 
  
2. **Conmutación por error front-end** Si un grupo de servidores VIS recibe una llamada de CUCM pero no puede alcanzar su registrador o grupo de servidores front-end principal del próximo salto, las llamadas se enrutar a un grupo de servidores front-end de reserva.
    
     ![Diagrama de conmutación por error front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    El VIS realizará un seguimiento del estado de su grupo de servidores front-end principal y su grupo de servidores front-end de reserva (la configuración se encuentra en la configuración de copia de seguridad del servicio registrador en el documento de topología). Envía sondeos de opciones una vez al minuto a ambos grupos de servidores y, si hay cinco errores consecutivos, el VIS asume que un grupo de servidores front-end determinado está abajo. Si el grupo de servidores front-end principal está marcado como no disponible y hay una copia de seguridad configurada disponible, el VIS envía nuevas llamadas desde la puerta de enlace al grupo de servidores front-end de copia de seguridad. Una vez que el grupo de servidores front-end principal vuelva, el VIS reanudará el uso del grupo de servidores front-end principal para nuevas llamadas.
    
    El VIS también implementará un temporizador de 10 segundos para las llamadas desde el tronco SIP de vídeo. Si el grupo de servidores front-end del próximo salto principal se usó para una llamada desde el tronco SIP de vídeo y el grupo de servidores front-end del próximo salto principal no respondió con algún mensaje SIP (incluido 100 Intentos) a la invitación enviada dentro de este valor del temporizador, el proxy de próximo salto de reserva para la llamada debe intentarse si está configurado. 
    
    > [!NOTE]
    > Si el próximo salto de copia de seguridad se intentó primero, el principal no se probará a continuación. 
  
    El administrador también podría usar el comando de conmutación por error de Windows PowerShell para forzar al VIS a usar el grupo de servidores front-end de copia de seguridad, por ejemplo, cuando se debe realizar el mantenimiento en el grupo de servidores front-end principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistencia de troncos de voz y vídeo en el mismo punto de puerta de enlace
<a name="resiliency"> </a>

Skype Empresarial Server admite que los troncos SIP de voz y vídeo usen la misma puerta de enlace del mismo nivel. Por lo tanto, la misma implementación de CUCM podría tener troncos SIP de voz al servidor de mediación y troncos SIP de vídeo a VIS.
  
- Una puerta de enlace RTC deberá definirse con un FQDN determinado en el documento de topología para los troncos SIP de voz.
    
- El sistema del mismo nivel que la puerta de enlace RTC será el servidor de mediación.
    
- Si es necesario, se pueden definir varios troncos de voz que se extienden desde una puerta de enlace RTC a varios grupos de servidores de mediación.
    
- Deberá definirse una puerta de enlace de vídeo en el documento de topología para el tronco SIP de vídeo con el mismo FQDN que para la puerta de enlace RTC.
    
- El sistema del mismo nivel que la puerta de enlace de vídeo será VIS.
    
- Un único tronco de vídeo se puede definir desde una puerta de enlace de vídeo a un grupo vis determinado.
    
- CUCM deberá configurarse para enrutar correctamente las llamadas a través del tronco de voz frente al tronco de vídeo. Por ejemplo, se podría usar un prefijo de marcado especial al marcar desde VTC; CUCM podría asociar este prefijo de marcado con llamadas al VIS y las reglas de conversión apropiadas quitarían este prefijo del SIP Invite to VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistencia de VIS en la versión de Skype Empresarial con versiones anteriores de Lync
<a name="resiliency"> </a>

El VIS solo se puede implementar como parte de la implementación de Skype Empresarial. Puede interoperar con conferencias y clientes de Lync 2013 que forman parte de una implementación existente; En esos casos, el grupo de servidores VIS tendrá que formar parte de una implementación de Skype Empresarial que incluya un grupo de registrador/FE que sea el próximo salto del grupo vis.
  
VIS no admite la transcodificación entre RTV y H.264. No hay interoperabilidad de vídeo entre clientes anteriores a Lync 2013 y participantes de VTC en una conferencia.
  
Tener clientes anteriores a Lync 2013 en una conferencia hará que los clientes móviles envíen con RTV, lo que provocará que los VTC no reciban ningún vídeo cuando el cliente móvil se convierta en el orador dominante.
  
Para que Lync 2013 funcione correctamente con el VIS que forma parte de una implementación de Skype Empresarial, Lync 2013 necesita que se aplique la CU adecuada que actualice el cliente de Lync 2013, CAA y AVMCU para trabajar con VIS.
  
Se ha probado y se admite la interoperabilidad del VIS con clientes de escritorio de Lync 2013 y Skype Empresarial.
  
Interoperabilidad del VIS con dispositivos que no son de escritorio (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Los clientes de Skype Empresarial disponibles en la Tienda de aplicaciones aplicable en el momento de la versión vis se han probado y son compatibles.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperación de pérdida de paquetes a través de FEC
<a name="resiliency"> </a>

FEC puede estar activado para ayudar en la recuperación de la pérdida de paquetes. Si está activado, se usará un 50 % más de ancho de banda de vídeo en la dirección vis a VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costos de tamaño y transcodificación vis
<a name="resiliency"> </a>

La transcodificación de las secuencias de vídeo únicas de Cisco VTC a varias secuencias de difusión simultánea usa capacidad de CPU. Aproximadamente 16 VTC pueden tener su transcodificación de vídeo (suponiendo que una secuencia de vídeo de 720p de cada VTC se transcodificará en 3 secuencias de difusión simultánea independientes a 720p, 360p y 180p) en un único VIS que se ejecute en el equivalente de la plataforma FE recomendada de Lync 2013. Si la transcodificación está desactivada, se ahorrará en la CPU VIS. Sin embargo, la imagen de vídeo solicitada por el VIS de los VTC será la resolución común más baja para satisfacer todos los receptores del lado de Skype Empresarial. Tenga en cuenta que, incluso con la transcodificación desactivada, la transcodificación puede activarse cuando los clientes de Skype Empresarial soliciten determinadas resoluciones baja que los VTC no pueden enviar.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribución de llamadas desde la puerta de enlace de vídeo al VIS
<a name="resiliency"> </a>

La distribución se realiza a través de uno de los mecanismos de distribución de CUCM:
  
- Uso dinámico de DNS.
    
- En CUCM, puede definir troncos individuales, donde cada tronco termina en un servidor diferente del grupo de servidores VIS. CUCM enruta las llamadas a través de los distintos troncos.
    
## <a name="no-hybrid-interoperability"></a>Sin interoperabilidad híbrida
<a name="resiliency"> </a>

La compatibilidad con VTC que se unen a reuniones en línea a través del VIS local no forma parte de Skype Empresarial.
  
## <a name="no-federation-support"></a>Sin compatibilidad de federación
<a name="resiliency"> </a>

La compatibilidad con VTC que se unen a reuniones federadas a través de VIS no forma parte de Skype Empresarial.
  
## <a name="see-also"></a>Ver también
<a name="resiliency"> </a>

[Implementar el servidor de interoperabilidad de vídeo en Skype Empresarial Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
