---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001445"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta

 


Los cmdlets **Grant-CS** (que se usan para asignar directivas a usuarios) requieren dos identificadores: una identidad de usuario (el parámetro Identity) y la identidad de una directiva por usuario (el parámetro PolicyName). Por ejemplo, para asignar la Directiva de voz, RedmondVoicePolicy, al usuario Ken Myer, use el siguiente comando:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Hay dos cosas que debe tener en cuenta al asignar directivas a los usuarios. En primer lugar, solo se pueden asignar directivas por usuario. No se puede asignar la directiva global a un usuario. Por ejemplo, se producirá un error en este comando:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Este comando produce un error porque no es necesario asignar la directiva global. Si desea administrar a un usuario mediante la directiva global, asegúrese de que no asigna a ese usuario una directiva por usuario. Si no se ha asignado ninguna directiva por usuario a un usuario, el usuario se administrará automáticamente mediante la directiva global.


> [!NOTE]  
> ¿Qué ocurre si el usuario ya tiene asignada una directiva por usuario y desea quitar la asignación de esa Directiva y, en su lugar, administrar al usuario la directiva global? En ese caso, primero usará la siguiente sintaxis, que anula la asignación de una directiva por usuario al conceder a esa usuario una directiva nula:<BR>Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null



En segundo lugar, tenga en cuenta que las directivas por usuario se crean en el ámbito de la etiqueta. Sin embargo, puede omitir el **prefijo** de etiqueta al especificar un nombre de directiva. Estos dos comandos son idénticos:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Si desea devolver las identidades de todas las directivas por usuario (o, al menos, todas las directivas por usuario del tipo especificado, como las directivas de voz), use un comando similar a este:

    Get-CsVoicePolicy -Filter "tag:*"

Los siguientes cmdlets usan la identidad del usuario y el ámbito de la etiqueta:

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Vea también


[Identidades, ámbitos e inquilinos en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

