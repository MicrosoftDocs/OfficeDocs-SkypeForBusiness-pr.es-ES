---
title: Planificar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumen: Revisar este tema mientras se planea integrar Skype para Business Server 2015 con dispositivos de terceros teleconferencia.'
ms.openlocfilehash: 1a0ae30cf383f9f05cc8c37ef2c1ba7b7c76cfb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server-2015"></a>Planificar el servidor de interoperabilidad de vídeo en Skype Empresarial Server 2015
 
**Resumen:** Revise este tema mientras se planea integrar Skype para Business Server 2015 con dispositivos de terceros teleconferencia.
  
Skype para Business Server ahora permite integrar con ciertas soluciones de terceros VTC (sistema de teleconferencia por vídeo). La nueva función de servidor que permite esta interoperabilidad de sistemas de videoconferencia es el servidor vídeo de interoperabilidad (VIS), que actualmente se implementa como una función de servidor de independiente disponible sólo para las instalaciones locales. Un VIS actúa como intermediario entre un sistema de teleconferencia de terceros y un Skype para la implementación de Business Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg. Revise este artículo para determinar si debe utilizar esta característica en su Skype para instalación del servidor de empresa.
  
## <a name="device-interoperability"></a>Interoperabilidad de dispositivos

La interoperación está probada y es compatible con el registro de las VTC de Cisco en CUCM versión 10.5 y troncos TCP SIP configurados entre CUCM y el VIS.
  
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
>  Software de Cisco versión TC7.0.0 o anteriormente es necesaria en estos sistemas para la integración con Skype para Business Server funcione como se esperaba.
  
## <a name="sip-trunks"></a>Troncos SIP

Las funciones de servidor de interoperabilidad de vídeo en el modo de tronco SIP, donde la VTCs continúan registrándose con la infraestructura existente de Cisco - por ejemplo, Cisco llamar Manager (CUCM). Un vídeo troncal SIP se define entre CUCM y el VIS para que se pueden enrutar llamadas entre los dos sistemas. Se admiten sólo llamadas sobre el tronco SIP de la VTC a la VIS. Por lo tanto, VTCs puede marcar a un Skype para conferencia de negocios (marcando el número de teléfono asociado con el operador automático de llamar), pero no se pueden arrastrar y colocar en la conferencia.
  
![Diagrama de VIS en SE](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Características

El rol de servidor proporciona:
  
- Conversión entre los formatos H.264 utilizado por sistemas de vídeo 3ª parte y el Skype para la implementación de Business Server.
    
- Conversión de una sola secuencia de vídeo con una resolución determinada de una VTC en varias secuencias de transmisión simultánea de diferentes resoluciones para su uso en el Skype para la implementación de Business Server. Estas secuencias pueden enviarse a la AVMCU y luego a Skype para extremos de Business Server y otros sistemas de vídeo que han solicitado diferentes resoluciones. Esta conversión también se utiliza cuando el sistema de vídeo de otro fabricante está implicado en un Skype para empresas A / de la llamada de conferencia V. Una vez que se alcanza el límite de transcodificación en un determinado servidor VIS, las siguientes solicitudes de diferentes resoluciones sólo recibirá una secuencia con la resolución más baja. 
    
- Soporte para un vídeo troncal SIP entre la puerta de enlace CUCM y un Skype para servidor Business Server vídeo interoperabilidad; VTCs continuarán registrarse con la puerta de enlace de Cisco, e iniciar llamadas al Skype para la implementación de la empresa a través de la puerta de enlace. Llamadas se enrutan desde la puerta de enlace para el Skype para Business Server de interoperabilidad vídeo sobre el vídeo tronco SIP.
    
- Soporte para un usuario en una sala de conferencias con un sistema de vídeo admitido para llamar desde ese sistema a fin de unirse a una conferencia abierta o cerrada. Esta llamada atravesará el tronco SIP de vídeo.
    
- Soporte para un usuario en una sala de conferencias con un sistema de vídeo compatible llamar a un Skype para cliente de empresa. Esta llamada atravesará el tronco SIP.
    
- Soporte para control de llamada intermedio desde el Skype para el lado de Business Server o desde el sistema VTC compatible con llamadas de punto a punto y multipuntos incluyendo audio en silencio y desactivar el modo silencio, pausar/reanudar el vídeo, vídeo de bloqueo y suspensión/ONU-hold llamada.
    
## <a name="known-limitations"></a>Limitaciones conocidas

Este rol de servidor tiene las siguientes limitaciones:
  
- No se admiten nuevas llamadas desde el Skype para implementación en la empresa a la VTCs sobre el vídeo tronco SIP. . Esto significa que se admiten sólo nuevas llamadas de la VTCs en el Skype para la implementación de negocios sobre el vídeo tronco SIP. Presencia para el sistema de vídeo compatible no estará disponible sobre el vídeo troncal SIP para VIS. 
    
- Solo un grupo de servidores VIS independiente será compatible con el modo de tronco SIP de vídeo.
    
-  Para las comunicaciones entre el VTC y el VIS por medio del tronco SIP de vídeo, TLS + SRTP o TCP + RTP serán compatibles.
    
- El uso compartido de aplicaciones no es compatible. Necesita un Skype para usuarios de empresa en la sala de conferencias unir el Skype para conferencia de negocios (a través de un equipo portátil por ejemplo) y mostrar la aplicación de uso compartido de pantallas en uno de los monitores en la sala de conferencias no asociado con el VTC libres.
    
- La capacidad de un VTC de unirse a una reunión federada por medio del VIS no es compatible.
    
- La capacidad de un VTC de unirse a una reunión en línea por medio del VIS no es compatible.
    
- Las llamadas desde un VTC a la RTC por medio de un VIS no son compatibles.
    
- Las llamadas desde la RTC a un VTC por medio de un VIS no son compatibles.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resistencia
<a name="resiliency"> </a>

El VIS admite llamadas entrantes desde CUCM realizadas por medio de un tronco SIP de vídeo. Es posible perder la conectividad del canal de subida o de bajada, de modo que considere ambas posibilidades para una resistencia sólida:
  
1. **Failover de grupo VIS** Si el grupo principal de VIS que señala la puerta de enlace de vídeo está desactivado, la recuperación es posible si la puerta de enlace de vídeo ha definido los troncos a dos (o más) conjuntos de VIS. Si la puerta de enlace de vídeo determina que no puede realizar llamadas al grupo de servidores VIS principal, simplemente, redirige las llamadas a un grupo de servidores VIS secundario.
    
     ![Diagrama de recuperación por error de grupo de VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un determinado conjunto de VIS puede tener troncos de acceso a varias puertas de enlace, pero normalmente una puerta de enlace concreto no puede tener los troncos a varios grupos de VIS, por lo que debe hacer para permitir esta conmutación por error un truco: definir 2 FDQNs en DNS que se resuelven en la misma dirección IP de una puerta de enlace de vídeo. Este truco consiste en definir 2 FDQN en DNS que se resuelvan en la misma dirección IP de una puerta de enlace de vídeo. Represente cada FQDN como una puerta de enlace de vídeo independiente en el documento de topología, donde cada puerta de enlace de vídeo tiene un tronco a un grupo de servidores VIS diferente y, de esta forma, la recuperación estará disponible (si se utiliza TLS, los nombres varios tendrán que estar en la SAN del certificado de la puerta de enlace de vídeo).
    
    > [!NOTE]
    > El VIS solo permite las llamadas entrantes de puertas de enlace configuradas en el documento de topología. 
  
2. **Failover de Front-End** Si un grupo de VIS recibe una llamada de CUCM, pero no puede llegar a su grupo principal de registrador o Front-End de salto siguiente, las llamadas se enrutan a un grupo de Front-End de copia de seguridad.
    
     ![Diagrama de recuperación por error del front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    El VIS realizará el seguimiento del estado de su grupo principal de Front-End y su grupo copia de seguridad de Front-End (la configuración se encuentra en la configuración de copia de seguridad para el servicio de Registrar en el documento de topología). Envía las encuestas de opciones una vez por minuto para ambos grupos, y si hay cinco errores consecutivos el VIS supone que un determinado grupo de Front-End está inactivo. Si el grupo principal de Front-End está marcado como abajo y allí está disponible configurado copia de seguridad el VIS envía nuevas llamadas desde la puerta de enlace para el grupo de Front-End de copia de seguridad. Una vez que vuelve el grupo principal de Front-End, reanudará el VIS utilizando el conjunto principal de Front-End para llamadas nuevas.
    
    Asimismo, el VIS implementará un temporizador de 10 segundos para las llamadas desde el tronco SIP de vídeo. Si se utilizó el conjunto principal de Front-End del próximo salto para una llamada de vídeo tronco SIP y el Front-End del próximo salto principal grupo no respondió con algún mensaje SIP (incluyendo intentando 100) a la invitación enviada a él dentro de este valor de temporizador, el proxy de salto siguiente copia de seguridad para la llamada de s Si ha configurado a intentarse digitalización. 
    
    > [!NOTE]
    > Si el salto siguiente copia de seguridad se ha probado en primer lugar, el principal no se intentará a continuación. 
  
    El administrador también puede utilizar el comando de conmutación por error de Windows PowerShell para forzar VIS a utilizar la copia de seguridad agrupación de Front-End, por ejemplo, al mantenimiento tiene que realizarse en el grupo principal de Front-End.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistencia de troncos de vídeo y voz a la puerta de enlace del mismo nivel
<a name="resiliency"> </a>

Skype para Business Server admite también voz y vídeo troncos SIP utilizan el mismo nodo de puerta de enlace. Por lo que podría tener la misma implementación de CUCM troncos de voz SIP en el servidor de mediación y vídeo troncos SIP para VIS.
  
- Una puerta de enlace RTC necesitará definirse con un FQDN en particular en el documento de topología para los troncos SIP de voz.
    
- El elemento del mismo nivel para la puerta de enlace RTC será el servidor de mediación.
    
- Si es necesario, se pueden definir varios troncos de voz, desde una puerta de enlace RTC hasta varios grupos de servidores de mediación.
    
- Será preciso definir una puerta de enlace de vídeo en el documento de topología para el tronco SIP de vídeo con el mismo FQDN que para la puerta de enlace RTC.
    
- El elemento del mismo nivel para la puerta de enlace de vídeo será el VIS.
    
- Se puede definir un tronco de vídeo único desde una puerta de enlace de vídeo a un grupo VIS en concreto.
    
- CUCM deberá configurarse para enrutar llamadas correctamente sobre el tronco de voz frente el tronco del vídeo. Por ejemplo, podría utilizarse un prefijo de marcado especiales cuando se marque desde el VTC; CUCM se pudo asociar este prefijo de marcado en las llamadas al respecto y las reglas de conversión adecuado eliminaría este prefijo de SIP Invite al VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistencia del VIS en la versión de Skype Empresarial con las versiones anteriores de Lync
<a name="resiliency"> </a>

VIS sólo puede implementarse como parte de Skype para la implementación en la empresa. Puede interoperar con Lync 2013 conferencias y clientes que forman parte de una implementación existente; en esos casos, el grupo VIS deberá formar parte de un Skype para la implementación de empresa que incluya un grupo de FE/registrador es el próximo salto para el grupo de VIS.
  
El VIS no es compatible con la transcodificación entre RTV y H.264. No hay interoperabilidad de vídeo entre los clientes anteriores a Lync 2013 y los participantes de VTC en una conferencia.
  
Tener clientes de 2013 pre-Lync en una conferencia hará que los clientes móviles enviar mediante RTV resultando en VTCs no recibir ningún vídeo cuando el cliente móvil se convierta en el altavoz dominante.
  
Para Lync 2013 funcione correctamente con VIS que forma parte de un Skype para implementación en la empresa, Lync 2013 necesita el CU adecuado aplicar que actualiza el cliente Lync 2013, CAA y AVMCU para trabajar con VIS.
  
Interoperabilidad de VIS con 2013 de Lync y Skype para clientes de escritorio de negocios se ha probado y es compatible.
  
Interoperabilidad de VIS con no escritorio (Android, Ipad, Iphone, Windows Phone, LMX, etcetera.) Skype para clientes de empresa disponibles desde el almacén de aplicaciones aplicable en el momento del lanzamiento de VIS se ha probado y es compatible.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperación de la pérdida de paquetes por medio de FEC
<a name="resiliency"> </a>

A fin de ayudar en la recuperación de la pérdida de paquetes, puede activar FEC. Cuando se activa, se utilizará un 50 % más de ancho de banda de vídeo en el trayecto del VIS al VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costes de transcodificación y ajustes del tamaño del VIS
<a name="resiliency"> </a>

Solo el vídeo se transmite desde el VTC de Cisco en varias secuencias de transmisión simultánea de transcodificación utiliza la capacidad de la CPU. Aproximadamente 16 VTCs pueden tener su vídeo transcodificado (suponiendo que una secuencia de vídeo 720p de cada VTC está transcodificado en 3 secuencias de transmisión simultánea independiente en 720p, p 360 y 180p) en un único VIS quedando el equivalente del 2013 Lync recomienda plataforma FE. Si está desactivada la transcodificación, guardará en CPU VIS. Sin embargo, la imagen de vídeo solicitada por VIS de la VTC será la resolución más baja común para satisfacer a todos los receptores en el Skype para el lado del negocio. Tenga en cuenta que incluso con transcodificación off, transcodificación puede activarse cuando Skype para clientes empresariales solicitan ciertas resoluciones bajas que VTCs no se puede enviar.
  
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

#### 

[Implementar servidor de interoperabilidad vídeo en Skype para Business Server 2015](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)

