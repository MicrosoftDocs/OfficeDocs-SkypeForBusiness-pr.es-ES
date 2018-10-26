---
title: Cmdlets con identidad de usuario y ámbito de etiqueta
TOCTitle: Cmdlets con identidad de usuario y ámbito de etiqueta
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56271278
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets con identidad de usuario y ámbito de etiqueta

 

_**Última modificación del tema:** 2015-06-22_

Los cmdlets **Grant-Cs** (usados para asignar directivas a los usuarios) requieren dos identificadores: la identidad del usuario (el parámetro Identity) y la identidad de una directiva por usuario (el parámetro PolicyName). Por ejemplo, para asignar la directiva de voz RedmondVoicePolicy al usuario Ken Myer, usamos el comando siguiente:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Al asignar directivas a los usuarios, debe recordar dos cosas. Lo primero es que solo se pueden asignar directivas por usuario. La directiva global no se puede asignar a los usuarios. Este comando, por ejemplo, no funcionará:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Este comando da error porque no hay necesidad de asignar la directiva global. Si quiere administrar a un usuario con la directiva global, lo único que debe hacer es no asignarle una directiva por usuario. Si a un usuario no se le ha asignado ninguna directiva por usuario, el usuario se administrará automáticamente con la directiva global.


> [!NOTE]
> ¿Qué sucede si al usuario se le ha asignado anteriormente una directiva por usuario y queremos anular la asignación de esa directiva para administrar al usuario con la directiva global? En este caso, primero usamos la sintaxis siguiente, que anula la asignación de una directiva por usuario y concede al usuario una directiva nula:<BR>Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null



Lo segundo es recordar que las directivas por usuario se crean en el ámbito de etiqueta. Sin embargo, el **prefijo** "tag" (etiqueta) se puede omitir al especificar un nombre de directiva. Estos dos comandos son idénticos:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Si quisiera devolver las identidades de todas las directivas por usuario (o, al menos, todas las directivas por usuario del tipo indicado, como las directivas de voz), usaría un comando parecido a este:

    Get-CsVoicePolicy -Filter "tag:*"

Los cmdlets siguientes usan tanto una identidad de usuario como el ámbito de etiqueta:

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

