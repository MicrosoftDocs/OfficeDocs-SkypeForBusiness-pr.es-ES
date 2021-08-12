---
title: Proceso de implementación para la recogida de llamadas de grupo en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Proceso de implementación y pasos para la recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: c802f36594704625258da31d18171499315f7e2f1c93020ba71ab42ebb3d97e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280315"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Proceso de implementación para la recogida de llamadas de grupo en Skype Empresarial
 
Proceso de implementación y pasos para la recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.
  
La recogida de llamadas en grupo permite a los usuarios responder llamadas entrantes a sus compañeros desde sus propios teléfonos. 
  
 Los componentes que usa la recogida de llamadas de grupo se instalan automáticamente y se habilitan en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial. Sin embargo, debe seguir los siguientes pasos para configurar la recogida de llamadas de grupo antes de que esté disponible para los usuarios.
  
**Proceso de implementación de la recogida de llamadas en grupo**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar la herramienta SEFAUtil en la topología|Use el cmdlet New-CsTrustedApplicationPool para crear un nuevo grupo de aplicaciones de confianza. Use el cmdlet New-CsTrustedApplication para especificar la herramienta SEFAUtil como aplicación de confianza. Ejecute el cmdlet Enable-CsTopology para habilitar la topología. Si aún no la tiene, descargue la versión Skype Empresarial Server de la herramienta SEFAUtil desde esta ubicación e instálesla en el grupo de aplicaciones de confianza que creó en el paso 1. Compruebe que SEFAUtil se ejecuta correctamente ejecutándose para mostrar la configuración de reenvío de llamadas de un usuario en la implementación. |RTCUniversalServerAdmins  <br/> |[Implementar la herramienta SEFAUtil en Skype Empresarial](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> Skype Empresarial Server de herramientas del [kit de recursos de 2015](../../management-tools/resource-kit-tools.md). (Por Skype Empresarial Server debe usar la versión actual de la herramienta, pero esta documentación de Lync Server 2013 todavía se aplica).  <br/> |
|Configurar intervalos de números de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas  <br/> |Use el cmdlet **New-CSCallParkOrbit** para crear intervalos de números de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas y asignar los intervalos de recogida de llamadas al tipo **GroupPickup**.  <br/> Para una integración perfecta con los planes de marcado existentes, los intervalos de números suelen configurarse como un bloque de extensiones virtuales. No se admite la asignación de números de marcado directo interno (DID) como números de intervalo en la tabla de órbitas de estacionamiento de llamadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un intervalo de números de recogida de llamadas de grupo en Skype Empresarial](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Asignar un número de recogida de llamadas a los usuarios y habilitar la recogida de llamadas de grupo para los usuarios  <br/> |Use el parámetro /enablegrouppickup en la herramienta del kit de recursos SEFAUtil para habilitar la recogida de llamadas de grupo y asignar un número de recogida de llamadas para los usuarios.  <br/> |-  <br/> |[Habilitar la recogida de llamadas de grupo para los usuarios y asignar un número de grupo en Skype Empresarial](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar a los usuarios su número de recogida de llamadas asignado y cualquier otro número de interés  <br/> |Después de habilitar la recogida de llamadas de grupo para los usuarios, use el correo electrónico u otro mecanismo para notificar a los usuarios su número de grupo de recogida de llamadas. Notifique a los usuarios el número de grupo de recogida de llamadas para cualquier grupo que desee supervisar. Dado que los usuarios pueden recuperar llamadas para otros usuarios incluso si no están en el mismo grupo, es posible que los usuarios necesiten el número de grupo de recogida de llamadas para varios grupos.  <br/> |-  <br/> ||
|Comprobar la implementación de la recogida de llamadas de grupo  <br/> | Pruebe la colocación y recuperación de llamadas para asegurarse de que la configuración funciona según lo esperado. Como mínimo, compruebe lo siguiente: <br/>  Llame a un usuario habilitado para la recogida de llamadas de grupo y haga que otro usuario recupere la llamada. El otro usuario puede estar en el mismo grupo, en un grupo diferente o no tener habilitada la recogida de llamadas de grupo. <br/>  Llama a un usuario que está habilitado para la recogida de llamadas en grupo y no responde a la llamada. <br/> |-  <br/> ||
