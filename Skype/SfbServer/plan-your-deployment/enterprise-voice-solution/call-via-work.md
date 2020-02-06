---
title: Plan de llamadas por trabajo en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planificación de llamadas mediante el trabajo en Skype empresarial Server, que permite la integración entre Skype empresarial y el sistema telefónico PBX, de modo que los usuarios puedan usar Skype empresarial para controlar sus teléfonos PBX.
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803160"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Plan de llamadas por trabajo en Skype empresarial Server
 
Planificación de llamadas mediante el trabajo en Skype empresarial Server, que permite la integración entre Skype empresarial y el sistema telefónico PBX, de modo que los usuarios puedan usar Skype empresarial para controlar sus teléfonos PBX.
  
 La **llamada a través del trabajo** es una nueva característica de Skype empresarial Server que le permite integrar su solución de Skype empresarial con sus sistemas telefónicos PBX existentes. Un usuario habilitado para la llamada a través del trabajo puede hacer clic en Skype empresarial para llamar a otro usuario, ya sea dentro de la implementación o de un usuario externo. La llamada se completa al utilizar el teléfono PBX del usuario. Esto permite que un usuario con un teléfono PBX incluya audio en sus conversaciones enriquecidas de Skype empresarial. En versiones anteriores de Lync Server, el control remoto de llamadas era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype empresarial Server, esta característica se ha sustituido por una llamada por trabajo.
  
Llamadas por trabajo permite lo siguiente para usuarios de centralita
  
- Experiencia "Hacer clic para llamar" con el audio proporcionado con el teléfono PBX.
    
- Presencia, búsqueda de usuarios e integración de mensajería instantánea: por ejemplo, dos llamadas a través de usuarios de trabajo en una sesión de mensajería instantánea pueden agregar audio a su sesión, con el audio proporcionado a través de los teléfonos PBX.
    
- La posibilidad de agregar mensajería instantánea, uso compartido de aplicaciones y transferencia de archivos a una llamada a través de una llamada de trabajo.
    
- Capacidad de unión a reuniones en un solo clic
    
## <a name="how-it-works"></a>Cómo funciona

La llamada a través del trabajo usa la API Web de comunicaciones unificadas (UCWA) como agente de usuario que se revierte (B2BUA) entre el sistema PBX y la implementación de Skype empresarial Server, de modo que no se necesita ninguna puerta de enlace de aplicación de telecomunicaciones (CSTA) compatible con el equipo para conectarse Skype empresarial Server con su sistema PBX. UCWA es un servicio introducido en versiones anteriores de Lync Server para habilitar la conectividad con clientes móviles y Web, y se instala automáticamente en todos los servidores front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flujo de trabajo de llamada para una llamada mediante una llamada de trabajo

A continuación se muestra cómo un usuario habilitado para la llamada a través del trabajo puede usar el servidor de Skype empresarial para hacer una llamada:
  
![Muestra los pasos durante una llamada Vía trabajo; primero, el autor de la llamada hace clic para llamar a alguien en el cliente Skype Empresarial; después, la UCWA hace sonar el teléfono del autor de la llamada. Cuando este contesta, se llama al destinatario.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. El usuario selecciona un usuario en su cliente de Skype empresarial y hace clic en el icono del teléfono para llamarlo. Durante una conversación de MI, el usuario también puede hacer clic para llamar al usuario con el que tiene establecida la sesión.
    
2. El teléfono PBX del usuario que realizó la llamada comienza a sonar. La identificación de llamadas para este teléfono muestra un número de teléfono global que usted ha configurado para mostrar en la identificación de llamadas de todos los usuarios que colocan llamadas por trabajo. Este número de teléfono global no es un número de teléfono real que se corresponda con el teléfono de cualquier persona. En su lugar, es una señal visual para que el usuario sepa que se trata de una llamada saliente, y no se realiza una llamada entrante al mismo tiempo. Al implementar las llamadas por trabajo, debe educar a esos usuarios sobre este número de teléfono global y qué significan.
    
3. El usuario que hizo la llamada toma su teléfono PBX. Skype empresarial inicia la llamada a la persona que llama. 
    
4. Cuando el destinatario responde se inicia la llamada de voz. Si ambos usuarios ya tenían una sesión de MI en curso, esta puede continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Unirse a una conferencia con Vía trabajo

Una llamada a través del usuario del trabajo puede unirse a una reunión programada haciendo clic en la dirección URL de la reunión. Skype empresarial muestra, a continuación, un **marcado para enviar** un mensaje hasta que el servicio de reuniones Marque el teléfono PBX del usuario. La llamada a través del usuario del trabajo selecciona el teléfono PBX y se une a la reunión.
  
Una llamada a través del usuario del trabajo también puede usar la opción **reunirse ahora** en Skype empresarial para crear reuniones reunirse ahora. A continuación, el usuario ve el mensaje **Marcado de salida a**, y suena el teléfono PBX.
  
Una llamada a través del usuario del trabajo también puede marcar una reunión llamando al número de puente de conferencia desde Skype empresarial. Si se necesita un PIN de conferencia, el usuario necesita usar su teléfono PBX para introducirlo.
  
### <a name="incoming-calls"></a>Llamadas entrantes

Cuando un usuario habilitado para la llamada recibe una llamada de Skype empresarial, el teléfono PBX y los clientes de Skype empresarial del usuario se resaltan simultáneamente (si el usuario ha configurado la llamada simultánea). El usuario puede aceptar la llamada si selecciona el teléfono PBX o hace clic en **Aceptar** en la notificación de Skype empresarial. Si el usuario acepta la llamada con Skype empresarial, la ventana de Skype empresarial para la llamada permanece abierta. Pero si el usuario acepta la llamada al recoger el teléfono PBX, la ventana de notificación de Skype empresarial se cerrará y no habrá ninguna sesión de Skype empresarial, solo la llamada de voz a través del teléfono PBX.
  
Cuando un usuario habilitado para la llamada a través del trabajo recibe una llamada de PBX, solo suena el teléfono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitaciones de la llamada a través del trabajo

La llamada a través del trabajo es una solución de voz que requiere poca configuración de hardware, pero tiene limitaciones comparadas con las características disponibles en la telefonía completa de la empresa o el control remoto de llamadas. La llamada a través del trabajo tiene las siguientes limitaciones:
  
- Si una llamada a través del usuario del trabajo ha configurado el desvío de llamadas para la llamada a través del número de devolución de llamada del trabajo y alguien intenta invitar a este usuario a una reunión por el número de teléfono del usuario, la invitación no se comunica con el usuario. Necesita informar a sus usuarios para que inviten a los participantes a reuniones haciendo clic en el nombre, en vez de hacerlo en el número de teléfono. 
    
- La función mejorada 911 y el seguimiento de llamadas malintencionadas no están disponibles durante las llamadas a través de llamadas de trabajo.
    
- Los usuarios habilitados para la llamada a través del trabajo no pueden usar las características delegación, llamada de equipo o grupo de respuesta.
    
- Los usuarios de la llamada a través del trabajo no pueden usar Skype empresarial para grabar una reunión, silenciar o reactivar la llamada, retener o transferir la llamada, o usar el parque de llamadas.
    
- Los usuarios no pueden usar la llamada a través del trabajo para acceder a sus mensajes de correo de voz PBX.
    
- Los usuarios de la llamada a través del trabajo no pueden asignar una sesión que se inició como una llamada de voz a una reunión de colaboración que incluye comunicaciones como vídeo, PowerPoint, pizarra o una nota.
    
- Los usuarios de la llamada a través del trabajo no pueden agregar más usuarios a una llamada de dos personas.
    
- No hay compatibilidad para el emparejamiento de teléfonos de escritorio ni para el emparejamiento de complementos VDI.
    
- Si un usuario hace o responde a una llamada con el teléfono PBX (y no usa la ventana de Skype empresarial), no habrá ningún registro de la llamada.
    
- Si su sistema PBX no admite **REFERENCIA con reemplazos**, se producirá el siguiente comportamiento. Mientras se encuentre en una llamada a través de una llamada de trabajo, si el usuario transfiere la llamada en curso desde el teléfono PBX, la ventana de la llamada no desaparecerá de la ventana de Skype empresarial. Si luego el usuario cierra la ventana, la llamada entre el destino de la transferencia y el usuario al que se transfiere la llamada finalizará. 
    
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para llamar por trabajo

Para permitir que los usuarios puedan realizar llamadas por trabajo, debe disponer de algunos requisitos previos. Para obtener más información sobre estos requisitos previos y sobre cómo habilitar a los usuarios para que llamen a través del trabajo, consulte [implementar llamada por trabajo en Skype empresarial Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Vea también

[Planear el control remoto de llamadas en Skype empresarial](remote-call-control.md)
  
[Implementar Vía trabajo en Skype Empresarial Server 2015](../../deploy/deploy-call-via-work.md)

