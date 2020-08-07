---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 04/12/2019
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Obtenga más información sobre cómo usar el servicio de atención telefónica y recuperar para poner una llamada en espera en el servicio de Teams en la nube.
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582657"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación de llamadas en Microsoft Teams

Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera en el servicio de Teams en la nube. Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que ha aparcado la llamada u otra persona puede usar ese código y una aplicación o dispositivo admitido para recuperar la llamada. 

Algunos de los escenarios comunes para usar el parque de llamadas son: 

- Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica. El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública. El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.
- Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando. Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.
- Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente. Un experto escribe el código de los clientes de Teams para recuperar la llamada

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación solo para equipos. Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia requerida

Para detener y recuperar llamadas, un usuario debe ser un usuario de telefonía empresarial y un administrador debe concederle una directiva de estacionamiento de llamadas. Para obtener más información sobre el modelo de licencias, vea [Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="call-park-and-retrieve-feature-availability"></a>Llamar a estacionamiento y recuperar la disponibilidad de características

En la actualidad, los siguientes clientes y dispositivos son compatibles con la función deestacionamiento y recuperar. (Compatible con el modo solo de Teams, con o sin conectividad RTC).

| Función | Equipo de escritorio | Aplicación de equipos Mac | Teams Web App (Edge) |Teams Mobile iOS/aplicación para Android | Teléfono IP de Teams | Teléfono IP de Skype empresarial |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Detener una llamada | Sí | Sí | Sí | Sí | Sí | No |
| Recuperar una llamada estacionada | Sí | Sí | Sí | Sí | Sí | No |
| Timbre de llamada no recuperado | Sí | Sí | Sí | Sí | Sí | No |

## <a name="configure-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

Debe ser administrador para configurar el parque de llamadas y recuperar, y la característica está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas. Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí. Para configurar el parque de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamadas, siga el procedimiento [asignar una directiva de estacionamiento de llamadas](#assign-a-call-park-policy) que se muestra a continuación.

Para obtener más información sobre cómo usar la característica Parque de llamadas y recuperar, consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Habilitar una directiva de estacionamiento de llamadas

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.
2. Seleccione **Agregar**.
3. Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.
4. Seleccione **Guardar**.

#### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).

### <a name="edit-a-call-park-policy"></a>Editar una directiva de estacionamiento de llamadas

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Cambie **permitir** que el parque de llamadas esté **desactivado** o **activado**.
4. Haga clic en **Guardar **.

#### <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps). Por ejemplo, para cambiar la configuración predeterminada, ejecute lo siguiente:

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a>Asignar una directiva de estacionamiento de llamadas

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
Consulte también [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).

## <a name="troubleshooting"></a>Solución de problemas

Si los usuarios no pueden ver el botón detener o recuperar: 

- Compruebe que el usuario tiene habilitada la Directiva de estacionamiento de llamadas. 

Si un usuario intenta recuperar una llamada y no se ha realizado correctamente, compruebe lo siguiente:

- Comprobar que el usuario está usando el cliente de Teams o un dispositivo/teléfono habilitado para Teams
- Agrupación: el usuario es miembro del grupo de estacionamiento de llamada, que se basa en que los mismos equipos tienen asignada la política de estacionamiento. 
- Modo isla: la llamada de estacionamiento y recuperar no está disponible en el modo isla de Teams.
- Ya se ha recuperado o finalizado la llamada.

## <a name="related-topics"></a>Temas relacionados

[Detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
