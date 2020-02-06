---
title: Asignar directivas de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumen: Aprenda a asignar directivas de conferencia en Skype empresarial Server.'
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818662"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Asignar directivas de conferencia en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo asignar directivas de conferencia en Skype empresarial Server.
  
Puede asignar directivas de conferencia a los usuarios mediante el shell de administración de Skype empresarial Server y el cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Asignar directivas de Conferencia mediante el shell de administración de Skype empresarial Server

En el siguiente ejemplo, la directiva SalesConferencingPolicy se asigna al usuario con el parámetro Identity "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

En el siguiente ejemplo, la directiva de conferencia FinanceConferencingPolicy se asigna a todos los usuarios que tienen cuentas en la unidad organizativa Finance. A fin de asignar la misma directiva a todos los usuarios en determinada unidad organizativa (OU), se usa el cmdlet Get-CsUser para recuperar todas las cuentas en esa OU. Después de que se hayan recuperado todas las cuentas de usuario, esa información se redirecciona al cmdlet Grant-CsConferencingPolicy, que asigna la directiva FinanceConferencingPolicy a cada usuario en la colección.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

