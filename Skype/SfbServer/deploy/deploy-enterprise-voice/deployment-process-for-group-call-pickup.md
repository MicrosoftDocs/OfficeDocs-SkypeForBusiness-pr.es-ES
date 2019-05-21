---
title: Proceso de implementación para la recogida de llamadas grupales en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Proceso de implementación y pasos para la recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289927"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Proceso de implementación para la recogida de llamadas grupales en Skype empresarial
 
Proceso de implementación y pasos para la recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial.
  
La recogida de llamada grupal permite a los usuarios contestar llamadas entrantes a sus colegas desde sus propios teléfonos. 
  
 Los componentes que usa la recogida de llamadas grupales se instalan y se habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial. Sin embargo, debe seguir estos pasos para configurar la recogida de llamadas grupales antes de que esté disponible para los usuarios.
  
**Proceso de implementación de la atención de llamadas grupales**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar la herramienta SEFAUtil en su topología|Use el cmdlet New-CsTrustedApplicationPool para crear un nuevo grupo de aplicaciones de confianza. Use el cmdlet New-CsTrustedApplication para especificar la herramienta SEFAUtil como aplicación de confianza. Ejecute el cmdlet enable-CsTopology para habilitar la topología. Si aún no la tiene, descargue la versión de Skype empresarial Server de la herramienta SEFAUtil desde esta ubicación e instálela en el grupo de aplicaciones de confianza que creó en el paso 1. Compruebe que SEFAUtil se esté ejecutando correctamente; para ello, ejecútelo para mostrar la configuración de desvío de llamadas de un usuario de la implementación. |RTCUniversalServerAdmins  <br/> |[Implementar la herramienta SEFAUtil en Skype empresarial](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentación de las herramientas del kit de recursos de Skype empresarial Server 2015](../../management-tools/resource-kit-tools.md). (Para Skype empresarial Server debe usar la versión actual de la herramienta, pero aún se aplica esta documentación de Lync Server 2013).  <br/> |
|Configurar los intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas  <br/> |Use el cmdlet **New-CSCallParkOrbit** para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asígneles el tipo **GroupPickup**.  <br/> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de intervalo.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un intervalo de números de recogida de llamadas grupales en Skype empresarial](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Asignar un número de llamada a los usuarios y habilitar la recogida de llamadas grupales para los usuarios  <br/> |Use el parámetro/enablegrouppickup en la herramienta del kit de recursos de SEFAUtil para habilitar la recogida de llamadas grupales y asignar un número de llamada para los usuarios.  <br/> |-  <br/> |[Habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo en Skype empresarial](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar a los usuarios el número de atención de llamadas que se les ha asignado y cualquier otro número de interés  <br/> |Después de habilitar la respuesta de llamadas en grupo para los usuarios, utilice el correo electrónico o algún otro mecanismo para notificarles el número del grupo de respuesta de llamadas. Notifique a los usuarios de este grupo el número de cualquier otro grupo que deseen supervisar. Como los usuarios pueden recuperar llamadas para otros usuarios aunque no estén en el mismo grupo, probablemente necesiten los números de varios grupos.  <br/> |-  <br/> ||
|Verificar la implementación de la recogida de llamadas grupales  <br/> | Realice pruebas de llamadas y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado. Como mínimo, compruebe lo siguiente: <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y haga que otro usuario responda a la llamada. El otro usuario puede pertenecer al mismo grupo, a un grupo diferente, o no tener activada la respuesta de llamadas en grupo. <br/>  Llame a un usuario que tenga activada la respuesta de llamadas en grupo y no responda a la llamada. <br/> |-  <br/> ||
   

