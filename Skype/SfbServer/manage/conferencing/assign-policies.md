---
title: Asignar directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumen: Obtenga información sobre cómo asignar directivas de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 22e82ef12c8ec6dc0c9029c0c8f2861fd5578509
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568810"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a>Asignar directivas de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo asignar directivas de conferencia en Skype para Business Server 2015.
  
Puede asignar directivas de conferencia a los usuarios con Skype para Shell de administración de servidor empresarial y el cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Asignar directivas de conferencia mediante Skype para Shell de administración de servidor empresarial

En el siguiente ejemplo, la directiva SalesConferencingPolicy se asigna al usuario con el parámetro Identity "Ken Myer":
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

En el siguiente ejemplo, la directiva de conferencia FinanceConferencingPolicy se asigna a todos los usuarios que tienen cuentas en la unidad organizativa Finance. A fin de asignar la misma directiva a todos los usuarios en determinada unidad organizativa (OU), se usa el cmdlet Get-CsUser para recuperar todas las cuentas en esa OU. Después de que se hayan recuperado todas las cuentas de usuario, esa información se redirecciona al cmdlet Grant-CsConferencingPolicy, que asigna la directiva FinanceConferencingPolicy a cada usuario en la colección.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, vea [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

