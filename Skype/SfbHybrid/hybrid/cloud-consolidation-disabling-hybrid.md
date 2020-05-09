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
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173976"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial. Aparte de quitar el hardware, un paso crítico es separar lógicamente la implementación local de Office 365 deshabilitando la implementación híbrida. La deshabilitación de un híbrido consta de tres pasos:

- Actualizar los registros DNS para que apunten a Office 365.
- Deshabilite el dominio dividido en la organización de Office 365.
- Deshabilite la capacidad local para comunicarse con Office 365.

Estos pasos deben realizarse juntos como una unidad. A continuación se proporcionan detalles. Además, se proporcionan instrucciones para administrar los números de teléfono de los usuarios migrados una vez que la implementación local está desconectada.

> [!Important] 
>Debe seguir haciendo que los atributos de msRTCSIP en la sincronización de Active Directory mediante Azure AD se conecten a Azure AD.  No borre ninguno de estos atributos a menos que se lo indique el soporte técnico.  No ejecute Disable-CsUser en el entorno local. Si necesita modificar la dirección SIP de un usuario, haga esto en su Active Directory local y deje que este cambio se sincronice en Azure AD a través de Azure AD Connect, como se describe a continuación. De forma similar, si necesita cambiar un número de teléfono y la LineURI del usuario ya está definida en local, debe modificarla en el entorno local de Active Directory.
>El borrado de los atributos msRTCSIP locales después de haber migrado de local podría provocar la pérdida de servicio para los usuarios.



1.  *Actualice DNS para que apunte a Office 365.*
Los registros DNS externos existentes de la organización para la organización local deben actualizarse para que los registros de Skype empresarial apunten a Office 365 en lugar de la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|Finalidad|
    |---|---|---|---|---|
    |SRV|_sipfederationtls. _tcp|3600|100 1 5061 sipfed. online. Lync. <span>com|Habilita la Federación|
    |SRV|_sip. _tls|3600|100 1 443 sipdir. online. Lync. <span>com|Necesario para los usuarios de Skype empresarial|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span>com|Necesario para los usuarios de Skype empresarial|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|Necesario solo para teléfonos SIP heredados más antiguos|

    Además, los registros CNAME para reunirse o marcar (si los hay) se pueden eliminar.

    > [!Note] 
    > En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:
    >
    > - Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy. Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube.
    > 
    > - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span>com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.
    >
    > Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que no se ha federado con ninguna organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.

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

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Administrar direcciones SIP y números de teléfono para los usuarios que se han migrado de local

Los administradores pueden administrar los usuarios que se movieron anteriormente desde un servidor local de Skype empresarial Server a la nube, incluso después de que se haya retirado la implementación local. Si desea realizar cambios en la dirección SIP de un usuario o en el URI de línea de un usuario (y la dirección SIP o URI de línea ya está definida en la implementación local de Active Directory), debe hacerlo en Active Directory local y dejar que los valores continúen hasta Azure AD. Esto no requiere Skype empresarial Server local. En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento usuarios y equipos de Active Directory de MMC, o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos apropiados que desea modificar:

- Para modificar la dirección SIP de un usuario, modifique `msRTCSIP-PrimaryUserAddress`el. Además, si el `ProxyAddresses` atributo contiene un valor SIP, actualice el valor SIP para que se ajuste al nuevo valor `msRTCSIP-PrimaryUserAddress`de. Si no contiene un valor SIP, puede dejarlo en blanco.

- Para modificar el número de teléfono de un usuario `msRTCSIP-Line` , modifique *si ya tiene un valor*.

  ![Herramienta usuarios y equipos de Active Directory](../media/disable-hybrid-1.png)
  
Si el usuario no tuvo originalmente un valor para `LineURI` local antes del movimiento, puede modificar el LineURI mediante el parámetro-`onpremLineUri` en el [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype empresarial online.


## <a name="see-also"></a>Vea también

[Consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md)
