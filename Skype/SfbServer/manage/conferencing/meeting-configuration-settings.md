---
title: Administrar la configuración de la reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Obtenga información sobre cómo administrar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283742"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Administrar la configuración de la reunión en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar la configuración de la reunión en Skype empresarial Server.
  
This topic describes how to manage meeting configuration settings. Para obtener más información sobre cómo planear e implementar conferencias, consulte [planear la Conferencia en Skype empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) e [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad-hoc creadas al hacer clic en la opción reunirse ahora en Skype empresarial.
  
Las opciones de configuración de reuniones definen lo siguiente:
  
- Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.
    
- Quién puede ser moderador.
    
- Si el tipo de conferencia está asignado de forma predeterminada.
    
- Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.
    
Puede definir las características de las reuniones con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server. 
  
Puede especificar la configuración de la reunión en el nivel global (creado de forma predeterminada), en el nivel de sitio o en el nivel de grupo. De forma predeterminada, la configuración global define la experiencia de la reunión. Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe. Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Administrar la configuración de la reunión con el panel de control de Skype empresarial Server

Para administrar la configuración de la reunión con el panel de control de Skype empresarial Server:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Administrar la configuración de la reunión con el shell de administración de Skype empresarial Server

Para administrar las reuniones con el shell de administración de Skype empresarial Server, use los siguientes cmdlets:
  
**Opciones de configuración de reuniones**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
   

