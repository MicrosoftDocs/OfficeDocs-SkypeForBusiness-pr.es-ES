---
title: Cmdlets que usan identidades de proveedores de servicios de conferencia
TOCTitle: Cmdlets que usan identidades de proveedores de servicios de conferencia
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56271351
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets que usan identidades de proveedores de servicios de conferencia

 

_**Última modificación del tema:** 2015-06-22_

Para devolver información sobre todos los proveedores de audioconferencia que tienen contrato con la organización, simplemente llame al cmdlet [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider) sin ningún parámetro:

    Get-CsAudioConferencingProvider

Si quiere limitar los datos devueltos a un solo proveedor (en este ejemplo, Contoso Audio Services), use el parámetro Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Solo hay un cmdlet de Skype Empresarial Online que acepta identificadores de proveedor de audioconferencia:

  - [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider)

## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

