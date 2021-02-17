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
ms.openlocfilehash: 7474b80975c5fc78285a8bba5a90de782f24ba5b
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260332"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación de llamadas en Microsoft Teams

La característica de estacionar y recuperar llamadas es una característica que permite a un usuario poner una llamada en espera. Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionó la llamada o cualquier otra persona puede usar ese código con una aplicación o dispositivo compatible para recuperar la llamada. (Consulte [Estacione una llamada en Teams para](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) obtener más información).

Algunos de los escenarios comunes para usar el parque de llamadas son:

- Un parque de recepciones es una llamada para alguien que trabaja en una fábrica. El recepcionista anunciará entonces la llamada y el número de código a través del sistema de direcciones públicas. El usuario para el que se llama puede elegir un teléfono de Teams en la planta de fábrica y escribir el código para recuperar la llamada.
- Un parque de usuarios es una llamada en un dispositivo móvil porque la batería del dispositivo se está quedando sin energía. Después, el usuario puede escribir el código para recuperar la llamada desde un teléfono de escritorio de Teams.
- Un representante de soporte técnico llama a un cliente y envía un anuncio en un canal de Teams para que un experto recupere la llamada y ayude al cliente. Un experto escribe el código en los clientes de Teams para recuperar la llamada

Para estacionar y recuperar llamadas, un usuario debe ser Telefonía IP empresarial usuario y debe incluirse en una directiva de parque de llamadas.

> [!NOTE]
> El parque de llamadas y la recuperación solo está disponible en el modo de implementación [de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no es compatible con los teléfonos IP de Skype Empresarial.

## <a name="configure-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

Debe ser administrador de Teams para configurar el parque de llamadas y recuperarlo. Está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios con la directiva de parque de llamadas. Cuando aplica la misma directiva a un conjunto de usuarios, estos pueden estacionar y recuperar llamadas entre ellos.

Para habilitar una directiva de parque de llamadas

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas **del parque de** llamadas de  >  **voz.**
2. En la pestaña **Administrar directivas,** haga clic **en Agregar.**
3. Asigne un nombre a la directiva y, a continuación, cambie Permitir el **parque de llamadas** a **Activar.**

    ![Captura de pantalla de la configuración de directiva de parque de llamadas](media/call-park-add-policy.png)

4. Seleccione **Guardar**.

Puede editar la directiva seleccionándosela en la lista y haciendo clic en **Editar.**

Para que la directiva funcione, debe asignarse a los usuarios. Puede asignar [la directiva a los usuarios individualmente](assign-policies.md) o asignarlos a un grupo.

Para asignar una directiva de elemento de llamada a un grupo

1. En la página **Directivas de parque de** llamadas, en la pestaña **Asignación de** directivas de grupo, haga clic en Agregar **grupo.**
2. Busque el grupo que desea usar y, a continuación, haga clic en **Agregar.**
3. Elija una clasificación en comparación con otras tareas de grupo.
4. En **Seleccionar una directiva,** elija la directiva a la que desea asignar este grupo.

    ![](media/call-park-assign-policy-to-group.png)

5. Haga clic en **Aplicar**.

## <a name="related-topics"></a>Temas relacionados

[Estacionar una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
