---
title: Administrar opciones de configuración en Skype para Business Server de la reunión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Obtenga información sobre cómo administrar los valores de configuración de Skype para Business Server de la reunión.'
ms.openlocfilehash: 2e4a3dae9eac83b94f6623faf07e5ee6e8e346db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888180"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Administrar opciones de configuración en Skype para Business Server de la reunión
 
**Resumen:** Obtenga información sobre cómo administrar los valores de configuración de Skype para Business Server de la reunión.
  
This topic describes how to manage meeting configuration settings. Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencias en Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a las reuniones de ad-hoc creadas haciendo clic en la opción Reunirse ahora en Skype para la empresa.
  
Las opciones de configuración de reuniones definen lo siguiente:
  
- Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.
    
- Quién puede ser moderador.
    
- Si el tipo de conferencia está asignado de forma predeterminada.
    
- Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.
    
Puede definir las características de las reuniones mediante Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial. 
  
Puede especificar opciones en el nivel global (creada de manera predeterminada) de la reunión, nivel de sitio o del nivel de grupo de servidores. De forma predeterminada, la configuración global define la experiencia de la reunión. Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe. Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Administrar la configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial

Para administrar la configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Administrar la configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial

Para administrar las reuniones mediante el uso de Skype para Shell de administración de servidor empresarial, use los cmdlets siguientes:
  
**Opciones de configuración de reuniones**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
   

