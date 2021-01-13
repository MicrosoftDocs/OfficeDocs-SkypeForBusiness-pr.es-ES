---
title: Plan for Call Via Work in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planificación de Vía trabajo en Skype Empresarial Server, que permite la integración entre Skype Empresarial y su sistema telefónico PBX, para que los usuarios puedan usar Skype Empresarial para controlar sus teléfonos PBX.
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825880"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Plan for Call Via Work in Skype for Business Server
 
Planificación de Vía trabajo en Skype Empresarial Server, que permite la integración entre Skype Empresarial y su sistema telefónico PBX, para que los usuarios puedan usar Skype Empresarial para controlar sus teléfonos PBX.
  
 **Vía trabajo es** una nueva característica de Skype Empresarial Server que le permite integrar su solución de Skype Empresarial con sus sistemas telefónicos PBX existentes. Un usuario habilitado para Vía trabajo puede hacer clic en Skype Empresarial para llamar a otro usuario, ya sea dentro de su implementación o un usuario externo. La llamada se completa con el teléfono PBX del usuario. Esto permite a un usuario con un teléfono PBX incluir audio en sus conversaciones enriquecciones de Skype Empresarial. En versiones anteriores del control remoto de llamadas de Lync Server era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo.
  
Vía trabajo permite lo siguiente para usuarios de teléfono PBX
  
- Experiencia de hacer clic y llamar, con el audio proporcionado a través del teléfono PBX.
    
- Presencia, búsqueda de usuarios e integración de mensajería instantánea( por ejemplo, dos usuarios de Vía trabajo en una sesión de mensajería instantánea pueden agregar audio a su sesión, con el audio proporcionado a través de los teléfonos PBX.
    
- La capacidad de agregar mensajería instantánea, uso compartido de aplicaciones y transferencia de archivos a una llamada vía trabajo.
    
- Funcionalidad de unirse a una reunión con un solo clic
    
## <a name="how-it-works"></a>Cómo funciona

Vía trabajo usa la API web de comunicaciones unificadas (UCWA) como agente de usuario back-to-back (B2BUA) entre el sistema PBX y la implementación de Skype Empresarial Server, de modo que no se necesite ninguna puerta de enlace de aplicación de telecomunicaciones (CSTA) compatible con el equipo para conectar Skype Empresarial Server con su sistema PBX. UCWA es un servicio introducido en versiones anteriores de Lync Server para habilitar la conectividad con clientes móviles y web, y se instala automáticamente en cada servidor front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flujo de trabajo de llamada para una llamada vía trabajo

A continuación se muestra cómo un usuario habilitado para Vía trabajo puede usar Skype Empresarial Server para realizar una llamada:
  
![Muestra los pasos durante una llamada vía trabajo; en primer lugar, el autor de la llamada hace clic para llamar a alguien en el cliente de Skype Empresarial; a continuación, UCWA llama al teléfono del autor de la llamada. Cuando el autor de la llamada toma el teléfono, se llama al destinatario](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. El usuario selecciona un usuario en su cliente de Skype Empresarial y hace clic en el icono de teléfono para llamarlo. O bien, durante una conversación de mensajería instantánea, el usuario hace clic para llamar al usuario con el que está teniendo la sesión.
    
2. El teléfono PBX del usuario que llamó empieza a sonar. El identificador de llamada de este teléfono muestra un número de teléfono global que se ha configurado para que se muestre en el identificador de llamada de todos los usuarios que llaman vía trabajo. Este número de teléfono global no es un número de teléfono real que se corresponda con el teléfono de una persona. En su lugar, es una señal visual para que un usuario sepa que esta es su propia llamada saliente y no una llamada entrante que tiene lugar al mismo tiempo. Al implementar Vía trabajo, debe informar a los usuarios sobre este número de teléfono global y lo que significa.
    
3. El usuario que llamó toma su teléfono PBX. Después, Skype Empresarial inicia la llamada de voz al destinatario de la llamada. 
    
4. Cuando el destinatario de la llamada responde, comienza la llamada de voz. Si los dos usuarios ya tenían una sesión de mensajería instantánea activa, puede continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Unirse a una conferencia con Vía trabajo

Un usuario de Vía trabajo puede unirse a una reunión programada haciendo clic en la dirección URL de la reunión. A continuación, Skype Empresarial muestra un mensaje de salida de llamada **hasta** que el servicio de reunión marca el teléfono PBX del usuario. A continuación, el usuario vía trabajo toma el teléfono PBX y se une a la reunión.
  
Un usuario de Vía trabajo también puede usar la opción **Reunirse** ahora en Skype Empresarial para crear reuniones reunirse ahora. A continuación, el usuario ve el mensaje de salida **de** llamada y el teléfono PBX suena.
  
Un usuario de Vía trabajo también puede llamar a una reunión llamando al número de puente de conferencia desde Skype Empresarial. Si se requiere un PIN de conferencia, el usuario debe usar su teléfono PBX para introducir el PIN.
  
### <a name="incoming-calls"></a>Llamadas entrantes

Cuando un usuario habilitado para Vía trabajo recibe una llamada de Skype Empresarial, el teléfono PBX y los clientes de Skype Empresarial del usuario suenan simultáneamente (si el usuario ha configurado la llamada simultánea). El usuario puede aceptar la llamada seleccionando el teléfono PBX o haciendo clic en Aceptar **en** la notificación de Skype Empresarial. Si el usuario acepta la llamada con Skype Empresarial, la ventana de Skype Empresarial para la llamada permanece abierta. Pero si el usuario acepta la llamada seleccionando el teléfono PBX, se cierra la ventana de notificación de Skype Empresarial y no hay ninguna sesión de Skype Empresarial, solo la llamada de voz a través del teléfono PBX.
  
Cuando un usuario habilitado para Vía trabajo recibe una llamada PBX, solo suena el teléfono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitaciones de Vía trabajo

Vía trabajo es una solución de voz que requiere poca configuración de hardware, pero tiene limitaciones en comparación con las características disponibles en el control de llamadas Telefonía IP empresarial o remoto. Vía trabajo tiene las siguientes limitaciones:
  
- Si un usuario de Vía trabajo ha configurado el reenvío de llamadas al número de devolución de llamada Vía trabajo y alguien intenta invitar a este usuario a una reunión por el número de teléfono del usuario, la invitación no se pondrá en contacto con el usuario. Debe instruir a los usuarios para que inviten a los participantes a las reuniones haciendo clic en el nombre, no en el número de teléfono. 
    
- La funcionalidad 911 mejorada y el seguimiento de llamadas malintencionadas no están disponibles durante las llamadas vía trabajo.
    
- Los usuarios habilitados para Vía trabajo no pueden usar las características de delegación, llamada de equipo o grupo de respuesta.
    
- Los usuarios de Vía trabajo no pueden usar Skype Empresarial para grabar una reunión, silenciar o desactivar el audio de la llamada, retener o transferir la llamada, ni usar el estacionamiento de llamadas.
    
- Los usuarios no pueden usar Vía trabajo para obtener acceso a sus mensajes de correo de voz de PBX.
    
- Los usuarios de Vía trabajo no pueden escalar una sesión iniciada como llamada de voz a una reunión de colaboración que incluya comunicaciones como vídeo, PowerPoint, pizarra o Una nota.
    
- Los usuarios de Vía trabajo no pueden agregar más usuarios a una llamada de dos personas.
    
- No se admite el emparejamiento de teléfonos de escritorio ni el emparejamiento de complementos de VDI.
    
- Si un usuario realiza o responde una llamada con el teléfono PBX (y no usa la ventana de Skype Empresarial), no habrá ningún registro de la llamada.
    
- Si el sistema PBX no admite **REFER con Replaces,** se realizará el siguiente comportamiento. Mientras se realiza una llamada vía trabajo, si el usuario transfiere la llamada en curso desde el teléfono PBX, la ventana de llamada no desaparecerá de la ventana de Skype Empresarial. Si, a continuación, el usuario cierra la ventana de llamada, la llamada entre el destino de transferencia y el destinatario de la transferencia finalizará. 
    
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para Vía trabajo

Para habilitar a cualquier usuario para Vía trabajo, debe tener algunos requisitos previos en su lugar. Para obtener más información sobre estos requisitos previos y para ver los pasos para habilitar a los usuarios para Vía trabajo, consulte Implementar Vía trabajo en [Skype Empresarial Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Ver también

[Planear el control remoto de llamadas en Skype Empresarial](remote-call-control.md)
  
[Implementar Vía trabajo en Skype Empresarial Server 2015](../../deploy/deploy-call-via-work.md)

