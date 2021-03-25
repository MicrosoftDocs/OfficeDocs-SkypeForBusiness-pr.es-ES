---
title: Administrar las opciones de configuración de reuniones en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: obtenga información sobre cómo administrar las opciones de configuración de reuniones en Skype Empresarial Server.'
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119439"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Administrar las opciones de configuración de reuniones en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar las opciones de configuración de reuniones en Skype Empresarial Server.
  
En este tema se describe cómo administrar las opciones de configuración de reuniones. Para obtener más información sobre cómo planear e implementar conferencias, vea [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de reunión determinan el tipo de reuniones que los usuarios pueden crear, además de controlar cómo (o incluso si) los usuarios anónimos y los usuarios de conferencias de acceso telefónico local pueden unirse a estas reuniones. Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype Empresarial.
  
Las opciones de configuración de reunión definen lo siguiente:
  
- Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan a la sala de espera.
    
- Quién puede ser moderador.
    
- Si el tipo de conferencia está asignado de forma predeterminada.
    
- Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.
    
Puede definir las características de las reuniones mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server. 
  
Puede especificar la configuración de reunión en el nivel global (creado de forma predeterminada), el nivel de sitio o el nivel de grupo. De forma predeterminada, la configuración global define la experiencia de reunión. Si crea una configuración en el nivel de grupo de servidores, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración en el nivel de grupo de servidores, se aplicará la configuración del nivel de sitio, si existe. Si no define la configuración en el nivel de sitio, se aplicará la configuración global a todas las reuniones.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Administrar la configuración de la reunión mediante el Panel de control de Skype Empresarial Server

Para administrar la configuración de reuniones mediante el Panel de control de Skype Empresarial Server:
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Administrar la configuración de reuniones mediante el Shell de administración de Skype Empresarial Server

Para administrar reuniones mediante el Shell de administración de Skype Empresarial Server, use los cmdlets siguientes:
  
**Opciones de configuración de reuniones**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reunión que se usan actualmente en la organización.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito de sitio o de servicio.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reunión que se usan actualmente en la organización.  <br/> |
