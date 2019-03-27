---
title: Planeación de servidor de interoperabilidad vídeo en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumen: Revise este tema cuando planee integrar Skype para Business Server con los dispositivos de terceros teleconferencia.'
ms.openlocfilehash: 015f93496879e84c1959db7d6b46b765e0d286e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894255"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planeación de servidor de interoperabilidad vídeo en Skype para Business Server
 
**Resumen:** Revise este tema cuando planee integrar Skype para Business Server con los dispositivos de terceros teleconferencia.
  
Skype para Business Server ahora permite integrar con determinadas soluciones de terceros VTC (sistema de teleconferencia de vídeo). La nueva función de servidor que permite la interoperabilidad de esta conferencia de vídeo es el servidor de vídeo de interoperabilidad (VISIBLES), que actualmente se implementa como una función de servidor independientes disponible solo para instalaciones locales. Un respecto actúa como intermediario entre un sistema de videoconferencia de terceros y un Skype para la implementación de Business Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg. Revise este artículo para determinar si debe usar esta característica en su Skype para la instalación de Business Server.
  
## <a name="device-interoperability"></a>Interoperabilidad de dispositivos

Interoperación es probado y compatible con Cisco VTCs registrar con Cisco Unified Communications Manager (CallManager o CUCM) versión 10.5 y troncos SIP TCP configuración entre CUCM y el VIS
  
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
>  Software Cisco versión TC7.0.0 o por encima de es necesaria en estos sistemas para la integración con Skype para Business Server para que funcione como se esperaba.
  
## <a name="sip-trunks"></a>Troncos SIP

Las funciones de servidor de interoperabilidad de vídeo en el modo de tronco SIP, donde el VTCs continuarán para registrar con la infraestructura existente de Cisco - por ejemplo, el Administrador de llamadas de Cisco (CUCM). Se define un tronco SIP vídeo entre CUCM y la luz visible para que las llamadas se puedan enrutar entre los dos sistemas. Se admiten sólo las llamadas a través del tronco SIP desde el VTC a la respecto. Por lo tanto, VTCs puedan participar en una Skype para conferencia de negocios (marcando el número de teléfono asociado con el operador automático de llamadas), pero no se puede arrastrar y colocar en la conferencia.
  
![Diagrama de VIS en SE](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Características

El rol de servidor proporciona:
  
- Conversión entre los formatos H.264 utilizados por 3 sistemas de vídeo de terceros y la Skype para la implementación de Business Server.
    
- Conversión de una única secuencia de vídeo con una resolución determinada de un VTC en varias secuencias de simulación de distintas resoluciones para su uso en la Skype para la implementación de Business Server. Estas secuencias se pueden enviar a la AVMCU y, a continuación, en Skype para extremos de Business Server y otros sistemas de vídeo que han solicitado diferentes resoluciones. Esta conversión también se usa cuando el sistema de vídeo de otro fabricante está implicado en una Skype para la empresa A la llamada de conferencia A/v. Una vez que se alcanza el límite de transcodificación en un determinado servidor respecto, las solicitudes siguientes para diferentes resoluciones sólo recibirá un objeto stream con la resolución más baja. 
    
- Soporte técnico para un tronco SIP vídeo entre la puerta de enlace CUCM y un Skype para Business Server vídeo interoperabilidad Server; VTCs continuar registrarse con la puerta de enlace de Cisco, e iniciar las llamadas a la Skype para la implementación de empresa a través de la puerta de enlace. Las llamadas se enrutan desde la puerta de enlace a la Skype para Business Server vídeo de interoperabilidad a través del tronco SIP vídeo.
    
- Soporte para un usuario en una sala de conferencias con un sistema de vídeo admitido para llamar desde ese sistema a fin de unirse a una conferencia abierta o cerrada. Esta llamada atravesará el tronco SIP de vídeo.
    
- Soporte técnico para un usuario en una sala de conferencias con un sistema de vídeo compatible para llamar a un Skype para clientes empresariales. Esta llamada atravesará el tronco SIP.
    
- Soporte técnico para el control de llamadas Atlántico desde el Skype para servidor empresarial o desde el sistema VTC compatible para las llamadas de punto a punto y multipunto incluyen audio de silencio/anular-mute, pausar o reanudar vídeo, vídeo de bloqueo y llamada de espera/Naciones Unidas-espera.
    
## <a name="known-limitations"></a>Limitaciones conocidas

Este rol de servidor tiene las siguientes limitaciones:
  
- No se admiten llamadas nuevo desde el Skype para la implementación empresarial para la VTCs a través del tronco SIP vídeo. . Esto significa que se admiten sólo nuevo llamadas desde el VTCs en el Skype para la implementación empresarial a través del tronco SIP vídeo. Presencia para el sistema de vídeo compatible no estará disponible a través del tronco SIP vídeo a la VIS 
    
- Solo un grupo de servidores VIS independiente será compatible con el modo de tronco SIP de vídeo.
    
-  Para las comunicaciones entre el VTC y el VIS por medio del tronco SIP de vídeo, TLS + SRTP o TCP + RTP serán compatibles.
    
- El uso compartido de aplicaciones no es compatible. Se necesita un Skype para usuarios de empresa en la sala de conferencias para unirse a la Skype para conferencia empresarial (a través de un equipo portátil por ejemplo) y mostrar la aplicación de uso compartido de pantallas en uno de los monitores gratuitos en la sala de conferencias no está asociado a la VTC.
    
- La capacidad de un VTC de unirse a una reunión federada por medio del VIS no es compatible.
    
- La capacidad de un VTC de unirse a una reunión en línea por medio del VIS no es compatible.
    
- Las llamadas desde un VTC a la RTC por medio de un VIS no son compatibles.
    
- Las llamadas desde la RTC a un VTC por medio de un VIS no son compatibles.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resistencia
<a name="resiliency"> </a>

El VIS admite llamadas entrantes desde CUCM realizadas por medio de un tronco SIP de vídeo. Es posible perder la conectividad del canal de subida o de bajada, de modo que considere ambas posibilidades para una resistencia sólida:
  
1. **Grupo de servidores con respecto la conmutación por error** Si el grupo principal respecto que la puerta de enlace vídeo apunta a es hacia abajo, recuperación es posible si la puerta de enlace de vídeo ha definido troncos a grupos de servidores de respecto de dos (o más). Si la puerta de enlace de vídeo determina que no puede realizar llamadas al grupo de servidores VIS principal, simplemente, redirige las llamadas a un grupo de servidores VIS secundario.
    
     ![Diagrama de recuperación por error de grupo de VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un determinado grupo de servidores con respecto puede tener troncos de acceso a varias puertas de enlace, pero normalmente una puerta de enlace concreto no puede tener troncos a varios grupos de servidores con respecto, por lo que deben realizarse para admitir esta conmutación por error un trucos: definir 2 FDQNs en DNS que se resuelven en la misma dirección IP de una puerta de enlace de vídeo. Este truco consiste en definir 2 FDQN en DNS que se resuelvan en la misma dirección IP de una puerta de enlace de vídeo. Represente cada FQDN como una puerta de enlace de vídeo independiente en el documento de topología, donde cada puerta de enlace de vídeo tiene un tronco a un grupo de servidores VIS diferente y, de esta forma, la recuperación estará disponible (si se utiliza TLS, los nombres varios tendrán que estar en la SAN del certificado de la puerta de enlace de vídeo).
    
    > [!NOTE]
    > El VIS solo permite las llamadas entrantes de puertas de enlace configuradas en el documento de topología. 
  
2. **Conmutación por error de Front-End** Si un grupo de servidores con respecto recibe una llamada de CUCM, pero no puede acceder a su grupo principal de registrador o Front-End del próximo salto, las llamadas se enrutan a un grupo de servidores Front-End copia de seguridad.
    
     ![Diagrama de recuperación por error del front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    El respecto realizará el seguimiento del estado de su grupo de servidores Front-End principal y su copia de seguridad del grupo de Front-End (la configuración se encuentra en la configuración de copia de seguridad para el servicio de registrador en el documento de topología). Envía sondeos opciones una vez por minuto para ambos grupos de servidores y, si hay cinco errores consecutivos el respecto se supone que es un grupo de servidores Front-End determinado hacia abajo. Si el grupo de servidores Front-End principal se marca como está disponible configurado hacia abajo y no existe copia de seguridad la respecto envía nuevas llamadas desde la puerta de enlace para el grupo de servidores Front-End copia de seguridad. Una vez que el grupo de servidores Front-End principal vuelve, reanudará la respecto utilizando el grupo de servidores Front-End principal para las llamadas nuevo.
    
    Asimismo, el VIS implementará un temporizador de 10 segundos para las llamadas desde el tronco SIP de vídeo. Si el grupo principal de Front-End del próximo salto se usó para una llamada desde el tronco SIP vídeo y el principal del próximo salto Front-End de grupo de servidores no ha respondido con algunos mensaje SIP (incluido Trying 100) a la invitación a la que se le envió dentro de este valor del temporizador, el proxy de copia de seguridad del próximo salto para la llamada s Si ha configurado a intentarse digitalización. 
    
    > [!NOTE]
    > Si el próximo salto de copia de seguridad se intentó primero, luego, no se intentará el principal. 
  
    El administrador también puede usar el comando de conmutación por error de Windows PowerShell para forzar a que el VIS utilice el grupo de servidores front-end de copia de seguridad, por ejemplo, cuando se precisa realizar el mantenimiento en el grupo de servidores front-end principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistencia de troncos de vídeo y voz a la puerta de enlace del mismo nivel
<a name="resiliency"> </a>

Skype para Business Server admite también de voz y vídeo troncos SIP use el mismo punto de puerta de enlace. Por lo que podría tener la misma implementación CUCM troncos SIP de voz para el servidor de mediación y vídeo troncos SIP a VIS
  
- Una puerta de enlace RTC necesitará definirse con un FQDN en particular en el documento de topología para los troncos SIP de voz.
    
- El elemento del mismo nivel para la puerta de enlace RTC será el servidor de mediación.
    
- Si es necesario, se pueden definir varios troncos de voz, desde una puerta de enlace RTC hasta varios grupos de servidores de mediación.
    
- Será preciso definir una puerta de enlace de vídeo en el documento de topología para el tronco SIP de vídeo con el mismo FQDN que para la puerta de enlace RTC.
    
- El elemento del mismo nivel para la puerta de enlace de vídeo será el VIS.
    
- Se puede definir un tronco de vídeo único desde una puerta de enlace de vídeo a un grupo VIS en concreto.
    
- CUCM deberá estar configurado para enrutar las llamadas a través del tronco de voz frente el tronco vídeo correctamente. Por ejemplo, se podría usar un prefijo de marcado especial al marcar desde el VTC; CUCM se pudo asociar este prefijo de marcado en las llamadas al respecto, y las reglas de conversión adecuado eliminaría este prefijo de la solicitud SIP Invite a VIS
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistencia del VIS en la versión de Skype Empresarial con las versiones anteriores de Lync
<a name="resiliency"> </a>

ANTE sólo puede implementarse como parte de Skype para la implementación de la empresa. Puede interoperar con las conferencias de Lync 2013 y los clientes que forman parte de una implementación existente; en esos casos, será necesario el grupo de servidores con respecto a formar parte de un Skype para la implementación de empresa que incluye un grupo de servidores de registrador o FE es el próximo salto para el grupo de servidores con respecto.
  
El VIS no es compatible con la transcodificación entre RTV y H.264. No hay interoperabilidad de vídeo entre los clientes anteriores a Lync 2013 y los participantes de VTC en una conferencia.
  
Al disponer de clientes anteriores a Lync 2013 en una conferencia, los clientes móviles llevarán a cabo el envío por medio de RTV, por lo que los VTC no recibirán vídeo cuando el cliente móvil se convierta en el orador dominante.
  
Para que Lync 2013 funcione correctamente con un VIS que sea parte de una implementación de Skype Empresarial, Lync 2013 necesita que se aplique el CU correspondiente para actualizar el cliente de Lync 2013, CAA y para que AVMCU funcione con el VIS.
  
La interoperabilidad del VIS con Lync 2013 y los clientes de escritorio de Skype Empresarial se ha probado y es compatible.
  
Interoperabilidad de respecto con que no sean de escritorio (Android, Ipad, Iphone, Windows Phone, LMX, etcetera.) Skype para clientes empresariales disponibles desde el almacén de aplicaciones aplicable en el momento del lanzamiento de respecto se ha probado y es compatible.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperación de la pérdida de paquetes por medio de FEC
<a name="resiliency"> </a>

A fin de ayudar en la recuperación de la pérdida de paquetes, puede activar FEC. Cuando se activa, se utilizará un 50 % más de ancho de banda de vídeo en el trayecto del VIS al VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costes de transcodificación y ajustes del tamaño del VIS
<a name="resiliency"> </a>

Solo el vídeo se transmite desde el VTC de Cisco a varias secuencias de simulación de transcodificación usa la capacidad de la CPU. Aproximadamente 16 VTCs pueden tener su transcodificación vídeo (suponiendo que una secuencia de vídeo 720p desde cada VTC es transformar en 3 secuencias de simulación independiente en 180p, p 360 y 720p) en un único respecto que se ejecutan en el equivalente de la plataforma FE de recomendado de Lync 2013. Si está desactivada de transcodificación, guardará en la CPU frente. Sin embargo, la imagen de vídeo solicitada por respecto de la VTC será la resolución más baja comunes para satisfacer a todos los receptores en la Skype para lado empresarial. Tenga en cuenta que incluso con transcodificación desactivado, transcodificación puede activarse cuando Skype para clientes empresariales solicitan ciertas resoluciones bajas que VTCs no se puede enviar.
  
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
  
## <a name="see-also"></a>Consulte también
<a name="resiliency"> </a>

[Implementar servidor de interoperabilidad vídeo en Skype para Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
