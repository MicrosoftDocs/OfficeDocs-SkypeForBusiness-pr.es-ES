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
description: 'Resumen: Conozca cómo asignar directivas de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 532065bee6f33b492639f5bcf949e29b082c5e84
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a>Asignar directivas de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo asignar directivas de conferencia en Skype para Business Server 2015.
  
Puede asignar directivas de conferencias a los usuarios con Skype de Shell de administración de servidor empresarial y el cmdlet de **Concesión CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Asignar directivas de conferencias mediante Skype para el Shell de administración de servidor empresarial

En el siguiente ejemplo, la directiva SalesConferencingPolicy se asigna al usuario con el parámetro Identity "Ken Myer":
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy

```

En el siguiente ejemplo, la directiva de conferencia FinanceConferencingPolicy se asigna a todos los usuarios que tienen cuentas en la unidad organizativa Finance. A fin de asignar la misma directiva a todos los usuarios en determinada unidad organizativa (OU), se usa el cmdlet Get-CsUser para recuperar todas las cuentas en esa OU. Después de que se hayan recuperado todas las cuentas de usuario, esa información se redirecciona al cmdlet Grant-CsConferencingPolicy, que asigna la directiva FinanceConferencingPolicy a cada usuario en la colección.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy

```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, vea [Grant CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

