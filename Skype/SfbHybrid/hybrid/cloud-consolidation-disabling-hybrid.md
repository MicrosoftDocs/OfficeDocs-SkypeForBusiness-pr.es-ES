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
description: Este apéndice incluye pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277254"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial. Además de quitar cualquier hardware, un paso crítico es separar lógicamente esa implementación local de Microsoft 365 u Office 365 deshabilitando la implementación híbrida. La deshabilitación de la implementación híbrida consta de 3 pasos:

1. Actualice los registros DNS para que apunten a Microsoft 365 u Office 365.

2. Deshabilitar el dominio dividido en la organización de Microsoft 365 u Office 365.

3. Deshabilitar la capacidad local para comunicarse con Microsoft 365 u Office 365.

Estos pasos deben realizarse conjuntamente como una unidad. A continuación se proporcionan detalles. Además, se proporcionan directrices para administrar los números de teléfono de los usuarios migrados una vez desconectada la implementación local.

Una vez completados estos pasos, los servidores locales de Skype Empresarial ya no se usan y se pueden volver a crear imágenes de estos servidores.

> [!Important] 
>Debes seguir permitir que los atributos msRTCSIP de Active Directory se sincronicen a través de Azure AD Connect en Azure AD.  No borre ninguno de estos atributos a menos que lo indique el soporte técnico.  No ejecute Disable-CsUser en el entorno local. Si necesita modificar la dirección SIP de un usuario, haga esto en su Active Directory local y deje que este cambio se sincronice en Azure AD a través de Azure AD Connect, como se describe a continuación. De forma similar, si necesita cambiar un número de teléfono y el LineURI del usuario ya está definido localmente, debe modificarlo en el Active Directory local.
>Borrar los atributos msRTCSIP locales después de haber migrado desde local podría provocar la pérdida de servicio para los usuarios.


1.  *Actualice DNS para que apunte a Microsoft 365 u Office 365.*
El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype Empresarial apunten a Microsoft 365 u Office 365 en lugar de a la implementación local. En particular:

    |Tipo de registro|Nombre|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|
    |CNAME| meet|   3600|   webdir.online.lync. <span> com|
    |CNAME| dialin  |3600|  webdir.online.lync. <span> com|

    Además, se pueden eliminar los registros CNAME para reunión o marcado (si está presente). Por último, se deben quitar todos los registros DNS de Skype Empresarial en la red interna.

    > [!Note] 
    > En raras ocasiones, cambiar el DNS de apuntar localmente a Office 365 para su organización puede provocar que la federación con otras organizaciones deje de funcionar hasta que esa otra organización actualice su configuración de federación:
    >
    > - Las organizaciones federadas que usan el antiguo modelo de federación directa (también conocido como Servidor de asociados permitidos) tendrán que actualizar las entradas de dominio permitido para que su organización quite el FQDN del proxy. Este modelo de federación heredado no se basa en los registros SRV de DNS, por lo que dicha configuración se desatendrán una vez que la organización se mueva a la nube.
    > 
    > - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync. <span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.
    >
    > Si sospecha que alguno de sus socios federados puede estar usando direct federation o no haber federado con ninguna organización en línea o híbrida, le sugerimos que envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.


2.  *Deshabilitar el espacio de direcciones SIP compartido en la organización de Microsoft 365 u Office 365.*
El siguiente comando debe realizarse desde una ventana de PowerShell de Skype Empresarial Online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Deshabilitar la capacidad local para comunicarse con Microsoft 365 u Office 365.*  
El siguiente comando debe realizarse desde una ventana de PowerShell local:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Administrar direcciones SIP y números de teléfono para los usuarios que se migraron desde un entorno local

Los administradores pueden administrar los usuarios que se movieron previamente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local. Si desea realizar cambios en la dirección SIP de un usuario o en el URI de línea de un usuario (y la dirección SIP o el URI de línea ya está definido en el Active Directory local), debe hacerlo en active directory local y permitir que los valores fluyan hasta Azure AD. Esto NO requiere Skype Empresarial Server local. En su lugar, puede modificar estos atributos directamente en el Active Directory local, mediante el complemento MMC Usuarios y equipos de Active Directory o mediante PowerShell. Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:

- Para modificar la dirección SIP de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo . Además, si el atributo contiene un valor SIP, actualice ese valor SIP para que coincida `ProxyAddresses` con el nuevo valor de `msRTCSIP-PrimaryUserAddress` . Si no contiene un valor SIP, puede dejarlo en blanco.

- Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor.*

  ![Herramienta de usuarios y equipos de Active Directory](../media/disable-hybrid-1.png)
  
Si el usuario no tenía originalmente un valor para local antes del traslado, puede modificar el LineURI con el parámetro - en el `LineURI` `onpremLineUri` cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) en el módulo de PowerShell de Skype Empresarial Online.


## <a name="see-also"></a>Vea también

[Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md)
