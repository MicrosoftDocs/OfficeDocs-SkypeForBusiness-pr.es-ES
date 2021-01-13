---
title: Proceso de implementación para la atención de llamadas grupales en Skype Empresarial
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
description: Proceso de implementación y pasos para la atención de llamadas grupales en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 5c89522828e5e5a0dc04ffccb0907c0a2cb8a008
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812350"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Proceso de implementación para la atención de llamadas grupales en Skype Empresarial
 
Proceso de implementación y pasos para la atención de llamadas grupales en Skype Empresarial Server Telefonía IP empresarial.
  
La atención de llamadas grupales permite a los usuarios responder llamadas entrantes a sus compañeros desde sus propios teléfonos. 
  
 Los componentes que usa la atención de llamadas grupales se instalan y habilitan automáticamente en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial. Sin embargo, debe seguir los pasos siguientes para configurar la atención de llamadas grupales antes de que esté disponible para los usuarios.
  
**Proceso de implementación de la atención de llamadas grupales**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar la herramienta SEFAUtil en la topología|Use el cmdlet New-CsTrustedApplicationPool para crear un nuevo grupo de aplicaciones de confianza. Use el cmdlet New-CsTrustedApplication para especificar la herramienta SEFAUtil como aplicación de confianza. Ejecute el cmdlet Enable-CsTopology para habilitar la topología. Si aún no la tiene, descargue la versión de Skype Empresarial Server de la herramienta SEFAUtil desde esta ubicación e instálel en el grupo de aplicaciones de confianza que creó en el paso 1. Compruebe que SEFAUtil se está ejecutando correctamente ejecutándose para mostrar la configuración de reenvío de llamadas de un usuario en la implementación. |RTCUniversalServerAdmins  <br/> |[Implementar la herramienta SEFAUtil en Skype Empresarial](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> Documentación de herramientas del kit de recursos de [Skype Empresarial Server 2015.](../../management-tools/resource-kit-tools.md) (Para Skype Empresarial Server debe usar la versión actual de la herramienta, pero esta documentación de Lync Server 2013 sigue vigente).  <br/> |
|Configurar intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas  <br/> |Use el cmdlet **New-CSCallParkOrbit** para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asignar a los intervalos de atención de llamadas el tipo **GroupPickup**.  <br/> Para una integración sin problemas con los planes de marcado existentes, los intervalos de números suelen configurarse como un bloque de extensiones virtuales. No se admite la asignación de números de llamada directa a la extensión (DID) como números de intervalo en la tabla de órbitas de estacionamiento de llamadas.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un intervalo de números de atención de llamadas grupales en Skype Empresarial](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Asignar un número de atención de llamadas a los usuarios y habilitar la atención de llamadas grupales para los usuarios  <br/> |Use el parámetro /enablegrouppickup en la herramienta del kit de recursos SEFAUtil para habilitar la atención de llamadas grupales y asignar un número de atención de llamadas para los usuarios.  <br/> |-  <br/> |[Habilitar la atención de llamadas grupales para los usuarios y asignar un número de grupo en Skype Empresarial](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar a los usuarios el número de atención de llamadas asignado y cualquier otro número de interés  <br/> |Después de habilitar la atención de llamadas grupales para los usuarios, use el correo electrónico u otro mecanismo para notificar a los usuarios su número de grupo de atención de llamadas. Notificar a los usuarios el número de grupo de atención de llamadas de cualquier grupo que quieran supervisar. Dado que los usuarios pueden recuperar llamadas de otros usuarios aunque no estén en el mismo grupo, es posible que los usuarios necesiten el número de grupo de atención de llamadas para varios grupos.  <br/> |-  <br/> ||
|Comprobar la implementación de la atención de llamadas grupales  <br/> | Prueba la realización y recuperación de llamadas para asegurarte de que la configuración funciona según lo esperado. Como mínimo, compruebe lo siguiente: <br/>  Llame a un usuario habilitado para la atención de llamadas grupales y haga que otro usuario recupere la llamada. El otro usuario puede estar en el mismo grupo, en un grupo diferente o no tener habilitada la atención de llamadas grupales. <br/>  Llame a un usuario habilitado para la atención de llamadas grupales y no responda a la llamada. <br/> |-  <br/> ||
   

