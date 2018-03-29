---
title: Planificar Vía trabajo en Skype Empresarial 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planes para llamar a través de trabajo en Skype para Business Server, que permite la integración entre Skype para el negocio y el sistema de teléfono PBX, para que los usuarios puedan utilizar Skype para empresas para controlar sus teléfonos PBX.
ms.openlocfilehash: d70ffb7cd46f5d2ffd7efe4db860f3a84ca34ef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-via-work-in-skype-for-business-server-2015"></a>Planificar Vía trabajo en Skype Empresarial 2015
 
Planes para llamar a través de trabajo en Skype para Business Server, que permite la integración entre Skype para el negocio y el sistema de teléfono PBX, para que los usuarios puedan utilizar Skype para empresas para controlar sus teléfonos PBX.
  
 **Llamar a través de un trabajo** es una nueva característica de Skype para Business Server que le permite integrar su Skype para soluciones de negocios con los sistemas de teléfono PBX existentes. Hacer clic en un usuario habilitado para llamar a través de trabajo en Skype para empresas llamar a otro usuario, ya sea dentro de su implementación o un usuario externo. La llamada se efectúa utilizando el teléfono PBX del usuario. Esto permite a un usuario con un teléfono PBX para incluir audio en su ricos Skype para conversaciones de negocios. En versiones anteriores de la llamada remota de Lync Server control era una característica que permite a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype para Business Server, esta característica se ha reemplazado con llamar a través de trabajo.
  
Llamar a través de trabajo permite lo siguiente para los usuarios de teléfono PBX
  
- Experiencia "Hacer clic para llamar" con el audio proporcionado con el teléfono PBX.
    
- Presencia, búsqueda de usuarios y la integración de mensajería instantánea, por ejemplo, dos usuarios llamar a través de trabajo en una sesión de IM pueden añadir audio a su sesión, con el audio que se proporciona a través de los teléfonos PBX.
    
- La capacidad de agregar mensajería instantánea, uso compartido de aplicaciones y transferencia de archivos a una llamada de llamar a través de trabajo.
    
- Capacidad de unión a reuniones en un solo clic
    
## <a name="how-it-works"></a>Cómo funciona

Llamar a través de trabajo utiliza API de Web de comunicaciones unificadas (UCWA) como el agente de usuario de tipo sándwich (B2BUA) entre el sistema PBX y su Skype para la implementación de Business Server, para que ninguna puerta de enlace de la aplicación (CSTA) admitidos por el equipo de telecomunicaciones necesaria para conectarse Skype para Business Server con su sistema PBX. UCWA es un servicio que se introdujo en las versiones anteriores de Lync Server para habilitar la conectividad con móviles y clientes web y se instala automáticamente en cada servidor Front-End.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flujo de trabajo de llamada para una llamada de llamar a través de trabajo

El ejemplo siguiente ilustra cómo un usuario habilitado para llamar a través de trabajo puede utilizar el Skype para Business Server para hacer una llamada:
  
![Muestra los pasos durante una llamada Vía trabajo; primero, el autor de la llamada hace clic para llamar a alguien en el cliente Skype Empresarial; después, la UCWA hace sonar el teléfono del autor de la llamada. Cuando este contesta, se llama al destinatario.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. El usuario selecciona un usuario en su Skype para clientes empresariales y hace clic en el icono del teléfono para llamar a ellos. Durante una conversación de MI, el usuario también puede hacer clic para llamar al usuario con el que tiene establecida la sesión.
    
2. El teléfono PBX del usuario que realizó la llamada comienza a sonar. El identificador de este teléfono muestra un número de teléfono global que ha configurado para mostrar en el identificador de llamadas de todos los usuarios realizar llamadas de llamar a través de trabajo. Este número de teléfono global no es un número de teléfono real que corresponde al teléfono de cualquier persona. En su lugar, es una señal visual de que el usuario pueda saber que esto es su propia llamada de salida y no una llamada entrante sucede al mismo tiempo. Al implementar llamar a través de trabajo, debe educar a los usuarios acerca de este número de teléfono global y lo que significa.
    
3. El usuario que hizo la llamada toma su teléfono PBX. Skype para el negocio, a continuación, inicia la llamada de voz al destinatario. 
    
4. Cuando el destinatario responde se inicia la llamada de voz. Si ambos usuarios ya tenían una sesión de MI en curso, esta puede continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Unirse a una conferencia con Vía trabajo

Un usuario llame a través de trabajo puede unirse a una reunión programada, haga clic en la dirección URL de la reunión. Skype para el negocio, a continuación, muestra un mensaje **marcado para** hasta que el servicio de reunión marca el teléfono PBX del usuario. El usuario llame a través de trabajo, a continuación, toma el teléfono PBX y se une a la reunión.
  
Un usuario llame a través de trabajo también puede utilizar la opción **Reunirse ahora** en Skype para empresas para crear reuniones Reunirse ahora. A continuación, el usuario ve el mensaje **Marcado de salida a**, y suena el teléfono PBX.
  
Un usuario llame a través de trabajo también puede llamar a una reunión llamando al número de puente de conferencia desde dentro de Skype para el negocio. Si se necesita un PIN de conferencia, el usuario necesita usar su teléfono PBX para introducirlo.
  
### <a name="incoming-calls"></a>Llamadas entrantes

Cuando un usuario habilitado para llamar a través de trabajo recibe un Skype para llamadas de negocios, el teléfono PBX y Skype del usuario para clientes empresariales que del anillo todos simultáneamente (si el usuario ha configurado la llamada simultánea). El usuario puede aceptar la llamada por descolgar el teléfono PBX o haga clic en **Aceptar** en el Skype para Business notification. Si el usuario acepta la llamada mediante Skype para empresas, permanece abierto el Skype para ventana de negocio para la llamada. Pero si el usuario acepta la llamada por descolgar el teléfono PBX, cierra el Skype para la ventana de notificación de negocios y no hay ningún Skype para la sesión de negocios, la llamada de voz por teléfono PBX.
  
Cuando un usuario habilitado para llamar a través de trabajo recibe una llamada de la PBX, sólo los anillos de teléfono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitaciones de la llamada a través del trabajo

Llamar a través de un trabajo es una solución de voz que requiere poca configuración de hardware, pero tiene limitaciones en comparación con las características disponibles en completa de Telefonía IP empresarial o de control de llamadas remotas. Llamar a través de trabajo tiene las siguientes limitaciones:
  
- Si un usuario llame a través de trabajo ha establecido el reenvío de llamada en el número de devolución de llamada de llamar a través de trabajo y alguien intenta invitar a este usuario a una reunión por número de teléfono del usuario, la invitación no llegará al usuario. Necesita informar a sus usuarios para que inviten a los participantes a reuniones haciendo clic en el nombre, en vez de hacerlo en el número de teléfono. 
    
- Capacidad mejorada de 911 y el seguimiento de llamadas maliciosas no están disponibles durante las llamadas de llamar a través de trabajo.
    
- Los usuarios habilitados para llamar a través de trabajo no pueden utilizar la delegación, llamada de equipo o características de grupo de respuesta.
    
- Los usuarios de llamar a través de trabajo no pueden utilizar Skype para empresas para grabar una reunión, silenciar el enmudecer, mantenga o transferir la llamada o utilizar llamada park.
    
- Los usuarios no pueden utilizar llamar a través de trabajo para tener acceso a sus mensajes de correo de voz de PBX.
    
- Los usuarios de llamar a través de trabajo no pueden escalar una sesión que comenzó como una llamada a una reunión de colaboración que incluye comunicaciones, como vídeo, Powerpoint, Pizarra, o una nota de voz.
    
- Los usuarios de llamar a través de trabajo no pueden agregar más usuarios a una llamada de 2-persona.
    
- No hay compatibilidad para el emparejamiento de teléfonos de escritorio ni para el emparejamiento de complementos VDI.
    
- Si un usuario hace o responde una llamada usando el teléfono PBX (y no utiliza el Skype para ventana de negocio), no habrá ningún registro de la llamada.
    
- Si su sistema PBX no admite **REFERENCIA con reemplazos**, se producirá el siguiente comportamiento. Mientras que en una llamada de llamar a través de trabajo, si el usuario transfiere la llamada continua desde el teléfono PBX, la ventana de llamada no desaparecerá de su Skype para el negocio. Si luego el usuario cierra la ventana, la llamada entre el destino de la transferencia y el usuario al que se transfiere la llamada finalizará. 
    
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para la llamada a través del trabajo

Para habilitar a los usuarios para llamar a través de trabajo, debe tener algunos requisitos previos en su lugar. Para obtener más información sobre estos requisitos previos y para conocer los pasos acerca de cómo habilitar a los usuarios para llamar a través de trabajo, vea [Implementar llame a través de trabajo en Skype para Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Vea también

#### 

[Plan para el control remoto de llamada en Skype para negocios 2015](remote-call-control.md)
  
[Implementar la llamada a través del trabajo en Skype de Business Server 2015](../../deploy/deploy-call-via-work.md)

