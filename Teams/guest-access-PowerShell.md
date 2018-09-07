---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
search.appverid: MET150
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a21333fb4d3f626b1f989ac103db73b87c985ce2
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867552"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar PowerShell para controlar el acceso de invitado a un equipo
================================================

Además de usar el Centro de administración de Office 365 y el portal de Azure Active Directory, puede usar Windows PowerShell para controlar el acceso de invitado. Con PowerShell, puede hacer lo siguiente:
  
  
   

- Permitir o bloquear el acceso de invitado a todos los equipos y grupos de Office 365
    
  
- Permitir que se puedan agregar invitados a todos los equipos y grupos de Office 365
    
  
- Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365
    
  
Para obtener más información, consulte la sección "Usar PowerShell para controlar el acceso de invitado" en la ficha Administrar de [Acceso de invitado en Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
    
    
También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio. Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam). Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos. Para obtener más información, vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Si desea bloquear a invitados en los equipos y seguir permitiendo que los invitados tengan acceso a sitios de SharePoint, puede usar los cmdlets de Azure Active Directory PowerShell para deshabilitar el parámetro AllowGuestAccessToGroups en el objeto de empresa, siempre que el uso compartido externo esté activado para los sitios de SharePoint.   

