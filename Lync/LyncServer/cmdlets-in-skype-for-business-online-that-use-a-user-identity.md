---
title: Cmdlets que usan identidades de usuario
TOCTitle: Cmdlets que usan identidades de usuario
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56271347
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets que usan identidades de usuario

 

_**Última modificación del tema:** 2015-06-22_

Skype Empresarial Online permite hacer referencia al parámetro Identity de un usuario individual de varias formas:

  - Use el nombre para mostrar de Servicios de dominio de Active Directory del usuario. Por ejemplo:
    
        -Identity "Ken Myer"

  - Use la dirección SIP del usuario. Por ejemplo:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Use el UPN del usuario. Por ejemplo:
    
        -Identity " kenmyer@litwareinc.com"

  - Use el nombre distintivo (DN) de Servicios de dominio de Active Directory del usuario. Por ejemplo:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Los cmdlets siguientes aceptan el parámetro Identity de usuario:

  - [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom)

  - [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom)

  - [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact)

  - [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom)

  - [Get-CsOnlineUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsOnlineUser?view=skype-ps)

  - [Get-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUserAcp)

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Remove-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExUmContact)

  - [Remove-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUserAcp)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

  - [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom)

  - [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp)

Tenga en cuenta que no es necesario especificar el parámetro Identity de usuario al llamar a los cmdlets **Get-Cs**. Estos cmdlets devuelven todas las instancias del elemento especificado. Por ejemplo, este comando devuelve información sobre todos los usuarios que se han habilitado para Skype Empresarial Online:

    Get-CsOnlineUser

El parámetro Identity solo se requiere para devolver información de un usuario específico:

    Get-CsOnlineUser -Identity "Ken Myer"

## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

