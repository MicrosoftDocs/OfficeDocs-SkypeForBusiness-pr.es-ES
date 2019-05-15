---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 815a35efbce89404b012d5534e257752bef8d53e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886385"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar PowerShell para controlar el acceso de invitado a un equipo
================================================

Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory, puede usar Windows PowerShell para controlar el acceso de invitado. Con PowerShell, puede hacer lo siguiente:
  
- Permitir o bloquear el acceso de invitado a todos los equipos y grupos de Office 365
    
- Permitir que se puedan agregar invitados a todos los equipos y grupos de Office 365
      
- Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365
    
Para obtener información detallada, vea la sección "Uso de PowerShell para controlar el acceso de invitado" en la ficha administrar de [acceso como invitado en grupos de Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio. Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam). Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos. Para obtener más información, vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Si desea bloquear los invitados en los equipos y desea que puedan obtener acceso a sitios de SharePoint, puede usar los cmdlets de Powershell de Azure Active Directory para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto de la compañía, suponiendo que está activado el uso compartido externo para Sitios de SharePoint.   

## <a name="guest-access-vs-external-access"></a>Acceso de invitado frente a acceso externo

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
