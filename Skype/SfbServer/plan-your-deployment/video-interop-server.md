---
title: Planear el servidor de interoperabilidad de vídeo en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumen: Revise este tema mientras planea la integración de Skype empresarial Server con dispositivos de teleconferencia de terceros.'
ms.openlocfilehash: 5531fd60cc2aa28202903fcc4392fe7830bcdfa0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684193"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planear el servidor de interoperabilidad de vídeo en Skype empresarial Server
 
**Resumen:** Revise este tema mientras planea la integración de Skype empresarial Server con dispositivos de teleconferencia de terceros.
  
Ahora, Skype empresarial Server le permite integrarse con determinadas soluciones de VTC (sistema de teleconferencia de video) de terceros. El nuevo rol de servidor que permite esta interoperabilidad de videoconferencia es el servidor de interoperabilidad de video (VIS), que actualmente está implementado como un rol de servidor independiente disponible solo para las instalaciones locales. Una acción de VIS es un intermediario entre un sistema de teleconferencia de terceros y una implementación de Skype empresarial Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg. Consulte este artículo para determinar si usar esta característica en la instalación de Skype empresarial Server.
  
## <a name="device-interoperability"></a>Interoperabilidad de dispositivos

La interoperación se ha probado y es compatible con Cisco VTCs al registrarse con Cisco Unified Communications Manager (CallManager, o CUCM) versión 10,5 y los troncos TCP SIP establecidos entre CUCM y el VIS.
  
Los VTC actualmente compatibles son:
  
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
>  Cisco software Release TC 7.0.0 o posteriores es necesario en estos sistemas de integración con Skype empresarial Server para funcionar según lo esperado.
  
## <a name="sip-trunks"></a>Troncos SIP

El servidor de interoperabilidad de vídeo funciona en modo de tronco de SIP, donde el VTCs continúa registrándose con la infraestructura existente de Cisco, por ejemplo, Cisco Call Manager (CUCM). Se define un tronco de SIP de video entre CUCM y VIS, de modo que las llamadas se puedan enrutar entre los dos sistemas. Solo se admiten llamadas por el tronco del SIP desde el VTC a la VIS. Por lo tanto, VTCs puede llamar a una conferencia de Skype empresarial (marcando el número de teléfono asociado al operador automático llamar), pero no se puede arrastrar y colocar en la Conferencia.
  
![Diagrama de VIS en SE](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Características

El rol de servidor proporciona:
  
- Conversión entre los formatos H. 264 usados por sistemas de video de terceros y la implementación de Skype empresarial Server.
    
- Conversión de una sola secuencia de vídeo a una resolución determinada de un VTC en varias Simulcast de diferentes resoluciones para su uso en la implementación de Skype empresarial Server. Estas transmisiones se pueden enviar a AVMCU y, a continuación, a puntos de conexión de Skype empresarial Server y otros sistemas de vídeo que hayan solicitado diferentes resoluciones. Esta conversión también se usa cuando el sistema de videollamadas de terceros está involucrado en una llamada en Conferencia de Skype empresarial A/V. Una vez que se alcance el límite de transcodificación en un servidor concreto, las siguientes solicitudes de resoluciones distintas solo recibirán una secuencia con la resolución más baja. 
    
- Compatibilidad con un tronco de video SIP entre la puerta de enlace de CUCM y un servidor de interoperabilidad de vídeo de Skype empresarial Server. VTCs continuar con el registro con la puerta de enlace de Cisco e iniciar llamadas a la implementación de Skype empresarial a través de la puerta de enlace. Las llamadas se enrutan desde la puerta de enlace al servidor de interoperabilidad de vídeo de Skype empresarial a través del tronco del SIP de video.
    
- Soporte para un usuario en una sala de conferencias con un sistema de vídeo admitido para llamar desde ese sistema a fin de unirse a una conferencia abierta o cerrada. Esta llamada atravesará el tronco SIP de vídeo.
    
- Soporte técnico para un usuario en una sala de conferencias con un sistema de vídeo compatible para llamar a un cliente de Skype empresarial. Esta llamada atravesará el tronco SIP.
    
- Compatibilidad con el control de llamada MID desde el lado del servidor de Skype empresarial o el sistema de VTC compatible para las llamadas de punto a punto y multipunto, como desactivar audio/reactivar audio, pausar/reanudar video, bloquear video y llamada en espera o deshacer.
    
## <a name="known-limitations"></a>Limitaciones conocidas

Este rol de servidor tiene las siguientes limitaciones:
  
- No se admiten llamadas nuevas desde la implementación de Skype empresarial a la VTCs sobre el tronco del SIP de video. . Esto significa que solo se admiten las nuevas llamadas de VTCs a la implementación de Skype empresarial a través del tronco del SIP de video. La presencia del sistema de video compatible no estará disponible a través del tronco de video SIP hacia el VIS. 
    
- Solo un grupo de servidores VIS independiente será compatible con el modo de tronco SIP de vídeo.
    
-  Para las comunicaciones entre el VTC y el VIS por medio del tronco SIP de vídeo, TLS + SRTP o TCP + RTP serán compatibles.
    
- El uso compartido de aplicaciones no es compatible. Un usuario de Skype empresarial en la sala de conferencias debe unirse a la Conferencia de Skype empresarial (a través de un equipo portátil, por ejemplo) y mostrar las pantallas de uso compartido de aplicaciones en uno de los monitores gratis de la sala de conferencias no asociada con el VTC.
    
- La capacidad de un VTC de unirse a una reunión federada por medio del VIS no es compatible.
    
- La capacidad de un VTC de unirse a una reunión en línea por medio del VIS no es compatible.
    
- Las llamadas desde un VTC a la RTC por medio de un VIS no son compatibles.
    
- Las llamadas desde la RTC a un VTC por medio de un VIS no son compatibles.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resistencia
<a name="resiliency"> </a>

El VIS admite llamadas entrantes desde CUCM realizadas por medio de un tronco SIP de vídeo. Es posible perder la conectividad del canal de subida o de bajada, de modo que considere ambas posibilidades para una resistencia sólida:
  
1. **Failover de bloque Vis** Si el grupo VIS principal al que apunta la puerta de enlace de vídeo está desactivado, la recuperación es posible si la puerta de enlace de vídeo tiene troncos definidos para dos (o más) bloques VIS. Si la puerta de enlace de vídeo determina que no puede realizar llamadas al grupo de servidores VIS principal, simplemente, redirige las llamadas a un grupo de servidores VIS secundario.
    
     ![Diagrama de recuperación por error de grupo de VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Una determinada piscina puede tener troncos para varias puertas de enlace, pero normalmente una puerta de enlace determinada no puede tener troncos de varias agrupaciones VIS, por lo que es necesario realizar un truco para admitir este failover: defina 2 FDQNs en DNS que se resuelvan en la misma dirección IP de una puerta de enlace de vídeo. Este truco consiste en definir 2 FDQN en DNS que se resuelvan en la misma dirección IP de una puerta de enlace de vídeo. Represente cada FQDN como una puerta de enlace de vídeo independiente en el documento de topología, donde cada puerta de enlace de vídeo tiene un tronco a un grupo de servidores VIS diferente y, de esta forma, la recuperación estará disponible (si se utiliza TLS, los nombres varios tendrán que estar en la SAN del certificado de la puerta de enlace de vídeo).
    
    > [!NOTE]
    > El VIS solo permite las llamadas entrantes de puertas de enlace configuradas en el documento de topología. 
  
2. **Conmutación por error front-end** Si un grupo de seguridad recibe una llamada de CUCM pero no puede llegar a su principal registrador de saltos o grupo de servidores front-end, las llamadas se enrutan a una agrupación front end frontal.
    
     ![Diagrama de recuperación por error del front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    El servicio VIS realiza un seguimiento del estado de su grupo principal front-end y de la copia de seguridad de su grupo front end (la configuración se encuentra en la configuración de copia de seguridad del servicio registrar en el documento de topología). Envía las encuestas de opciones una vez por minuto a los dos grupos, y si hay cinco errores consecutivos, el botón supone que un grupo de servidores front-end determinado está desactivado. Si el grupo de servidores front-end principal se marca como desactivado y hay una copia de seguridad configurada disponible, el envía las llamadas desde la puerta de enlace a la agrupación front end. Una vez que el grupo de servidores front-end principal vuelve, el se reanudará con el grupo de servidores front-end primario para las llamadas nuevas.
    
    Asimismo, el VIS implementará un temporizador de 10 segundos para las llamadas desde el tronco SIP de vídeo. Si el grupo de servidores front-end principal del próximo salto se usó para una llamada desde el tronco del SIP de video, y el grupo de servidores front-end primario del próximo salto no respondió con algún mensaje SIP (incluyendo 100 intentando) en la invitación que se le envió dentro de este temporizador, el proxy de salto siguiente para la llamada hould se puede probar si está configurado. 
    
    > [!NOTE]
    > Si el próximo salto de copia de seguridad se intentó primero, luego, no se intentará el principal. 
  
    El administrador también puede usar el comando de conmutación por error de Windows PowerShell para forzar a que el VIS utilice el grupo de servidores front-end de copia de seguridad, por ejemplo, cuando se precisa realizar el mantenimiento en el grupo de servidores front-end principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistencia de troncos de vídeo y voz a la puerta de enlace del mismo nivel
<a name="resiliency"> </a>

Skype empresarial Server permite que los troncos SIP de voz y video usen el mismo interlocutor de puerta de enlace. Así, la misma implementación de CUCM podría tener troncos de SIP de voz para el servidor de mediación y los troncos de SIP de video.
  
- Una puerta de enlace RTC necesitará definirse con un FQDN en particular en el documento de topología para los troncos SIP de voz.
    
- El elemento del mismo nivel para la puerta de enlace RTC será el servidor de mediación.
    
- Si es necesario, se pueden definir varios troncos de voz, desde una puerta de enlace RTC hasta varios grupos de servidores de mediación.
    
- Será preciso definir una puerta de enlace de vídeo en el documento de topología para el tronco SIP de vídeo con el mismo FQDN que para la puerta de enlace RTC.
    
- El elemento del mismo nivel para la puerta de enlace de vídeo será el VIS.
    
- Se puede definir un tronco de vídeo único desde una puerta de enlace de vídeo a un grupo VIS en concreto.
    
- CUCM necesitará configurarse para enrutar correctamente las llamadas a través del tronco de voz en comparación con el tronco de video. Por ejemplo, se puede usar un prefijo de marca especial al marcar desde la VTC. CUCM podría asociar este prefijo de marcado con las llamadas a VIS, y las reglas de traducción apropiadas eliminarían este prefijo de la invitación SIP a VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistencia del VIS en la versión de Skype Empresarial con las versiones anteriores de Lync
<a name="resiliency"> </a>

VIS solo se puede implementar como parte de la implementación de Skype empresarial. Puede interoperar con conferencias y clientes de Lync 2013 que forman parte de una implementación existente; en esos casos, el conjunto de contabilidad necesitará formar parte de una implementación de Skype empresarial que incluya un grupo registrador/FE que es el próximo salto para el conjunto de conexiones.
  
El VIS no es compatible con la transcodificación entre RTV y H.264. No hay interoperabilidad de vídeo entre los clientes anteriores a Lync 2013 y los participantes de VTC en una conferencia.
  
Al disponer de clientes anteriores a Lync 2013 en una conferencia, los clientes móviles llevarán a cabo el envío por medio de RTV, por lo que los VTC no recibirán vídeo cuando el cliente móvil se convierta en el orador dominante.
  
Para que Lync 2013 funcione correctamente con un VIS que sea parte de una implementación de Skype Empresarial, Lync 2013 necesita que se aplique el CU correspondiente para actualizar el cliente de Lync 2013, CAA y para que AVMCU funcione con el VIS.
  
La interoperabilidad del VIS con Lync 2013 y los clientes de escritorio de Skype Empresarial se ha probado y es compatible.
  
Interoperabilidad de VIS con otros usuarios que no sean de escritorio (Android, iPad, iPhone, Windows Phone, LMX, etc.) Los clientes de Skype empresarial que se encuentran disponibles en el establecimiento de aplicaciones correspondientes en el momento de la versión de VIS se han probado y son compatibles.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperación de la pérdida de paquetes por medio de FEC
<a name="resiliency"> </a>

A fin de ayudar en la recuperación de la pérdida de paquetes, puede activar FEC. Cuando se activa, se utilizará un 50 % más de ancho de banda de vídeo en el trayecto del VIS al VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costes de transcodificación y ajustes del tamaño del VIS
<a name="resiliency"> </a>

La transcodificación de las videollamadas de Cisco VTC a varias transmisiones de Simulcast usa la capacidad de la CPU. Aproximadamente 16 VTCs pueden tener su vídeo transcodificado (suponiendo que una secuencia de vídeo 720p de cada VTC está transcodificada en 3 transmisiones de Simulcast independientes en 720p, 360p y 180P) en un único VIS de ejecución en el equivalente de la plataforma FE de Lync 2013. Si la transcodificación está desactivada, se guardará en VIS CPU. Sin embargo, la imagen de video solicitada con VIS desde el VTC será la resolución común más baja para satisfacer a todos los receptores en el lado de Skype empresarial. Tenga en cuenta que, incluso con la transcodificación desactivada, la transcodificación puede activarse cuando los clientes de Skype empresarial solicitan ciertas resoluciones bajas que VTCs no puede enviar.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribución de llamadas desde la puerta de enlace de vídeo al VIS
<a name="resiliency"> </a>

La distribución se realiza por medio de uno de los métodos de distribución de CUCM:
  
- Al usar DNS de manera dinámica.
    
- En CUCM, puede definir troncos individuales, donde cada tronco finaliza en un servidor diferente en el grupo de servidores VIS. CUCM también redirigirá las llamadas a través de troncos diferentes.
    
## <a name="no-hybrid-interoperability"></a>Sin interoperabilidad híbrida
<a name="resiliency"> </a>

La compatibilidad para que los VTC se unan a reuniones en línea por medio del VIS local no es parte de Skype Empresarial.
  
## <a name="no-federation-support"></a>Sin compatibilidad de federación
<a name="resiliency"> </a>

La compatibilidad para que los VTC se unan a reuniones federadas por medio del VIS no es parte de Skype Empresarial.
  
## <a name="see-also"></a>Vea también
<a name="resiliency"> </a>

[Implementar el servidor de interoperabilidad de vídeo en Skype empresarial Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
