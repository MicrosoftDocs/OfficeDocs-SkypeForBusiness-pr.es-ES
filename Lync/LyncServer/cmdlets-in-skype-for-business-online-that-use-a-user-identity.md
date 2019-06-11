---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0086f4b04dd199a285820db811a57899cdc0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Cmdlets de Skype empresarial online que usan una identidad de usuario

 


En Skype empresarial online, hay varias maneras de hacer referencia a una identidad de usuario individual:

  - Use el nombre para mostrar de los servicios de dominio de Active Directory del usuario. Por ejemplo:
    
        -Identity "Ken Myer"

  - Use la dirección SIP del usuario. Por ejemplo:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Use el UPN del usuario. Por ejemplo:
    
        -Identity " kenmyer@litwareinc.com"

  - Use el nombre completo de los servicios de dominio de Active Directory del usuario. Por ejemplo:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Los siguientes cmdlets aceptan una identidad de usuario:

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))

Tenga en cuenta que no es necesario especificar una identidad de usuario al llamar a uno de los cmdlets **Get-CS** . En este caso, los cmdlets devuelven todas las instancias del elemento especificado. Por ejemplo, este comando devuelve información acerca de todos los usuarios que se han habilitado para Skype empresarial online:

    Get-CsOnlineUser

El parámetro Identity solo es necesario si desea devolver información para un usuario específico:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Vea también


[Identidades, ámbitos y espacios empresariales en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

