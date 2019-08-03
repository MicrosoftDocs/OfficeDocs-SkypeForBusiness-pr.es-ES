---
title: Deshabilitar la migración híbrida para completar la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160784"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar la migración híbrida para completar la nube

Una vez que haya movido a todos los usuarios de la nube local a la nube, puede retirar la implementación local de Skype empresarial. Aparte de quitar el hardware, un paso crítico es separar lógicamente esa implementación local de Office 365 deshabilitando híbrido. La deshabilitación de un híbrido consta de tres pasos:

1. Actualice los registros DNS para que apunten a Office 365.
2. Deshabilite el dominio dividido en el inquilino de Office 365.
3. Deshabilite la capacidad local para comunicarse con Office 365.


Estos pasos deben realizarse juntos como una unidad. A continuación se proporcionan detalles.

> [!Note] 
> En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:<ul><li>
Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy. Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube. </li><li>Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span>com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada se encuentra exclusivamente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.</li></ul>Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que se ha federado con una organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.

1.  *Actualice DNS para que apunte a Office 365.*
El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype empresarial apunten a Office 365 en lugar de a la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls. _ TCP|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_ SIP. _ TLS|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span>com|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|
    |CNAME| cumplir|   3600|   webdir. online. Lync. <span>com|
    |CNAME| Dialin  |3600|  webdir. online. Lync. <span>com|

2.  *Deshabilitar el espacio de direcciones SIP compartido en Office 365 tenant.*
El siguiente comando debe realizarse desde una ventana de PowerShell de Skype empresarial online.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Deshabilite la capacidad local para comunicarse con Office 365.*  
El siguiente comando debe realizarse desde una ventana de PowerShell local.  Si ya ha importado una sesión de Skype empresarial online, inicie una nueva sesión de PowerShell de Skype empresarial.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Vea también

[Consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md)