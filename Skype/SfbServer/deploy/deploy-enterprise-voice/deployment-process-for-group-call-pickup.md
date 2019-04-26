---
title: Proceso de implementación de grupo de llamada recogida en Skype para la empresa
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Proceso de implementación y los pasos para el grupo de llamada recogida en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 92dbb6ef4a96ed4972794a61814abcd31586ffb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223065"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Proceso de implementación de grupo de llamada recogida en Skype para la empresa
 
Proceso de implementación y los pasos para el grupo de llamada recogida en Skype para Business Server Enterprise Voice.
  
Recogida de llamadas de grupo permite a los usuarios responder a las llamadas entrantes a sus compañeros de trabajo desde sus propios teléfonos. 
  
 Los componentes que usa el grupo llamar recogida automáticamente instalados y habilitados en el servidor Front-End o Standard Edition al implementar Enterprise Voice. Sin embargo, debe usar los siguientes pasos para configurar el grupo llamar recogida antes de que esté disponible para los usuarios.
  
**Proceso de implementación de la atención de llamadas grupales**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar la herramienta de SEFAUtil en su topología|Use el cmdlet New-CsTrustedApplicationPool para crear un nuevo grupo de aplicaciones de confianza. Use el cmdlet New-CsTrustedApplication para especificar la herramienta SEFAUtil como aplicación de confianza. Ejecute el cmdlet Enable-CsTopology para habilitar la topología. Si ya no tienes, descargar el Skype para la versión de la herramienta SEFAUtil Business Server desde esta ubicación e instalarlo en el grupo de servidores de aplicaciones de confianza que ha creado en el paso 1. Compruebe que SEFAUtil se esté ejecutando correctamente; para ello, ejecútelo para mostrar la configuración de desvío de llamadas de un usuario de la implementación. |RTCUniversalServerAdmins  <br/> |[Implementar la herramienta SEFAUtil en Skype para la empresa](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentación de las herramientas Skype for Business Server 2015 Resource Kit](../../management-tools/resource-kit-tools.md). (Para Skype para Business Server debe usar la versión actual de la herramienta, pero aún se aplica esta documentación de Lync Server 2013).  <br/> |
|Configurar los intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas  <br/> |Use el cmdlet **New-CSCallParkOrbit** para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asígneles el tipo **GroupPickup**.  <br/> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de intervalo.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creación o modificación de un intervalo de números de grupo llamada recogida en Skype para la empresa](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Asignar a un número de llamada de recogida a los usuarios y habilitar recogida de llamadas de grupo para los usuarios  <br/> |Use el parámetro /enablegrouppickup en la herramienta del kit de recursos de SEFAUtil para habilitar recogida de llamadas de grupo y asignar a un número de recogida de llamada para los usuarios.  <br/> |-  <br/> |[Habilitar la recogida de llamadas de grupo para los usuarios y asignar a un número de grupo en Skype para la empresa](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar a los usuarios el número de atención de llamadas que se les ha asignado y cualquier otro número de interés  <br/> |Después de habilitar la respuesta de llamadas en grupo para los usuarios, utilice el correo electrónico o algún otro mecanismo para notificarles el número del grupo de respuesta de llamadas. Notifique a los usuarios de este grupo el número de cualquier otro grupo que deseen supervisar. Como los usuarios pueden recuperar llamadas para otros usuarios aunque no estén en el mismo grupo, probablemente necesiten los números de varios grupos.  <br/> |-  <br/> ||
|Comprobar la implementación de recogida de llamadas de grupo  <br/> | Realice pruebas de llamadas y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado. Como mínimo, compruebe lo siguiente: <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y haga que otro usuario responda a la llamada. El otro usuario puede pertenecer al mismo grupo, a un grupo diferente, o no tener activada la respuesta de llamadas en grupo. <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y no responda a la llamada. <br/> |-  <br/> ||
   

