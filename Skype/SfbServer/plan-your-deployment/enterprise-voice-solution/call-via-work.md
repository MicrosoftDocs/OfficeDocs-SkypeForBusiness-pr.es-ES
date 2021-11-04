---
title: Plan for Call Via Work in Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planeación de llamadas a través del trabajo en Skype Empresarial Server, que permite la integración entre Skype Empresarial y el sistema telefónico PBX, de modo que los usuarios puedan usar Skype Empresarial para controlar sus teléfonos PBX.
ms.openlocfilehash: 268ee3a6caa7b304cc63b4e7e16c2a7565f9ced3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768568"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Plan for Call Via Work in Skype Empresarial Server
 
Planeación de llamadas a través del trabajo en Skype Empresarial Server, que permite la integración entre Skype Empresarial y el sistema telefónico PBX, de modo que los usuarios puedan usar Skype Empresarial para controlar sus teléfonos PBX.
  
 **Llamar a través del** trabajo es una nueva característica de Skype Empresarial Server que le permite integrar su solución Skype Empresarial con los sistemas telefónicos PBX existentes. Un usuario habilitado para Llamar a través del trabajo puede hacer clic en Skype Empresarial para llamar a otro usuario, ya sea dentro de la implementación o un usuario externo. La llamada se completa con el teléfono PBX del usuario. Esto permite que un usuario con un teléfono PBX incluya audio en sus conversaciones Skype Empresarial enriquecciones. En versiones anteriores del control remoto de llamadas de Lync Server era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Llamar a través del trabajo.
  
Llamar a través del trabajo habilita lo siguiente para usuarios de teléfono PBX
  
- Experiencia de hacer clic y llamar, con el audio proporcionado a través del teléfono PBX.
    
- Presencia, búsqueda de usuarios e integración de mensajería instantánea: por ejemplo, dos usuarios de Llamadas a través del trabajo en una sesión de mensajería instantánea pueden agregar audio a su sesión, con el audio proporcionado a través de los teléfonos PBX.
    
- La capacidad de agregar mensajería instantánea, uso compartido de aplicaciones y transferencia de archivos a una llamada a través del trabajo.
    
- Funcionalidad de unirse a una reunión con un solo clic
    
## <a name="how-it-works"></a>Cómo funciona

Call Via Work usa la API web de comunicaciones unificadas (UCWA) como agente de usuario back-to-back (B2BUA) entre el sistema PBX y la implementación de Skype Empresarial Server, de modo que no se necesite ninguna puerta de enlace de aplicación de telecomunicaciones (CSTA) compatible con el equipo para conectar Skype Empresarial Server con el sistema PBX. UCWA es un servicio introducido en versiones anteriores de Lync Server para habilitar la conectividad con clientes móviles y web, y se instala automáticamente en todos los servidores front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flujo de trabajo de llamada para una llamada a Través del trabajo

A continuación se muestra cómo un usuario habilitado para llamar a través del trabajo puede usar el Skype Empresarial Server realizar una llamada:
  
![Muestra los pasos durante una llamada a Través del trabajo; primero el autor de la llamada hace clic para llamar a alguien en el Skype Empresarial cliente; a continuación, la UCWA llama al teléfono del autor de la llamada. Cuando el autor de la llamada toma el teléfono, se llama al destinatario.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. El usuario selecciona un usuario en su Skype Empresarial y hace clic en el icono de teléfono para llamarlos. O bien, durante una conversación de mensajería instantánea, el usuario hace clic para llamar al usuario con el que está teniendo la sesión.
    
2. El teléfono PBX del usuario que ha realizado la llamada empieza a sonar. El identificador de autor de la llamada para este teléfono muestra un número de teléfono global que se ha configurado para que se muestre en el identificador de autor de la llamada de todos los usuarios que llaman a través del trabajo. Este número de teléfono global no es un número de teléfono real que corresponde al teléfono de una persona. En su lugar, es una señal visual para que un usuario sepa que esta es su propia llamada saliente y no una llamada entrante que se está produciendo al mismo tiempo. Cuando implemente Llamadas a través del trabajo, debe informar a los usuarios acerca de este número de teléfono global y lo que significa.
    
3. El usuario que ha realizado la llamada toma su teléfono PBX. Skype Empresarial inicia la llamada de voz al destinatario de la llamada. 
    
4. Cuando el destinatario responde, comienza la llamada de voz. Si los dos usuarios ya tenían una sesión de mi mi en marcha, puede continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Unirse a una conferencia con llamada a través del trabajo

Un usuario de Llamada a través del trabajo puede unirse a una reunión programada haciendo clic en la dirección URL de la reunión. Skype Empresarial muestra un **mensaje de** marcado hacia fuera hasta que el servicio de reunión marca el teléfono PBX del usuario. A continuación, el usuario Llamar a través del trabajo toma el teléfono PBX y se une a la reunión.
  
Un usuario de Llamada a través del trabajo también puede usar la opción **Reunirse ahora** en Skype Empresarial para crear reuniones de Meet Now. A continuación, el usuario ve el mensaje Marcar hacia **fuera** y el teléfono PBX suena.
  
Un usuario de Llamada a través del trabajo también puede llamar a una reunión llamando al número de puente de conferencia desde dentro de Skype Empresarial. Si se requiere un PIN de conferencia, el usuario debe usar su teléfono PBX para introducir el PIN.
  
### <a name="incoming-calls"></a>Llamadas entrantes

Cuando un usuario habilitado para llamar a través del trabajo recibe una llamada Skype Empresarial, el teléfono PBX y los clientes de Skype Empresarial del usuario suenan simultáneamente (si el usuario ha configurado un anillo simultáneo). El usuario puede aceptar la llamada seleccionando el teléfono PBX o haciendo clic en **Aceptar** en la Skype Empresarial llamada. Si el usuario acepta la llamada mediante Skype Empresarial, la Skype Empresarial de la llamada permanece abierta. Pero si el usuario acepta la llamada seleccionando el teléfono PBX, la ventana de notificación de Skype Empresarial se cierra y no hay ninguna sesión de Skype Empresarial, solo la llamada de voz a través del teléfono PBX.
  
Cuando un usuario habilitado para Llamar a través del trabajo recibe una llamada PBX, solo suena el teléfono PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitaciones de la llamada a través del trabajo

Call Via Work es una solución de voz que requiere poca configuración de hardware, pero tiene limitaciones en comparación con las características disponibles en el control de llamadas Telefonía IP empresarial o remoto. Llamar a través del trabajo tiene las siguientes limitaciones:
  
- Si un usuario de Llamada a través del trabajo ha configurado el reenvío de llamadas al número de devolución de llamada De llamada a través del trabajo y alguien intenta invitar a este usuario a una reunión por el número de teléfono del usuario, la invitación no llegará al usuario. Debe educar a los usuarios para que inviten a los participantes a las reuniones haciendo clic en el nombre, no en el número de teléfono. 
    
- La funcionalidad mejorada 911 y el seguimiento de llamadas malintencionadas no están disponibles durante las llamadas a través del trabajo.
    
- Los usuarios habilitados para Llamar a través del trabajo no pueden usar las características de delegación, llamada de equipo o grupo de respuesta.
    
- Los usuarios de Llamadas a través del trabajo no pueden usar Skype Empresarial para grabar una reunión, silenciar o desactivar la llamada, retener o transferir la llamada, ni usar el estacionamiento de llamadas.
    
- Los usuarios no pueden usar La llamada a través del trabajo para obtener acceso a sus mensajes de correo de voz PBX.
    
- Los usuarios de Llamada a través del trabajo no pueden escalar una sesión que se inició como llamada de voz a una reunión de colaboración que incluya comunicaciones como vídeo, Powerpoint, pizarra o Una nota.
    
- Los usuarios de Llamada a través del trabajo no pueden agregar más usuarios a una llamada de 2 personas.
    
- No se admite el emparejamiento de teléfonos de escritorio o el emparejamiento de complementos VDI.
    
- Si un usuario realiza o responde una llamada con el teléfono PBX (y no usa la ventana Skype Empresarial), no habrá ningún registro de la llamada.
    
- Si el sistema PBX no admite **REFER con Replaces,** se realizará el siguiente comportamiento. Mientras se realiza una llamada a través del trabajo, si el usuario transfiere la llamada en curso desde el Teléfono PBX, la ventana de llamada no desaparecerá de su ventana Skype Empresarial llamada. Si el usuario cierra la ventana de llamada, la llamada entre el destino de transferencia y el transferee finalizará. 
    
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para llamar a través del trabajo

Para habilitar cualquier usuario para llamar a través del trabajo, debe tener algunos requisitos previos en su lugar. Para obtener más información sobre estos requisitos previos y para ver los pasos para habilitar a los usuarios para llamadas a través del trabajo, vea [Deploy Call Via Work in Skype Empresarial Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Consulte también

[Planear el control remoto de llamadas en Skype Empresarial](remote-call-control.md)
  
[Implementar llamadas a través del trabajo en Skype Empresarial Server 2015](../../deploy/deploy-call-via-work.md)

