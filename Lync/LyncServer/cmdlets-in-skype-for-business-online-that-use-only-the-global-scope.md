---
title: Cmdlets de Skype empresarial online que solo usan el ámbito global
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4a894c4a9c6e2913abb003c49094bc6d6868483
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001255"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlets de Skype empresarial online que solo usan el ámbito global

 


Una cantidad de opciones de configuración de Skype empresarial online solo está disponible en el *ámbito global*. Esto significa que hay una sola colección de opciones de configuración que se aplican a todos los usuarios que están asignados a ese inquilino. (Cada inquilino tiene su propia colección única de configuración global). Cuando se usan cmdlets que están limitados al ámbito global, el parámetro Identity es opcional. Por ejemplo, para recuperar las opciones de configuración de reunión, puede usar este comando:

    Get-CsMeetingConfiguration -Identity "global"

Como alternativa, puede omitir el parámetro Identity y usar este comando más sencillo en su lugar:

    Get-CsMeetingConfiguration

Como solo hay una colección global de opciones de configuración de reuniones, los dos comandos devuelven exactamente la misma información. El parámetro Identity también puede omitirse cuando se usa uno de los cmdlets **set-CS** . Estos dos comandos son idénticos:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Los dos comandos son idénticos porque, de manera predeterminada, Windows PowerShell modificará la colección global si no se incluye el parámetro Identity.

Los cmdlets siguientes solo funcionan en el ámbito global:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Tenga en cuenta que el cmdlet **Remove-CsVoicePolicy** es algo de una anomalía. En primer lugar, este cmdlet requiere que incluya el parámetro Identity:

    Remove-CsVoicePolicy -Identity "global"

En segundo lugar, el cmdlet **Remove-CsVoicePolicy** no elimina realmente la Directiva de voz global; Skype empresarial online no permite eliminar directivas globales ni opciones de configuración. Lo que hace el cmdlet le permite restablecer todas las propiedades de la Directiva de voz global a sus valores predeterminados. Por ejemplo, de forma predeterminada, la propiedad AllowCallForwarding se establece en false. Sin embargo, es posible que AllowCallForwarding se haya modificado, con el valor ahora establecido en true. Cuando se ejecuta el cmdlet **Remove-CsVoicePolicy** , la propiedad AllowCallForwarding se revertirá a su valor predeterminado: false. En la tabla siguiente se resume este escenario:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor AllowCallForwarding</th>
<th>Escenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Una vez modificada la directiva global</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Después <strong>de ejecutar el cmdlet Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Vea también


[Identidades, ámbitos e inquilinos en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

