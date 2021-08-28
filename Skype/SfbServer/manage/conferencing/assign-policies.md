---
title: Asignar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumen: obtenga información sobre cómo asignar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 3ae21518cf53aad48d4fc9b6963d0e5402007db9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635284"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Asignar directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo asignar directivas de conferencia en Skype Empresarial Server.
  
Puede asignar directivas de conferencia a los usuarios mediante Skype Empresarial Server Shell de administración y el cmdlet **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Asignar directivas de conferencia mediante Skype Empresarial Server Shell de administración

En el siguiente ejemplo, la directiva SalesConferencingPolicy se asigna al usuario con la identidad "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

En el siguiente ejemplo, la directiva de conferencia FinanceConferencingPolicy se asigna a todos los usuarios que tienen cuentas en la unidad organizativa Finanzas. A fin de asignar la misma directiva a todos los usuarios en determinada unidad organizativa (OU), se usa el cmdlet Get-CsUser para recuperar todas las cuentas en esa OU. Una vez recuperadas las cuentas de usuario, esa información se canalizará al cmdlet Grant-CsConferencingPolicy, que asigna la directiva FinanceConferencingPolicy a cada usuario de la colección:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, [vea Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
