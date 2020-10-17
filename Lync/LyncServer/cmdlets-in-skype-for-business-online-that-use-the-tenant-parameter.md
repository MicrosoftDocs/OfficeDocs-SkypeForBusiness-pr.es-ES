---
title: Cmdlets en Skype empresarial online que usan el parámetro tenant
description: Cmdlets de Skype empresarial online que usan el parámetro tenant.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546806"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets en Skype empresarial online que usan el parámetro tenant

 


Al modificar la configuración de un proveedor público, siempre debe proporcionar una identidad de espacio empresarial; Esto es así incluso si solo tiene un único inquilino. Por ejemplo, este comando configura Windows Live como el único proveedor público con el que los usuarios pueden comunicarse:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Afortunadamente, no es necesario escribir el identificador de inquilino (por ejemplo, bf19b7db-6960-41e5-A139-2aa373474354) cada vez que se ejecuta uno de estos cmdlets. En su lugar, puede recuperar el identificador de inquilino ejecutando el cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , almacenando el identificador de inquilino en una variable y, a continuación, usando esa variable cuando se llama a uno de los otros cmdlets. Por ejemplo:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Como alternativa, puede hacer esto en un solo comando al recuperar el identificador de inquilino y, a continuación, canalizar ese valor al cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

No es necesario especificar el identificador de inquilino al llamar al cmdlet **Get-CsTenant** . Este comando devuelve información sobre el espacio empresarial:

    Get-CsTenant

Los siguientes cmdlets aceptan una identidad de inquilino. Sin embargo, en estos casos, el parámetro es opcional y no es necesario especificarlo al llamar al cmdlet. En su lugar, Windows PowerShell introducirá la identidad del espacio empresarial de forma efectiva en el inquilino de Skype empresarial online al que esté conectado actualmente:

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Por ejemplo, se puede llamar al cmdlet **Get-CsTenantFederationConfiguration** con este comando:

    Get-CsTenantFederationConfiguration

Aunque no es necesario, puede incluir el parámetro tenant al llamar a Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Consulte también


[Identidades, ámbitos e inquilinos en Skype empresarial online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

