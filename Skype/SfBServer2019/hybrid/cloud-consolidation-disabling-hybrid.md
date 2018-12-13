---
title: Deshabilitar híbrido para completar la migración a la nube
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye los pasos detallados para deshabilitar híbrida como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247734"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar híbrido para completar la migración a la nube

Después de mover todos los usuarios de local a la nube, puede retirar el Skype local para la implementación de la empresa. Aparte de eliminar cualquier hardware, un paso crítico es separar de forma lógica que la implementación local de Office 365 deshabilitando híbrida. Deshabilitar híbrida consta de 3 pasos:

1. Actualizar registros DNS que apunten a Office 365.
2. Deshabilitar dominio dividido en el inquilino de Office 365.
3. Deshabilitar la capacidad de comunicarse con Office 365 en prem.


Estos pasos deben realizarse conjuntamente como una unidad. A continuación se proporcionan los detalles.

> [!Note] 
> En algunos casos poco frecuentes, cambiar DNS de apuntar en local a Office 365 para su organización puede causar federación con otras organizaciones dejen de funcionar hasta que otra organización actualiza su configuración de federación:<ul><li>
Las organizaciones federadas que usan el modelo de federación directa antiguo (también conocido como servidor de socio permitido) tendrá que actualizar sus entradas de dominios permitidos para su organización quitar el FQDN del proxy. Este modelo de federación heredada no se basa en los registros DNS SRV, por lo que dicha configuración se convertirán en caducada una vez que la organización se mueve a la nube. </li><li>Cualquier organización federada que no tiene un proveedor de hospedaje habilitado para sipfed.online.lync. <span>com tendrá que actualizar su configuración para permitir que. Esta situación sólo es posible si la organización federada es puramente local y nunca ha federados con cualquier híbrido o inquilino en línea. En tal caso, la federación con estas organizaciones no funcionará hasta que permiten que su proveedor de hospedaje.</li></ul>Si sospecha que alguno de los socios federados que esté utilizando la federación directa o tengan federado en línea con cualquiera u organización híbrida, es recomendable que les envíe una comunicación sobre esto mientras se prepara para llevar a cabo la migración a la nube.

1.  *Actualización de DNS para que apunten a Office 365.*
DNS externo de la organización para la organización local debe actualizarse para que apunten Skype para los registros de negocios a Office 365 en lugar de la implementación local. En concreto:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span>com|
    |CNAME| lyncdiscover|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| SIP|    3600|   sipdir.Online.Lync. <span>com|
    |CNAME| cumplir|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| acceso telefónico  |3600|  WebDir.Online.Lync. <span>com|

2.  *Deshabilitar el espacio de direcciones SIP compartido en Office 365 inquilino.*
El comando siguiente debe realizarse desde un Skype para la ventana de PowerShell en línea de negocio.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Deshabilitar la capacidad de comunicarse con Office 365 en prem.*  
El comando siguiente debe realizarse desde una ventana de PowerShell local.  Si ha importado previamente un Skype para sesión empresarial en línea, inicie un nuevo Skype para la sesión de PowerShell de negocio.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Vea también

[Consolidación de la nube para equipos y Skype para la empresa](cloud-consolidation.md)