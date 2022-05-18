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
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465451"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamiento y recuperación de llamadas en Microsoft Teams

Estacionar y recuperar llamadas es una característica que permite a un usuario poner una llamada en espera. Cuando se estaciona una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionó la llamada u otra persona puede usar ese código con una aplicación o dispositivo compatible para recuperar la llamada. (Consulta [Estacionar una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obtener más información).

Algunos de los escenarios comunes para usar el parque de llamadas son:

- Una recepcionista estaciona una llamada para alguien que trabaja en una fábrica. A continuación, el recepcionista anuncia la llamada y el número de código sobre el sistema de direcciones públicas. El usuario para el que es la llamada puede, a continuación, recoger un teléfono Teams en la fábrica e introducir el código para recuperar la llamada.
- Un usuario estaciona una llamada en un dispositivo móvil porque la batería del dispositivo se está quedando sin energía. A continuación, el usuario puede escribir el código para recuperar la llamada desde un teléfono de escritorio Teams.
- Un representante de soporte técnico estaciona una llamada de cliente y envía un anuncio en un canal de Teams para que un experto recupere la llamada y ayude al cliente. Un experto escribe el código en Teams clientes para recuperar la llamada

Para aparcar y recuperar llamadas, un usuario debe ser un usuario Telefonía IP empresarial y debe estar incluido en una directiva de parque de llamadas.

> [!NOTE]
> La opción de aparcar y recuperar llamadas solo está disponible en [Teams modo de implementación](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no se admite en teléfonos IP Skype Empresarial.

## <a name="configure-call-park-and-retrieve"></a>Configurar el parque de llamadas y recuperar

Debe ser un administrador de Teams para configurar el parque de llamadas y recuperarla. Está deshabilitada de forma predeterminada. Puede habilitarlo para los usuarios y crear grupos de usuarios mediante la directiva de parque de llamadas. Al aplicar la misma directiva a un conjunto de usuarios, estos pueden aparcar y recuperar llamadas entre sí.

De forma predeterminada, el intervalo de números de recogida de llamadas es del 10 al 99. También puede crear su propio rango personalizado entre 10 y 9999. La primera llamada estacionada se representará como un código de recogida del inicio del intervalo (por ejemplo, 10). La siguiente llamada estacionada se representará un código de recogida incrementado por 1; es decir, 11, y así sucesivamente, hasta que el final del intervalo se representa como un código de recogida. Después, los códigos de recogida representados vuelven a empezar desde el principio del intervalo. 

Puede especificar un tiempo de espera como el número de segundos de espera antes de volver a llamar cuando la llamada estacionada no se ha recogido. El intervalo permitido es de 120-1800 segundos y el valor predeterminado es 300 segundos.

Para habilitar una directiva de parque de llamadas:

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a Directivas de **parque** **de VoiceCall** > .
2. En la pestaña **Administrar directivas** , haga clic en **Agregar**.
3. Asigna un nombre a la directiva y, a continuación, cambia **Permitir parque de llamadas** a **Activado**.
4. Cambie el intervalo y el tiempo de espera del parque según sea necesario.
5. Seleccione **Guardar**.

Puede editar la directiva seleccionándola en la lista y haciendo clic en **Editar**.

Para que la directiva funcione, debe asignarse a los usuarios. Puede [asignar la directiva a los usuarios individualmente](assign-policies-users-and-groups.md) o asignarlos a un grupo.

Para asignar una directiva de parque de llamadas a un grupo

1. En la página **Directivas de estacionamiento de llamadas** , en la pestaña **Asignación de directiva** de grupo, haga clic en **Agregar grupo**.
2. Busque el grupo que desea usar y, a continuación, haga clic en **Agregar**.
3. Elija una clasificación en comparación con otras tareas de grupo.
4. En **Seleccionar una directiva**, elija la directiva a la que desea asignar este grupo.

    ![imagen de políticas de parque.](media/call-park-assign-policy-to-group.png)

5. Seleccione **Aplicar**.

## <a name="related-topics"></a>Temas relacionados

[Estacionar una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
