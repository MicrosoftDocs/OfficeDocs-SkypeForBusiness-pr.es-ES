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
ms.openlocfilehash: f852a3fb44408c6601be8c6bd4f07946419cea71
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269664"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial. Aparte de quitar el hardware, un paso crítico es separar lógicamente esa implementación local de Microsoft 365 u Office 365 deshabilitando el entorno híbrido. La deshabilitación de un híbrido consta de tres pasos:

1. Actualice los registros DNS para que apunten a Microsoft 365 u Office 365.

2. Deshabilite el dominio dividido en la organización de Microsoft 365 u Office 365.

3. Deshabilite la capacidad local para comunicarse con Microsoft 365 u Office 365.

Estos pasos deben realizarse juntos como una unidad. A continuación se proporcionan detalles. Además, se proporcionan instrucciones para administrar los números de teléfono de los usuarios migrados una vez que la implementación local está desconectada.

Una vez completados estos pasos, los servidores locales de Skype empresarial ya no se usan y se pueden volver a crear las imágenes de estos servidores.

> [!Important] 
>Debe seguir haciendo que los atributos de msRTCSIP en la sincronización de Active Directory mediante Azure AD se conecten a Azure AD.  No borre ninguno de estos atributos a menos que se lo indique el soporte técnico.  No ejecute Disable-CsUser en el entorno local. Si necesita modificar la dirección SIP de un usuario, haga esto en su Active Directory local y deje que este cambio se sincronice en Azure AD a través de Azure AD Connect, como se describe a continuación. De forma similar, si necesita cambiar un número de teléfono y la LineURI del usuario ya está definida en local, debe modificarla en el entorno local de Active Directory.
>El borrado de los atributos msRTCSIP locales después de haber migrado de local podría provocar la pérdida de servicio para los usuarios.

> [!Note] 
> En raras ocasiones, cambiar el DNS de los locales a Microsoft 365 u Office 365 en su organización puede provocar que la Federación con otras organizaciones deje de funcionar hasta que la otra organización actualice su configuración de Federación:<ul><li>
Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy. Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube. </li><li>Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada se encuentra exclusivamente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.</li></ul>Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que se ha federado con una organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.

1.  *Actualice DNS para que apunte a Microsoft 365 u Office 365.*
El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype empresarial apunten a Microsoft 365 o a Office 365 en lugar de a la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. Lync. <span> Puerto|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span> Puerto|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span> Puerto|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span> Puerto|
    |CNAME| cumplir|   3600|   webdir. online. Lync. <span> Puerto|
    |CNAME| Dialin  |3600|  webdir. online. Lync. <span> Puerto|

    Además, los registros CNAME para reunirse o marcar (si los hay) se pueden eliminar. Por último, se deben quitar todos los registros DNS para Skype empresarial en la red interna.

    > [!Note] 
    > En raras ocasiones, al cambiar el DNS de los locales a Office 365 para su organización, la Federación con otras organizaciones puede dejar de funcionar hasta que la otra organización actualice la configuración de la Federación:
    >
    > - Todas las organizaciones federadas que usen el modelo de Federación directa anterior (también conocido como servidor asociado permitido) tendrán que actualizar las entradas de dominio permitidas en su organización para quitar el FQDN del proxy. Este modelo de Federación heredada no se basa en los registros SRV de DNS, por lo que dicha configuración quedará obsoleta una vez que la organización se traslade a la nube.
    > 
    > - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed. online. Lync. <span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la Federación con estas organizaciones no funcionará hasta que habilite su proveedor de hospedaje.
    >
    > Si sospecha que cualquiera de sus socios federados puede usar Federación directa o que no se ha federado con ninguna organización en línea o híbrida, le sugerimos que les envíe una comunicación sobre esto cuando se prepare para completar la migración a la nube.


2.  *Deshabilite el espacio de direcciones SIP compartido en la organización de Microsoft 365 u Office 365.*
El siguiente comando debe realizarse desde una ventana de PowerShell de Skype empresarial online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Deshabilite la capacidad local para comunicarse con Microsoft 365 u Office 365.*  
El siguiente comando debe realizarse desde una ventana de PowerShell local:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Administrar direcciones SIP y números de teléfono para los usuarios que se han migrado de local

Los administradores pueden administrar los usuarios que se movieron anteriormente desde un servidor local de Skype empresarial Server a la nube, incluso después de que se haya retirado la implementación local. Si desea realizar cambios en la dirección SIP de un usuario o en el URI de línea de un usuario (y la dirección SIP o URI de línea ya está definida en la implementación local de Active Directory), debe hacerlo en Active Directory local y dejar que los valores continúen hasta Azure AD. Esto no requiere Skype empresarial Server local. En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento usuarios y equipos de Active Directory de MMC, o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos apropiados que desea modificar:

- Para modificar la dirección SIP de un usuario, modifique el `msRTCSIP-PrimaryUserAddress` . Además, si el `ProxyAddresses` atributo contiene un valor SIP, actualice el valor SIP para que se ajuste al nuevo valor de `msRTCSIP-PrimaryUserAddress` . Si no contiene un valor SIP, puede dejarlo en blanco.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.

  ![Herramienta usuarios y equipos de Active Directory](../media/disable-hybrid-1.png)
  
Si el usuario no tuvo originalmente un valor para `LineURI` local antes del movimiento, puede modificar el LineURI mediante el `onpremLineUri` parámetro-en el [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype empresarial online.


## <a name="see-also"></a>Vea también

[Consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md)
