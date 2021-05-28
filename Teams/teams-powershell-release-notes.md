---
title: Microsoft Teams Notas de la versión de PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre los cambios más recientes en Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 986aebf2ae86e463976f4480fbd2f7dde440f0a1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684377"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Notas de la versión de PowerShell

En esta página se proporcionan las últimas Teams de cambios de PowerShell para las versiones disponibilidad general y vista previa pública.

## <a name="release-notes"></a>Notas de la versión

> [!NOTE]
> **-preview** en la columna de versión siguiente representa las actualizaciones Teams vista previa pública de PowerShell.

| Fecha | Versión | Actualizaciones |
|------- | -------------------- | ------------------------------ |
| Mayo de 2021 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Compatibilidad con el inicio de sesión de AccessToken con Conectar-MicrosoftTeams. Se ha agregado el parámetro -AccessTokens que acepta la matriz de token. MSGraph y Teams de recursos son necesarios al usar el parámetro AccessTokens.</li><li>Se han quitado los parámetros AadAccessToken y MsAccessToken.</li>|
| Mayo de 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Actualizar desde . NETCore 2.1 a 3.1</li><li>Cmdlet agregado para obtener una región multige geográfica para usuarios y grupos</li><li>Correcciones para la autenticación integrada de Windows para usar -AccountId con Connect-MicrosoftTeams</li><li>Los cmdlets de TeamsCallHoldPolicy ya están disponibles</li><li>Actualizaciones de parámetros de entrada y formatos de salida de muchos comandos</li><li>Corrige un problema de latencia grande al ejecutar comandos de comunicación remota</li><li>Características de paquetes personalizados de GA</li>|
| Abril de 2021 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Correcciones para la autenticación Windows usuario integrada para usar -AccountId con Conectar-MicrosoftTeams.</li><li>Cmdlet agregado para obtener detalles del total de eventos de notificación de cambio que se pueden enviar a los usuarios.</li><li>Se ha agregado un cmdlet para obtener una región multige geográfica para usuarios y grupos.</li><li>El control de los valores pasados a TeamsEnvironment name distingue entre mayúsculas y minúsculas. Esto se ha corregido.</li><li>Refactorización importante de la administración remota de sesiones dentro del módulo para facilitar las pruebas de unidad. No debe haber ningún cambio funcional para los administradores de inquilinos.</li>|
| Abril de 2021 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Se ha corregido el formato de los cmdlets existentes (por ejemplo, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy y mucho más).</li><li>Lista de parámetros actualizada de cmdlets de administración de directivas.</li>|
| Marzo de 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL para la autenticación & autorización</li> <li>Connect-MicrosoftTeams es el punto de entrada de todos los cmdlets.</li><li>New-csOnlineSession ya no está disponible. Se ha sustituido por Conectar-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection ya no es necesario. La característica se ha implementado de forma nativa en Teams módulo de PowerShell.</li> <li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Mejoras significativas de rendimiento para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de administración de plantillas agregados</li> <li>Desuso de New-CsOnlineSession</li>|
| Febrero de 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlets de administración de plantillas agregados</li><li>Mejoras de mezzo y procesamiento por lotes para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de paquete de directivas refactorizado</li>|
| Diciembre de 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Actualizaciones del cmdlet New-team con mayores reintentos y duración de suspensión</li>|
| Diciembre de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Actualizaciones para Skype Empresarial integración en línea</li><li>Corrección del mensaje duplicado con Connect-Microsoft Teams</li>|
| Noviembre de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Agrega cmdlets de paquetes de directivas personalizados</li><li>Correcciones para los comandos de carga de la jerarquía de destino</li>|
| Noviembre de 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL para la autenticación & autorización</li><li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Comandos de carga de jerarquía de segmentación refactorizado para usar un modelo asíncrono</li> <li>Se le pedirá al usuario dos veces durante la autenticación inicial cuando no use el parámetro -credential. Los usuarios pueden pasar credenciales con el parámetro -credential para evitar un mensaje duplicado. Este comportamiento se solucionará en la próxima versión.</li> |
| Septiembre de 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype Empresarial Integración con Conectores en línea</li> |
| Septiembre de 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype Empresarial Integración con Conectores en línea</li> |
| Julio de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlets de [asignación de directivas de grupo agregados](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Junio de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype Empresarial Integración con Conectores en línea<li>Get-Team optimizaciones<li>Confiabilidad mejorada</li> |
| Junio de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Se ha agregado la precarga del cmdlet<li>Optimizaciones de .Net Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Firma de autenticación y ensamblado<li>Se agregaron Get-CsPolicyPackage<li>Se agregaron Get-CsUserPolicyPackage<li>Se agregaron Get-CsUserPolicyPackageRecommendation<li>Se agregaron Grant-CsUserPolicyPackage<li>Se agregaron New-CsBatchPolicyPackageAssignmentOperation<li>Se agregaron Set-TeamArchivedState<li>Se agregaron Set-TeamPicture<li>Eliminado Get-TeamHelp</li>  |
| Marzo de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Se agregaron New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimizaciones</li>  |

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Instalar Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams referencia de cmdlet](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)
