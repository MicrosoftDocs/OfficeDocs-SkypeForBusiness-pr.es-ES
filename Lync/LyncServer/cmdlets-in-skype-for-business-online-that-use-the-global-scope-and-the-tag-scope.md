---
title: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233102"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta

 


En Skype empresarial online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito* de la etiqueta (o *por ámbito de usuario*). Al usar los cmdlets **Get-CS** , no tiene que especificar un ámbito o una identidad. Si llama a uno de estos cmdlets sin parámetros, se devolverán todos los elementos pertinentes. Por ejemplo, este comando devuelve información acerca de todas las directivas de acceso externas:

    Get-CsExternalAccessPolicy

Si desea limitar los datos devueltos, solo tiene que incluir el parámetro Identity o el parámetro filter. Por ejemplo, para devolver solo la directiva global, use este comando:

    Get-CsExternalAccessPolicy -Identity "global"

Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Cuando se hace referencia a una directiva por usuario, <STRONG></STRONG> el prefijo de etiqueta es opcional. Esta sintaxis, que incluye el prefijo, también es válida:<BR>Get-CsExternalAccessPolicy – Identity "etiqueta: RedmondAccessPolicy"



Para devolver todas las directivas excepto las directivas globales (es decir, todas las directivas por usuario), use este comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Los siguientes cmdlets funcionan contra el ámbito global y el ámbito por usuario (etiqueta):

  - [Get-ClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> A pesar del nombre, los planes de marcado son, en términos funcionales, directivas. El <EM>plan de marcado</EM> de términos se usa en lugar de, por ejemplo, la Directiva de marcado, a fin de preservar la terminología que se usa con versiones anteriores de Lync Server.



## <a name="see-also"></a>Vea también


[Identidades, ámbitos y espacios empresariales en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

