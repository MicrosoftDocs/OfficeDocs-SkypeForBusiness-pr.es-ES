---
title: Cmdlets de Skype empresarial online que no usan un ámbito ni una identidad
description: Cmdlets de Skype empresarial online que no usan un ámbito ni una identidad.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545726"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlets de Skype empresarial online que no usan un ámbito ni una identidad

 


Los cmdlets que se usan cuando se modifican las listas permitidas y las listas bloqueadas (listas que determinan a las organizaciones externas con las que los usuarios pueden comunicarse) no usan ni un ámbito ni una identidad. De hecho, el cmdlet **New-CsEdgeAllowAllKnownDomains** no tiene ningún parámetro en absoluto. Los cmdlets que no usan ni un ámbito ni una identidad son:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

Tenga en cuenta que, con el cmdlet **New-CsEdgeAllowList** y el cmdlet **New-CsEdgeDomainPattern** , debe incluir el parámetro domain. Por ejemplo:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Vea también


[Identidades, ámbitos e inquilinos en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

