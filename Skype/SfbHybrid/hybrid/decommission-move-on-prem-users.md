---
title: Mover usuarios y puntos de conexión a la nube
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
description: Mueva usuarios y puntos de conexión antes de retirar un entorno local de Skype Empresarial.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593913"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Mover los usuarios y puntos de conexión necesarios antes de retirar el entorno local

En este artículo se describe cómo mover usuarios y puntos de conexión de aplicaciones necesarios a la nube de Microsoft antes de retirar el entorno local de Skype Empresarial. Este es el paso 1 de los siguientes pasos para retirar el entorno local:

- **Paso 1. Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.** (En este artículo).

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- Paso 3. [Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos los usuarios necesarios de local a la nube

Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube. Los usuarios se mueven mediante las herramientas de administración locales. Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Aunque es posible que los usuarios con cuentas locales de Skype Empresarial Server usen Teams, estos usuarios no tienen la funcionalidad completa de Teams. Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local). Estos usuarios tampoco pueden recibir llamadas RTC en su cliente de Teams. Por lo tanto, debe mover estos usuarios a línea. Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.

Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana de PowerShell de Skype Empresarial Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md). Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Al Disable-CsUser se quitarán todos los atributos de Skype Empresarial para todos los usuarios que cumplan los criterios de filtro. Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Mover puntos de conexión de aplicaciones híbridas locales a Microsoft 365

1. Recupere y exporte la configuración de extremo de aplicación híbrida local ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Crear y licenciar [nuevas cuentas de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) recursos en Microsoft 365 para reemplazar los puntos de conexión de aplicaciones híbridas locales existentes.

3. Asocie las nuevas cuentas de recursos con los extremos de aplicación híbrida existentes.

4. Quite los números de teléfono definidos en los extremos de la aplicación híbrida local ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Dado que es posible que los números de teléfono de estas cuentas se administraron en Microsoft 365 en lugar de local, ejecute el siguiente comando en PowerShell de Skype Empresarial Online:

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

6. Asigne números de teléfono a las nuevas cuentas de recursos creadas en el paso 2. Para obtener más información acerca de cómo asignar un número de teléfono a una cuenta de recurso, vea el siguiente artículo: [Asignar un número de servicio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).

7. Elimine los extremos locales ejecutando el siguiente comando local de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

## <a name="see-also"></a>Ver también

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Quitar la implementación local de Skype Empresarial](decommission-remove-on-prem.md)




