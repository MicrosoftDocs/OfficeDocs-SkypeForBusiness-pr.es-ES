---
title: Cmdlets de Skype empresarial online que no usan un ámbito o una identidad
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727600"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlets de Skype empresarial online que no usan un ámbito o una identidad

 


Los cmdlets que se usan al modificar las listas permitidas y las listas bloqueadas (listas que determinan de qué organizaciones externas a las que los usuarios pueden comunicarse) no usan un ámbito ni una identidad. De hecho, el cmdlet **New-CsEdgeAllowAllKnownDomains** no tiene ningún parámetro. Los cmdlets que no usan un ámbito o una identidad son:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

Tenga en cuenta que, con el cmdlet **New-CsEdgeAllowList** y el cmdlet **New-CsEdgeDomainPattern** , debe incluir el parámetro domain. Por ejemplo:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Vea también


[Identidades, ámbitos y espacios empresariales en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

