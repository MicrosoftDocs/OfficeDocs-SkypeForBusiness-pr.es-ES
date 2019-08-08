---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f6b76b6c63b39bf22f456260f084736d481513
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233130"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta

 


Los cmdlets **Grant-CS** (que se usan para asignar directivas a los usuarios) requieren dos identificadores: una identidad de usuario (el parámetro Identity) y la identidad de una directiva por usuario (el parámetro PolicyName). Por ejemplo, para asignar la Directiva de voz, RedmondVoicePolicy, al usuario Ken Myer, use el siguiente comando:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Hay dos cosas que se deben tener en cuenta al asignar directivas a los usuarios. En primer lugar, solo se pueden asignar directivas por usuario. No se puede asignar la directiva global a un usuario. Por ejemplo, este comando fallará:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Este comando falla porque no es necesario asignar la directiva global. Si desea administrar un usuario mediante la directiva global, asegúrese de no asignarle a ese usuario una directiva por usuario. Si no se ha asignado ninguna directiva por usuario a un usuario, el usuario se administrará automáticamente mediante la directiva global.


> [!NOTE]  
> ¿Qué sucede si el usuario tiene asignada una directiva por usuario y desea cancelar la asignación de esa Directiva y, en su lugar, la directiva global la administrará? En ese caso, primero usará la sintaxis siguiente, que anula la asignación de una directiva por usuario al otorgar a ese usuario una directiva nula:<BR>Grant-CsVoicePolicy – identidad "Ken Myer" – PolicyName $Null



En segundo lugar, tenga en cuenta que las directivas por usuario se crean en el ámbito de la etiqueta. Sin embargo, puede omitir el **prefijo** de etiqueta al especificar un nombre de directiva. Estos dos comandos son idénticos:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Si desea devolver las identidades de todas las directivas de cada usuario (o, al menos, todas las directivas de cada usuario de tipo especificado, como las directivas de voz), use un comando similar a este:

    Get-CsVoicePolicy -Filter "tag:*"

Los siguientes cmdlets usan la identidad del usuario y el ámbito de la etiqueta:

  - [Grant-ClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Vea también


[Identidades, ámbitos y espacios empresariales en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

