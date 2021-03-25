---
title: Habilitar o deshabilitar conferencias de acceso telefónico local en Skype Empresarial Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Summary: Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119469"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar o deshabilitar conferencias de acceso telefónico local en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo usar el Panel de control o el Shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype Empresarial Server.
  
Puede habilitar las conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar o deshabilitar conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**
    
4. En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia con acceso telefónico, haga clic en **Editar** y luego en **Mostrar detalles**. 
    
5. Para permitir que los usuarios se unan a la reunión con acceso telefónico, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones mediante la red telefónica conmutada (RTC).
    
6. Haga clic en **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar o deshabilitar conferencias de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server

Para habilitar o deshabilitar las conferencias de acceso telefónico local, use el cmdlet **Set-CsConferencingPolicy** con el parámetro EnableDialInConferencing de la siguiente manera:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obtener más información, [vea Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
