---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el parque de llamadas y recuperar para poner una llamada en espera en Microsoft Teams.
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614243"
---
# <a name="configure-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

La opción de aparcar y recuperar llamadas permite a un usuario poner una llamada en espera. Cuando se estaciona una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionó la llamada u otra persona puede usar ese código con una aplicación o dispositivo compatible para recuperar la llamada. (Para obtener más información, consulte [Estacionar una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)).

Algunos de los escenarios comunes para usar el parque de llamadas son:

- Una recepcionista estaciona una llamada para alguien que trabaja en una fábrica. A continuación, el recepcionista anuncia la llamada y el número de código sobre el sistema de direcciones públicas. El usuario para el que es la llamada puede entonces recoger un teléfono de Teams en la fábrica e introducir el código para recuperar la llamada.

- Un usuario estaciona una llamada en un dispositivo móvil porque la batería del dispositivo se está quedando sin energía. A continuación, el usuario puede escribir el código para recuperar la llamada desde un teléfono de escritorio de Teams.

- Un representante de soporte técnico estaciona una llamada de cliente y envía un anuncio en un canal de Teams para que un experto recupere la llamada y ayude al cliente. Un experto escribe el código en los clientes de Teams para recuperar la llamada.

Para aparcar y recuperar llamadas, un usuario debe ser un usuario Telefonía IP empresarial y debe estar incluido en una directiva de parque de llamadas.

De forma predeterminada, el intervalo de números de recogida de llamadas es del 10 al 99. También puede crear su propio rango personalizado entre 10 y 9999. La primera llamada estacionada se representará como un código de recogida del inicio del intervalo (por ejemplo, 10). La siguiente llamada estacionada se representará un código de recogida incrementado por 1; es decir, 11, y así sucesivamente, hasta que el final del intervalo se representa como un código de recogida. Después, los códigos de recogida representados vuelven a empezar desde el principio del intervalo. 

Puede especificar un tiempo de espera como el número de segundos de espera antes de volver a llamar cuando la llamada estacionada no se ha recogido. El intervalo permitido es de 120-1800 segundos y el valor predeterminado es 300 segundos.

Para configurar el parque de llamadas y recuperarlo, debe ser administrador de Teams. Está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios mediante la directiva de parque de llamadas. Al aplicar la misma directiva a un conjunto de usuarios, estos pueden aparcar y recuperar llamadas entre sí.

> [!NOTE]
> La opción de aparcar y recuperar llamadas solo está disponible en el [modo de implementación solo de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md). No se admite en los teléfonos IP Skype Empresarial.

Puede configurar el parque de llamadas y recuperarlos mediante el Centro de administración de Teams o mediante PowerShell.

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

Para crear una nueva instancia de directiva de parque de llamadas:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de **estacionamiento de llamadas** de **voz** > .

2. En la pestaña **Administrar directivas** , haga clic en **Agregar**.

3. Asigna un nombre a la directiva y, a continuación, cambia **Permitir parque de llamadas** a **Activado**.

4. Cambie el intervalo y el tiempo de espera del parque según sea necesario.

5. Seleccione **Guardar**.

Puede editar la directiva seleccionándola en la lista y haciendo clic en **Editar**.

Para que la directiva funcione, debe asignarse a los usuarios. Puede [asignar la directiva a los usuarios individualmente](assign-policies-users-and-groups.md) o asignarlos a un grupo.

Para asignar una directiva de parque de llamadas a un grupo:

1. En la página **Directivas de estacionamiento de llamadas** , en la pestaña **Asignación de directiva** de grupo, haga clic en **Agregar grupo**.

2. Busque el grupo que desea usar y, a continuación, haga clic en **Agregar**.

3. Elija una clasificación en comparación con otras tareas de grupo.

4. En **Seleccionar una directiva**, elija la directiva a la que desea asignar este grupo.

5. Seleccione **Aplicar**.

## <a name="use-powershell"></a>Usar PowerShell

Para administrar el parque de llamadas y recuperar directivas con PowerShell, use los siguientes cmdlets del módulo de PowerShell de Teams:

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>Ejemplos

#### <a name="new-custom-call-park-policy"></a>Nueva directiva de parque de llamadas personalizada

En el ejemplo siguiente se crea una directiva de parque de llamadas personalizada que genera números de recogida de 500 a 1500, y que llamará de vuelta al parker después de 600 segundos si la llamada estacionada no se responde.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>Cambiar una directiva de parque de llamadas

En el ejemplo siguiente se deshabilita la directiva de parque de llamadas:

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>Conceder una directiva de parque de llamadas a un usuario

En el ejemplo siguiente se concede la directiva de parque de llamadas a un usuario:

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>Quitar una directiva de parque de llamadas

En el ejemplo siguiente se quita la directiva de parque de llamadas:

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>Temas relacionados

[Estacionar una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

