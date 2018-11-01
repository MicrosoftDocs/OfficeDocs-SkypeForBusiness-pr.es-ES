---
title: Cmdlets que no usan ámbitos ni identidades
TOCTitle: Cmdlets que no usan ámbitos ni identidades
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56271330
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets que no usan ámbitos ni identidades

 

_**Última modificación del tema:** 2015-06-22_

Los cmdlets que se usan al modificar las listas de dominios permitidos y bloqueados (listas que determinan con qué organizaciones externas se pueden comunicar los usuarios) no usan ámbitos ni el parámetro Identity. De hecho, el cmdlet **New-CsEdgeAllowAllKnownDomains** no incluye absolutamente ningún parámetro. Los cmdlets que no usan ámbitos ni el parámetro Identity son los siguientes:

  - [New-CsEdgeAllowAllKnownDomains](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowAllKnownDomains)

  - [New-CsEdgeAllowList](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowList)

  - [New-CsEdgeDomainPattern](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeDomainPattern)

Tenga en cuenta que en los cmdlets **New-CsEdgeAllowList** y **New-CsEdgeDomainPattern** debe incluir el parámetro Domain. Por ejemplo:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

