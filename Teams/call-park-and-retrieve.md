---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: Use estacionamiento y recuperar para poner una llamada en espera en el servicio de Teams en la nube.
ms.openlocfilehash: 01d46aff527a0e846b6bb552f5b3241deb3d9c14
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483427"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación de llamadas en Microsoft Teams

Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera en el servicio de Teams en la nube. Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que ha aparcado la llamada u otra persona puede usar ese código y una aplicación o dispositivo admitido para recuperar la llamada. 

Algunos de los escenarios comunes para usar el parque de llamadas son: 

- Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica. El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública. El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.
- Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando. Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.
- Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente. Un experto escribe el código de los clientes de Teams para recuperar la llamada

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación solo para equipos. Para obtener más información sobre los modos de implementación de Teams, consulte comprender la coexistencia y la interoperabilidad [de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia requerida

Para detener y recuperar llamadas, un usuario debe ser un usuario de telefonía empresarial y un administrador debe concederle una directiva de estacionamiento de llamadas. Para obtener más información sobre el modelo de licencias, consulte [licencias de Office 365 para Microsoft Teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Llamar a estacionamiento y recuperar la disponibilidad de características

En la actualidad, los siguientes clientes y dispositivos son compatibles con la función deestacionamiento y recuperar. (Compatible con el modo solo de Teams, con o sin conectividad RTC).

| Capacidades | Equipo de escritorio | Aplicación de equipos Mac | Teams Web App (Edge) |Teams Mobile iOS/aplicación para Android | Teléfono IP de Teams | Teléfono IP de Skype empresarial |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Detener una llamada | Sí | Sí | Sí | Sí | Próximamente| No |
| Recuperar una llamada estacionada | Sí | Sí | Sí | Sí | Próximamente| No |
| Timbre de llamada no recuperado | Sí | Sí | Sí | Sí | Próximamente| No |

## <a name="configuring-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

Debe ser administrador para configurar el parque de llamadas y recuperar, y la característica está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas. Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí. Para configurar el parque de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamadas, siga el procedimiento [asignar una directiva de estacionamiento de llamadas](#assign-a-call-park-policy) que se muestra a continuación.

Para obtener más información sobre cómo usar la característica Parque de llamadas y recuperar, consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Habilitar una directiva de estacionamiento de llamadas

Siga estos pasos para habilitar una directiva de estacionamiento de llamadas:

1. Vaya al **Centro** > de administración de Microsoft Teams**directivas de estacionamiento de llamadas**de**voz** > .
2. Seleccione **nueva Directiva**.
3. Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.
4. Seleccione **Guardar**.

### <a name="assign-a-call-park-policy"></a>Asignar una directiva de estacionamiento de llamadas

Siga estos pasos para asignar una directiva de estacionamiento de llamadas a uno o más usuarios:

1. Vaya al **Centro** > de administración de Microsoft Teams**directivas de estacionamiento de llamadas**de**voz** > .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurar el parque de llamadas y recuperar con PowerShell

Use el cmdlet [de PowerShell New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) para crear una directiva de estacionamiento de llamadas.

Use el cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) de PowerShell para conceder una directiva de estacionamiento de llamadas.

Puede cambiar la configuración predeterminada con [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) de la siguiente manera:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Solución de problemas

Si los usuarios no pueden ver el botón detener o recuperar: 

- Compruebe que el usuario tiene habilitada la Directiva de estacionamiento de llamadas. 

Si un usuario intenta recuperar una llamada y no se ha realizado correctamente, compruebe lo siguiente:

- Comprobar que el usuario está usando el cliente de Teams o un dispositivo/teléfono habilitado para Teams
- Agrupación: ¿es el usuario miembro del grupo de estacionamiento de llamadas?
- Modo isla: la llamada de estacionamiento y recuperar no está disponible en el modo isla de Teams.
- Ya se ha recuperado o finalizado la llamada.

## <a name="more-information"></a>Más información

[Estacione una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).