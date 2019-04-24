---
title: Planeación de la llamada vía trabajo en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planeación para llamar vía trabajo en Skype para Business Server, lo que permite la integración entre Skype para la empresa y el sistema de teléfono PBX, para que los usuarios pueden usar Skype para la empresa para controlar sus teléfonos PBX.
ms.openlocfilehash: 3a2452f732d55f305d91cee9cd2b940f7bb3c88e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207247"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planeación de la llamada vía trabajo en Skype para Business Server
 
Planeación para llamar vía trabajo en Skype para Business Server, lo que permite la integración entre Skype para la empresa y el sistema de teléfono PBX, para que los usuarios pueden usar Skype para la empresa para controlar sus teléfonos PBX.
  
 **Llamar vía trabajo** es una característica nueva de Skype para Business Server que le permite integrar su Skype para soluciones de negocio con los sistemas de teléfono PBX existentes. Hacer clic en un usuario habilitado para llamar vía trabajo en Skype para la empresa llamar a otro usuario, ya sea dentro de la implementación o un usuario externo. La llamada se completa al utilizar el teléfono PBX del usuario. Esto permite que un usuario con un teléfono PBX incluir audio en su Skype enriquecido para conversaciones de negocios. En versiones anteriores de llamada remota de Lync Server control era una característica que habilita a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype para Business Server, esta característica se ha reemplazado con llamar vía trabajo.
  
Llamar vía trabajo permite los siguientes elementos para los usuarios de teléfonos PBX
  
- Experiencia "Hacer clic para llamar" con el audio proporcionado con el teléfono PBX.
    
- Presencia, búsqueda de usuarios y la integración de mensajería instantánea--por ejemplo, dos usuarios llamar vía trabajo en una sesión de mensajería instantánea pueden agregar audio a su sesión, con el audio que se proporciona a través de los teléfonos PBX.
    
- La capacidad de agregar mensajería instantánea, uso compartido de aplicaciones y transferencia de archivos a una llamada de llamar vía trabajo.
    
- Capacidad de unión a reuniones en un solo clic
    
## <a name="how-it-works"></a>Cómo funciona

Llamar vía trabajo usa API de Web de comunicaciones unificadas (UCWA) como el agente de usuario opuesta (B2BUA) entre el sistema PBX y su Skype para la implementación de servidor empresarial, por lo que no es necesario ninguna puerta de enlace de la aplicación (CSTA) compatibles con el equipo de telecomunicaciones para conectarse Skype para Business Server con su sistema PBX. UCWA es un servicio que se introdujo en las versiones anteriores de Lync Server para habilitar la conectividad con mobile y clientes web y se instala automáticamente en cada servidor Front-End.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Llamar al flujo de trabajo para una llamada de llamadas a través de trabajo

El ejemplo siguiente ilustra cómo un usuario habilitado para llamar vía trabajo puede usar la Skype para Business Server para realizar una llamada:
  
![Muestra los pasos durante una llamada Vía trabajo; primero, el autor de la llamada hace clic para llamar a alguien en el cliente Skype Empresarial; después, la UCWA hace sonar el teléfono del autor de la llamada. Cuando este contesta, se llama al destinatario.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. El usuario selecciona un usuario en su Skype para clientes empresariales y hace clic en el icono de teléfono para llamar a ellos. Durante una conversación de MI, el usuario también puede hacer clic para llamar al usuario con el que tiene establecida la sesión.
    
2. El teléfono PBX del usuario que realizó la llamada comienza a sonar. El identificador de autor de la llamada de este teléfono muestra un número de teléfono globales que ha configurado para mostrar en el identificador de autor de la llamada de todos los usuarios realizar llamadas de llamar vía trabajo. Este número de teléfono global no es un número de teléfono real que corresponde al teléfono de cualquier persona. En su lugar, es una señal visual para que un usuario sepan que se trata de su propia llamada de salida y no una llamada entrante que sucede al mismo tiempo. Al implementar llamar vía trabajo, deben instruir a los usuarios acerca de este número de teléfono global y lo que significa.
    
3. El usuario que hizo la llamada toma su teléfono PBX. Skype para la empresa, a continuación, inicia la llamada de voz para el destinatario de la llamada. 
    
4. Cuando el destinatario responde se inicia la llamada de voz. Si ambos usuarios ya tenían una sesión de MI en curso, esta puede continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Unirse a una conferencia con Vía trabajo

Un usuario llamar vía trabajo puede unirse a una reunión programada, haga clic en la dirección URL de la reunión. Skype para la empresa, a continuación, muestra un mensaje de **llamadas de salida a** hasta que el servicio de reunión marca el teléfono PBX del usuario. El usuario llamar vía trabajo, a continuación, descuelga el teléfono PBX y se une a la reunión.
  
Un usuario llamar vía trabajo también puede usar la opción **Reunirse ahora** en Skype para la empresa para crear reuniones Reunirse ahora. A continuación, el usuario ve el mensaje **Marcado de salida a**, y suena el teléfono PBX.
  
Un usuario llamar vía trabajo también puede conectarse a una reunión llamando al número de puente de conferencia desde dentro de Skype para la empresa. Si se necesita un PIN de conferencia, el usuario necesita usar su teléfono PBX para introducirlo.
  
### <a name="incoming-calls"></a>Llamadas entrantes

Cuando un usuario habilitado para llamar vía trabajo recibe un Skype para llamada de negocio, el teléfono PBX y Skype del usuario para clientes empresariales todos los teléfonos suenan simultáneamente (si el usuario ha configurado la llamada simultánea). El usuario puede aceptar la llamada por descolgar el teléfono PBX o al hacer clic en **Aceptar** en el Skype para Business notification. Si el usuario acepta la llamada mediante Skype para la empresa, la Skype para la ventana de negocio para la llamada permanece abierta. Pero si el usuario acepta la llamada por descolgar el teléfono PBX, a continuación, se cierra el Skype para la ventana de notificación de negocio y no hay ningún Skype para la sesión de negocio, la llamada de voz a través del teléfono PBX.
  
Cuando un usuario habilitado para llamar vía trabajo recibe una llamada de PBX, solo la suena el teléfono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitaciones de la llamada vía trabajo

Llamar vía trabajo es una solución de voz que requiere poca el programa de instalación de hardware, pero tiene limitaciones en comparación con las características disponibles en el control remoto de llamadas o de telefonía IP empresarial completa. Llamar vía trabajo tiene las limitaciones siguientes:
  
- Si un usuario llamar vía trabajo ha configurado el desvío de llamadas al número de devolución de llamada llamar vía trabajo y alguien intenta invitar a este usuario a una reunión por número de teléfono del usuario, la invitación no alcanzará el usuario. Necesita informar a sus usuarios para que inviten a los participantes a reuniones haciendo clic en el nombre, en vez de hacerlo en el número de teléfono. 
    
- Capacidad de 911 mejorada y seguimiento de llamadas malintencionadas no están disponibles durante las llamadas de llamar vía trabajo.
    
- Los usuarios habilitados para llamar vía trabajo no pueden usar la delegación, llamada de equipo o las características de grupo de respuesta.
    
- Los usuarios de llamar vía trabajo no pueden usar Skype para la empresa para grabar una reunión, desactivar o reactivar el audio de la llamada, mantenga o transferir la llamada o usar estacionamiento de llamadas.
    
- Los usuarios no pueden usar llamar vía trabajo para tener acceso a sus mensajes de correo de voz de PBX.
    
- Los usuarios de llamadas a través de trabajo no pueden pasar de una sesión que ha iniciado como una llamada de voz a una reunión de colaboración que incluye comunicaciones, como vídeo, Powerpoint, Pizarra, o una nota.
    
- Los usuarios de llamadas a través de trabajo no pueden agregar más usuarios a una llamada de 2-persona.
    
- No hay compatibilidad para el emparejamiento de teléfonos de escritorio ni para el emparejamiento de complementos VDI.
    
- Si un usuario realiza o se responde a una llamada con el teléfono PBX (y no usa la Skype para la ventana de negocio), no habrá ningún registro de la llamada.
    
- Si su sistema PBX no admite **REFERENCIA con reemplazos**, se producirá el siguiente comportamiento. Mientras se encuentra en una llamada de llamar vía trabajo, si el usuario transfiere la llamada continuada desde el teléfono PBX, la ventana de llamada no desaparecerá de su Skype para la ventana de negocio. Si luego el usuario cierra la ventana, la llamada entre el destino de la transferencia y el usuario al que se transfiere la llamada finalizará. 
    
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para la llamada vía trabajo

Para habilitar a los usuarios para llamar vía trabajo, debe tener algunos requisitos previos en su lugar. Para obtener más información sobre estos requisitos previos y para obtener instrucciones acerca de cómo habilitar a los usuarios para llamar vía trabajo, vea [Implementar llamar vía trabajo en Skype para Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Vea también

[Plan para el control remoto de llamadas en Skype para la empresa](remote-call-control.md)
  
[Implementar Vía trabajo en Skype Empresarial Server 2015](../../deploy/deploy-call-via-work.md)

