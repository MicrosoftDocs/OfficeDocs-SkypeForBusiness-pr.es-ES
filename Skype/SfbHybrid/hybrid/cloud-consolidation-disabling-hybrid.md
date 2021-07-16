---
title: Deshabilitar híbrido para completar la migración a Teams solo
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
description: En este artículo se incluyen pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación de la nube Teams y Skype Empresarial.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453649"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Deshabilitar la configuración híbrida para completar la migración a Teams solo 

En este artículo se describe cómo deshabilitar la configuración híbrida antes de retirar el entorno Skype Empresarial local. Este es el paso 2 de los siguientes pasos para retirar el entorno local:

- Paso 1. [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)

- **Paso 2. Deshabilite la configuración híbrida.** (Este artículo)

- Paso 3. [Migre los puntos de conexión de aplicaciones híbridas de local a en línea.](decommission-move-on-prem-endpoints.md)

- Paso 4. [Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)

> [!NOTE]
> Los pasos 2 y 3 deben realizarse en la misma ventana de mantenimiento porque los extremos de aplicación híbrida existentes no se podrán detectar entre los pasos 2 y la finalización del paso 3.


## <a name="summary"></a>Resumen

Después de actualizar todos los usuarios de Skype Empresarial local a Teams Solo en Microsoft 365, puede retirar la implementación Skype Empresarial local.

Antes de retirar la implementación Skype Empresarial local y quitar cualquier hardware, debe separar lógicamente la implementación local de Microsoft 365 deshabilitando la implementación híbrida. La deshabilitación híbrida consta de los cuatro pasos siguientes:

1. [Actualice los registros DNS para que apunten a Microsoft 365](#update-dns-to-point-to-microsoft-365).

2. [Cambie el modo de coexistencia de la organización a Teams Solo](#change-the-coexistence-mode-for-your-organization-to-teams-only).

3. [Deshabilitar el espacio de direcciones sip compartido (también conocido como "dominio dividido")](#disable-shared-sip-address-space-in-microsoft-365-organization)en la Microsoft 365 organización .

4. [Deshabilitar la comunicación entre locales y Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

Estos pasos separan lógicamente la implementación local de Skype Empresarial Server de Microsoft 365 y garantizan que la organización Teams solo. Después de completar estos pasos, puede retirar la implementación de Skype Empresarial local mediante uno de los dos métodos a los que se hace referencia en [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).

> [!Important] 
> Una vez completada esta separación lógica, los atributos msRTCSIP de su Active Directory local siguen teniendo valores y seguirán sincroniendo a través de Azure AD Conectar en Azure AD. La forma de retirar el entorno local depende de si desea dejar estos atributos en su lugar o, en primer lugar, borrarlos de su Active Directory local. Tenga en cuenta que borrar los atributos msRTCSIP locales después de migrar desde local podría provocar la pérdida de servicio para los usuarios. Los detalles y las transacciones de los dos enfoques de retirada se describen en [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).

## <a name="update-dns-to-point-to-microsoft-365"></a>Actualizar DNS para que apunte a Microsoft 365

El DNS externo de la organización para la organización local debe actualizarse para que los registros Skype Empresarial apunten a Microsoft 365 en lugar de a la implementación local. 

Además, se pueden eliminar los registros CNAME para meet o dialin (si están presentes). Por último, se deben quitar los registros DNS Skype Empresarial de la red interna.

Para obtener información detallada acerca de la actualización de registros [DNS,](decommission-manage-dns-entries.md)vea Actualizar entradas DNS para permitir que la organización sea Teams solo .

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Cambiar el modo de coexistencia de la organización a Teams solo

Este paso garantiza que cualquier nuevo usuario de la organización siempre se cree como un Teams solo usuario. 

Al intentar cambiar el modo de inquilino a Teams Only comprobará automáticamente la existencia de los registros DNS locales que se hayan perdido en el paso 1 e identificará estos registros en el resultado. Cambiar el modo de inquilino a Teams Solo no se realizará correctamente hasta que se actualicen todos los registros DNS de la organización. 

Para cambiar el modo de inquilino a Teams ejecute el siguiente comando desde una ventana Teams PowerShell.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

Como alternativa, puede usar el Centro de administración de Teams para cambiar el modo de coexistencia de inquilinos a TeamsOnly, en "Configuración de toda la organización" -> "Teams upgrade".    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Deshabilitar el espacio de direcciones sip compartido en Microsoft 365 organización
    
Para deshabilitar el espacio de direcciones sip compartido, ejecute el siguiente comando desde una ventana Teams PowerShell.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Deshabilitar la comunicación entre locales y Microsoft 365

Para deshabilitar la comunicación entre el entorno local y Microsoft 365, ejecute el siguiente comando desde una ventana de PowerShell local:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>Vea también

- [Consolidación de nube para Teams y Skype Empresarial](cloud-consolidation.md)

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

