---
title: Apariencia de línea compartida en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Obtenga información sobre la característica Compartir la apariencia de línea en Microsoft Teams.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614102"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Apariencia de línea compartida en Microsoft Teams

La apariencia de línea compartida permite a un usuario elegir un delegado para responder o administrar llamadas en su nombre. Esta característica es útil si un usuario tiene un asistente administrativo que se encarga periódicamente de las llamadas del usuario. En el contexto de la apariencia de línea compartida, un administrador es alguien que autoriza a un delegado a realizar o recibir llamadas en su nombre. Un delegado puede realizar o recibir llamadas en nombre del delegador.

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación de Teams. Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia necesaria

Tanto los administradores como los delegados deben tener una licencia de Sistema telefónico con conectividad RTC (Plan de llamadas, Conexión de operadores o Enrutamiento directo). La experiencia de línea compartida forma parte de la delegación y se incluye con Sistema telefónico. Para obtener más información sobre las licencias, consulte [descripción del servicio microsoft teams](/office365/servicedescriptions/teams-service-description).

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidad de características de apariencia de línea compartida

La apariencia de línea compartida es compatible actualmente con las siguientes aplicaciones y dispositivos.

| Funcionalidad | Equipos de escritorio de Teams | Aplicación Teams para Mac | Teams Web App (Edge) |Aplicación móvil de Teams para iOS/Android | Teléfono IP de Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegación | Sí | Sí | Sí | No | Sí |
| Recibir llamadas en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un número de teléfono en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un usuario de Teams en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Ver la vista de delegado de líneas compartidas | Sí | Sí | Sí | No | Sí |
| Ver la vista de delegado de las actividades de llamada del jefe | Sí | Sí | Sí | No | Sí |
| Ver la vista de administrador de delegados | Sí | Sí | Sí | No | Sí |
| El delegado o el administrador pueden retener o reanudar | Sí | Sí | Sí | No | Sí |

## <a name="limitations"></a>Limitaciones

Los administradores pueden agregar hasta 25 delegados, y los delegados pueden tener hasta 25 administradores. No hay ningún límite en el número de relaciones de delegación que se pueden crear en un inquilino. 
 
Si el delegado y el delegado no se encuentran en la misma ubicación geográfica, el proveedor de RTC debe permitir que el identificador de llamada aparezca desde una ubicación geográfica diferente para una llamada delegada. 

No se permite la configuración de delegación circular. Si los usuarios delegados también tienen delegaciones entre ellos, solo podrán ver su delegación y no la delegación inicial.

## <a name="enable-delegation-and-shared-line-appearance"></a>Habilitar la delegación y la apariencia de la línea compartida

Para habilitar la delegación, use la configuración **de TeamsCallingPolicy AllowDelegation** . Puede usar el Centro de administración de Teams o PowerShell de Teamms. 

Cuando se habilita, el usuario final puede configurar sus relaciones de delegación directamente en Teams. 

> [!IMPORTANT]
> Al desactivar la delegación de un usuario, también debe limpiar las relaciones de delegación para ese usuario en el Centro de administración de Teams para evitar el enrutamiento incorrecto de llamadas.

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

Para configurar la delegación y la apariencia de las líneas compartidas con el Centro de administración de Teams, vea [Configurar las opciones de llamada para los usuarios](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usar PowerShell

Para configurar la delegación y la apariencia de la línea compartida con Teams PowerShell, use los cmdlets siguientes:

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>Ejemplos

En el ejemplo siguiente, se agrega user2@contoso.com como delegado de user1@contoso.com con permisos para realizar y recibir llamadas en nombre de usuario1 y para cambiar la configuración de otros delegados:

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

En el siguiente ejemplo, el user2@contoso.com delegado ya no podrá realizar llamadas en nombre del usuario1:

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

En el ejemplo siguiente, se quita user2@contoso.com como delegado de user1@contoso.com:

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>Más información

[Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Directiva de llamadas de Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
