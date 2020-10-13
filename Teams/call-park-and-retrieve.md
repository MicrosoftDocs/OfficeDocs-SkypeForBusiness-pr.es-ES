---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el parque de llamadas y recuperar para poner una llamada en espera en Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424600"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación de llamadas en Microsoft Teams

Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera. Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que ha aparcado la llamada u otra persona puede usar ese código con una aplicación o dispositivo admitido para recuperar la llamada. (Consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obtener más información).

Algunos de los escenarios comunes para usar el parque de llamadas son:

- Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica. El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública. El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.
- Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando. Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.
- Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente. Un experto escribe el código de los clientes de Teams para recuperar la llamada

Para detener y recuperar llamadas, un usuario debe ser un usuario de voz de empresa y debe estar incluido en una directiva de Parque de llamadas.

> [!NOTE]
> La llamada en estacionamiento y recuperar solo está disponible en el [modo de implementación solo de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no es compatible con los teléfonos IP de Skype empresarial.

## <a name="configure-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

Debe ser un administrador de equipo para configurar el parque de llamadas y recuperar. Está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas. Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí.

Para habilitar una directiva de estacionamiento de llamadas

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.
2. En la pestaña **Administrar directivas** , haga clic en **Agregar**.
3. Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.

    ![Captura de pantalla de la configuración de directiva de estacionamiento de llamadas](media/call-park-add-policy.png)

4. Seleccione **Guardar**.

Para editar la Directiva, selecciónela en la lista y haga clic en **Editar**.

Para que la Directiva funcione, debe estar asignada a los usuarios. Puede [asignar la Directiva a los usuarios individualmente](assign-policies.md) o asignarlos a un grupo.

Para asignar una directiva de papel de llamada a un grupo

1. En la página **directivas de estacionamiento** , en la pestaña asignación de directivas de **Grupo** , haga clic en **Agregar grupo**.
2. Busque el grupo que desea usar y, a continuación, haga clic en **Agregar**.
3. Elija un rango comparado con otras asignaciones de grupo.
4. En **seleccionar una directiva**, elija la Directiva a la que desea asignar este grupo.

    ![](media/call-park-assign-policy-to-group.png)

5. Haga clic en **Aplicar**.

## <a name="related-topics"></a>Temas relacionados

[Detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Asignar directivas a los usuarios de Teams](assign-policies.md)

[Nuevo: CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)