---
title: Cmdlets de ámbito global y de etiqueta
TOCTitle: Cmdlets de ámbito global y de etiqueta
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56271271
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets de ámbito global y de etiqueta

 

_**Última modificación del tema:** 2015-06-22_

En Skype Empresarial Online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito de etiqueta* (o *ámbito por usuario*). Al usar los cmdlets de **Get-Cs**, no tiene que especificar un ámbito ni una identidad. Si llama a uno de estos cmdlets sin ningún parámetro, se devolverán todos los elementos relevantes. Por ejemplo, este comando devuelve información sobre todas las directivas de acceso externo:

    Get-CsExternalAccessPolicy

Solo tiene que incluir el parámetro Identity o Filter si quiere limitar los datos devueltos. Por ejemplo, para devolver solo la directiva global, use este comando:

    Get-CsExternalAccessPolicy -Identity "global"

Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]
> Al hacer referencia a una directiva por usuario, el <STRONG>prefijo</STRONG> "tag" (etiqueta) es opcional. Esta sintaxis, que incluye el prefijo, también es válida:<BR>Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"



Para devolver todas las directivas excepto las globales (es decir, todas las directivas por usuario), use este comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Los cmdlets siguientes funcionan tanto en el ámbito global como en el ámbito por usuario (de etiqueta):

  - [Get-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientPolicy)

  - [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy)

  - [Get-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialPlan)

  - [Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

  - [Get-CsPresencePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPresencePolicy)

  - [Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)


> [!NOTE]
> A pesar del nombre, los planes de marcado son directivas desde el punto de vista funcional. El término <EM>plan de marcado</EM> se usa en lugar de, por ejemplo, directiva de marcado para mantener la coherencia con la terminología de las versiones anteriores de Lync Server.



## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

