---
title: Proceso de implementación de la atención de llamadas grupales en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Proceso de implementación y los pasos para la recogida de grupo llamar en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 1e87b475e5628aa9df46d025c95d80dc355c6567
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business-2015"></a>Deployment process for Group Call Pickup in Skype for Business 2015
 
Proceso de implementación y los pasos para la recogida de grupo llamar en Skype para Telefonía IP empresarial de Business Server.
  
Recogida de llamar a grupo permite a los usuarios contestar las llamadas entrantes a sus compañeros desde sus propios teléfonos. 
  
 Los componentes que usa el grupo llamar recogida automáticamente instalados y habilitados en el servidor Standard Edition o de servidor Front-End al implementar la Telefonía IP empresarial. Sin embargo, debe utilizar los pasos siguientes para configurar el grupo llamar recogida antes de que esté disponible para los usuarios.
  
**Proceso de implementación de recogida de llamada de grupo**

|**Fase**|**Pasos**|**Roles y grupos requeridos**|**Documentación sobre la implementación**|
|:-----|:-----|:-----|:-----|
|Activar la herramienta de SEFAUtil de la topología  <br/> |
Utilice el cmdlet New-CsTrustedApplicationPool para crear un nuevo grupo de aplicaciones de confianza. Utilice el cmdlet New-CsTrustedApplication para especificar la herramienta SEFAUtil como aplicación de confianza. Ejecute el cmdlet Enable-CsTopology para habilitar la topología. Si ya no tienes, descargar el Skype para la versión de la herramienta SEFAUtil Business Server desde esta ubicación e instalarlo en el grupo de aplicaciones de confianza que creó en el paso 1. Compruebe que SEFAUtil se esté ejecutando correctamente; para ello, ejecútelo para mostrar la configuración de desvío de llamadas de un usuario de la implementación. |RTCUniversalServerAdmins  <br/> |[Implementar la herramienta SEFAUtil en Skype para negocios 2015](deploy-the-sefautil-tool.md) <br/> [Nueva CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) [Nueva CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps) [Habilitar CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentación de herramienta del kit de recursos de Lync Server 2013](https://technet.microsoft.com/en-us/library/jj945604%28v=ocs.15%29.aspx). (Para Skype para Business Server debe utilizar la versión actual de la herramienta, pero esta documentación de Lync Server 2013 todavía se aplica.  <br/> |
|Configurar los intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas  <br/> |Utilice el cmdlet **New-CSCallParkOrbit** para crear intervalos numéricos de llamada recogida en la tabla de órbita llamada park y asignarles los rangos de recogida de llamada del tipo **GroupPickup**.  <br/> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de intervalo.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un rango de números de grupo llamar recogida en Skype para negocios 2015](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Asignar a un número de llamada de recogida a los usuarios y habilitar recogida de llamar al grupo para los usuarios  <br/> |Utilice el parámetro /enablegrouppickup en la herramienta del kit de recursos de SEFAUtil para habilitar la recogida de llamar al grupo y asignar a un número de llamada de recogida para los usuarios.  <br/> |-  <br/> |[Habilitar recogida de llamar al grupo para los usuarios y asignar a un número de grupo en Skype para negocios 2015](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar a los usuarios el número de atención de llamadas que se les ha asignado y cualquier otro número de interés  <br/> |Después de habilitar la respuesta de llamadas en grupo para los usuarios, utilice el correo electrónico o algún otro mecanismo para notificarles el número del grupo de respuesta de llamadas. Notifique a los usuarios de este grupo el número de cualquier otro grupo que deseen supervisar. Como los usuarios pueden recuperar llamadas para otros usuarios aunque no estén en el mismo grupo, probablemente necesiten los números de varios grupos.  <br/> |-  <br/> ||
|Comprobar la distribución de grupo llame al recoger el artículo  <br/> | Realice pruebas de llamadas y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado. Como mínimo, compruebe lo siguiente: <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y haga que otro usuario responda a la llamada. El otro usuario puede pertenecer al mismo grupo, a un grupo diferente, o no tener activada la respuesta de llamadas en grupo. <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y no responda a la llamada. <br/> |-  <br/> ||
   

