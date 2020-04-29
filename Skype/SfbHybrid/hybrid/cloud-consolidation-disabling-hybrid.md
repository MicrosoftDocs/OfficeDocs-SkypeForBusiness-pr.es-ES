---
title: Deshabilitar la implementación híbrida para completar la migración a la nube
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 039e8a30495567fe818fe4d60b863f37cf94e049
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918739"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial. Aparte de quitar el hardware, un paso crítico es separar lógicamente la implementación local de Office 365 deshabilitando la implementación híbrida. La deshabilitación de un híbrido consta de tres pasos:

1. Actualizar los registros DNS para que apunten a Office 365.

2. Deshabilite el dominio dividido en la organización de Office 365.

3. Deshabilite la capacidad local para comunicarse con Office 365.

Estos pasos deben realizarse juntos como una unidad. A continuación se proporcionan detalles. Además, se proporcionan instrucciones para administrar los números de teléfono de los usuarios migrados una vez que la implementación local está desconectada.

> [!Note] 
> En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:<ul><li>
Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy. Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube. </li><li>Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span>com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.</li></ul>Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que no se ha federado con ninguna organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.

1.  *Actualice DNS para que apunte a Office 365.*
El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype empresarial apunten a Office 365 en lugar de a la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls. _tcp|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_sip. _tls|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span>com|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|
    |CNAME| cumplir|   3600|   webdir. online. Lync. <span>com|
    |CNAME| Dialin  |3600|  webdir. online. Lync. <span>com|

2.  *Deshabilite el espacio de direcciones SIP compartido en la organización de Office 365.*
El siguiente comando debe realizarse desde una ventana de PowerShell de Skype empresarial online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Deshabilite la capacidad local para comunicarse con Office 365.*  
El siguiente comando debe realizarse desde una ventana de PowerShell local:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Administrar los números de teléfono para los usuarios que se han migrado de local

Los administradores pueden administrar los usuarios que se movieron anteriormente desde un servidor local de Skype empresarial Server a la nube, incluso después de que se haya retirado la implementación local. Hay dos posibilidades diferentes:

- El usuario no tenía un valor para LineURI local antes del movimiento. 

  En este caso, puede modificar la LineURI con los parámetros-onpremLineUri del [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype empresarial online.

- El usuario tenía un LineURI local antes del movimiento (presumiblemente porque el usuario estaba habilitado para telefonía IP empresarial). 

  Si desea cambiar la LineURI, debe hacerlo en Active Directory local y dejar que el valor pase a Azure AD... Esto no requiere Skype empresarial Server local. En su lugar, este atributo, msRTCSIP-line, se puede editar directamente en Active Directory local, mediante el complemento usuarios y equipos de Active Directory de MMC, o bien mediante PowerShell. Si está usando el complemento de MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque msRTCSIP-line.

  ![Herramienta usuarios y equipos de Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a>Vea también

[Consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md)
