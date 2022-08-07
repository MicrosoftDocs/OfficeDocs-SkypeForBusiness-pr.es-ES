---
title: Enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre Teams Phone System con enrutamiento directo.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269925"
---
# <a name="direct-routing"></a>Enrutamiento directo

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [Reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora ya está listo para agregar cargas de trabajo de voz y ha decidido usar su propio operador de telefonía para la conectividad de la red telefónica conmutada (RTC) mediante El sistema telefónico con enrutamiento directo. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier proveedor de servicios de telefonía.

En este artículo se describen las decisiones principales de implementación del enrutamiento directo, así como consideraciones adicionales que puede que quiera considerar, en función de las necesidades de su organización. También debería leer [Planear la solución de voz](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Más información sobre enrutamiento directo

En los artículos siguientes se proporciona más información sobre cómo configurar y usar el enrutamiento directo. Configurar el enrutamiento directo requiere información sobre el diseño del enrutamiento RTC. Lea todos estos artículos para comprender cómo planear y configurar el enrutamiento directo:

- [Planear el enrutamiento directo](direct-routing-plan.md) 
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)
- [Supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md)

Además, es posible que quiera leer los artículos siguientes según sus requisitos:

-  [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md)
-  [Migrar a enrutamiento directo](direct-routing-migrating.md)
-  [Cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vea la siguiente sesión para obtener más información sobre enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las decisiones principales que debe tener en cuenta para el enrutamiento directo. 

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
|¿Para qué usuarios habilitaré el enrutamiento directo? | Para obtener más información, consulte [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md). |
¿Tengo las licencias necesarias para Direct Routing? | Para obtener más información, consulte [Concesión de licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones del controlador de borde de sesión (SBC)

Con el enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico. Para obtener una lista de LOSC certificados, consulte [Controladores de borde de sesión compatibles](direct-routing-border-controllers.md).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Dónde y cómo implementaré los SBCs? | Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md) | 
¿Tengo varios inquilinos? | Para obtener más información, vea [Configurar un controlador de borde de sesión para varios espacios empresariales](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Consideraciones de enrutamiento de voz

Tendrá que configurar Sistema telefónico para redirigir las llamadas a los SBCs específicos.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear? | Para obtener información sobre el enrutamiento de voz, consulte [Configurar el enrutamiento de voz](direct-routing-configure.md).
| ¿Qué usuarios se asignarán a la directiva de enrutamiento de voz que defina? | Vea los ejemplos en [Configurar el enrutamiento de voz](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Asegúrese de que las llamadas entrantes lleguen al cliente de Teams con TeamsUpgradePolicy

Enrutamiento directo solo se admite con Microsoft Teams. Para recibir llamadas RTC a través de enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciben en Teams. Los usuarios deben estar en el modo TeamsOnly, lo que puede hacer si les asigna la instancia de "UpgradeToTeams" de TeamsUpgradePolicy. 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué significa el modo TeamsOnly? | Para obtener más información, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).|
|||


