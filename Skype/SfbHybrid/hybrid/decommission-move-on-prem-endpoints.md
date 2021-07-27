---
title: Migrar puntos de conexión de aplicaciones híbridas a la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Migre los puntos de conexión de la aplicación hirid antes de retirar Skype Empresarial entorno local.
ms.openlocfilehash: ee437f7f6c35ee67168c81e8e8ad440b1b0ba824
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574245"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Migrar puntos de conexión de aplicaciones híbridas antes de retirar el entorno local

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se describe cómo mover puntos de conexión de aplicación híbrida necesarios a la nube de Microsoft antes de retirar el entorno Skype Empresarial local. Este es el paso 3 de los siguientes pasos para retirar el entorno local:

- Paso 1. [Mover todos los usuarios necesarios de local a online](decommission-move-on-prem-users.md)

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- **Paso 3. Migre los puntos de conexión de aplicaciones híbridas de local a online.** (Este artículo)

- Paso 4. [Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Migrar todos los extremos de aplicación híbrida necesarios de local a online

Para poder mover estos puntos de conexión a línea, debe asegurarse de que ha actualizado los registros DNS para que apunten a Microsoft 365 para todos los dominios sip usados por los puntos de conexión. Tenga en cuenta que una vez que actualice DNS para que apunte a Microsoft 365, los puntos de conexión de aplicaciones híbridas existentes ya no se podrán detectar hasta que complete este paso. Dado que este paso (crear cuentas de recursos en línea) no es posible si los registros DNS apuntan a local, debe planear realizar los pasos 2 y 3 en la misma ventana de mantenimiento. Para obtener más información, vea [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).

1. Recupere y exporte la configuración de extremo de aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Cree y licencia nuevas [cuentas de](/microsoftteams/manage-resource-accounts) recursos en Microsoft 365 reemplazar los puntos de conexión de aplicación híbrida locales existentes.

3. Asocie las nuevas cuentas de recursos con los extremos de aplicación híbrida existentes.

4. Quite los números de teléfono definidos en los extremos de la aplicación híbrida local ejecutando el siguiente comando de PowerShell Skype Empresarial Server local:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Dado que es posible que los números de teléfono de estas cuentas se administraron en Microsoft 365 en lugar de local, ejecute el siguiente comando en Teams PowerShell:

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Asigne números de teléfono a las nuevas cuentas de recursos creadas en el paso 2. Para obtener más información acerca de cómo asignar un número de teléfono a una cuenta de recurso, vea el siguiente artículo: [Asignar un número de servicio](/microsoftteams/manage-resource-accounts#assign-a-service-number).

7. Elimine los extremos locales ejecutando el siguiente comando local Skype Empresarial Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Ya está listo para [quitar la implementación Skype Empresarial local.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Vea también

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Mover todos los usuarios necesarios de local a online](decommission-move-on-prem-users.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Eliminar la implementación local de Skype Empresarial](decommission-remove-on-prem.md)




