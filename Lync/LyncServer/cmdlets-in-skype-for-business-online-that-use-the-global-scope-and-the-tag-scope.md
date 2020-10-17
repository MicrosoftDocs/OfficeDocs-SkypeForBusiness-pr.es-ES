---
title: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta
description: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545626"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta

 


En Skype empresarial online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito* de la etiqueta (o *por ámbito de usuario*). Cuando se usan los cmdlets **Get-CS** , no es necesario especificar un ámbito o una identidad. Si se llama a uno de estos cmdlets sin ningún parámetro, se devolverán todos los elementos relevantes. Por ejemplo, este comando devuelve información sobre todas las directivas de acceso externo:

    Get-CsExternalAccessPolicy

Si desea limitar los datos devueltos, solo tiene que incluir el parámetro Identity o el parámetro filter. Por ejemplo, para devolver sólo la directiva global, use este comando:

    Get-CsExternalAccessPolicy -Identity "global"

Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Cuando se hace referencia a una directiva por usuario, el <STRONG>prefijo</STRONG> de etiqueta es opcional. Esta sintaxis, que incluye el prefijo, también es válida:<BR>Get-CsExternalAccessPolicy – Identity "etiqueta: RedmondAccessPolicy"



Para devolver todas las directivas excepto las directivas globales (es decir, todas las directivas por usuario), use este comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Los siguientes cmdlets operan en el ámbito global y en el ámbito por usuario (etiqueta):

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> A pesar del nombre, los planes de marcado son, en términos funcionales, directivas. El plan de términos de <EM>marcado</EM> se usa en lugar de, por ejemplo, la Directiva de marcado, a fin de preservar la terminología que se usa con versiones anteriores de Lync Server.



## <a name="see-also"></a>Consulte también


[Identidades, ámbitos e inquilinos en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

