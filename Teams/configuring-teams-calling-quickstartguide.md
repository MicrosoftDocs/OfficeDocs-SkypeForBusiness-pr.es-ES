---
title: 'Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams'
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guía de inicio rápido para configurar Planes de llamada en Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 980bb0ad6602cc25df5743f1932fbc76092e7842
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516826"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams
==============================================================

Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.

Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Se recomienda que, en paralelo con esta guía de inicio rápido, lea [Sistema telefónico con planes de llamada](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear y unidad de una implementación correcta.

Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.
Para habilitar la ficha de **llamadas** en los equipos de los usuarios necesitan tener habilitada en los equipos de llamada y utilizando a un cliente de los equipos que admite una llamada a los equipos de 1:1 de 1:1. Para obtener información sobre cómo administrar las llamadas a 1:1 en los equipos, lea [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para obtener información sobre los clientes que admiten las llamadas, lea [los límites y las especificaciones de los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> En la actualidad, correo de voz no estará disponible en la ficha llamadas a menos que el usuario está habilitado para las llamadas de RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Requisitos previos para habilitar el **Teclado de marcado** en los equipos
Para habilitar la ficha de **Teclado de marcado** en los equipos y permitir que los usuarios a realizar y recibir llamadas de RTC debe abastecer a los usuarios para el sistema telefónico y planes de llamada. Para obtener información sobre cómo configurar planes de llamada, lea [Configurar planes de llamada](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> También puede usar el enrutamiento directo para permitir a los usuarios a realizar y recibir llamadas de RTC. Para obtener información sobre cómo configurar el enrutamiento directo, leer la [Configuración de enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso de TeamsUpgradePolicy para control donde land llamadas
Para controlar si las llamadas entrantes (y chats) land en los equipos o Skype para la empresa, los administradores usan TeamsUpgradePolicy, mediante cualquiera de [Centro de administración de equipos de Microsoft](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con el [Skype para la empresa](https://docs.microsoft.com/powershell/module/skype) cmdlets.


La configuración predeterminada de TeamsUpgradePolicy es el modo islas, que está diseñado para asegurarse de que los flujos de trabajo no se interrumpen durante una implementación de los equipos de negocio existentes. De forma predeterminada, VoIP, RTC y las llamadas a los usuarios federadas seguirán deben enrutarse a Skype para la empresa hasta que actualice la directiva para habilitar las llamadas entrantes a los equipos.  Cuando los destinatarios se encuentran en modo de islas:

 - VOIP entrante llama a ese originadas en Skype para la empresa siempre land en Skype del destinatario para clientes empresariales.
 - VOIP entrante llama a se ha originado en el mundo de los equipos en los equipos, *Si el remitente y el destinatario se encuentran en el mismo arrendatario*.
 - Entrante federados VOIP (independientemente del cliente que se origina) y llamadas RTC siempre land en Skype del destinatario para clientes empresariales.
 
Para asegurarse de que entrante VOIP y RTC llama siempre land en los equipos cliente de un usuario, actualizar el modo de coexistencia del usuario para que sea TeamsOnly (lo que significa que les asigne la instancia de "UpgradeToTeams" de TeamsUpgradePolicy.  Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**NOTAS**
 - Skype para teléfonos IP empresarial va a recibir llamadas, incluso si el usuario está en modo de TeamsOnly.  
 - Usuarios que ya han aprovisionados con el sistema telefónico y llamar a los planes de licencias para su uso con Skype para profesionales en línea (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tendrá la ficha llamadas habilitada en los equipos y puede colocar las llamadas RTC salientes desde Equipos sin tener que realizar ninguna acción administrativa de los administradores.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Cómo configurar usuarios para recibir todos los entrantes VOIP y RTC llama en los equipos
Para asegurarse de que los usuarios reciben todas las llamadas entrantes de VOIP y RTC en los equipos, establezca el modo de coexistencia del usuario como TeamsOnly en el centro de administración de Microsoft Teams o usar Skype para la sesión remota de Windows PowerShell de negocio para actualizar TeamsUpgradePolicy de la siguiente manera:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Consulte también
[Configurar planes de llamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema telefónico con planes de llamada](calling-plan-landing-page.md)

[Skype para referencia del cmdlet de PowerShell de negocio](https://docs.microsoft.com/powershell/module/skype)

