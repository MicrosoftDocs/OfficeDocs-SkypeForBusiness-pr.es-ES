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
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información Teams Sistema telefónico con enrutamiento directo.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518712"
---
# <a name="direct-routing"></a>Enrutamiento directo

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Quizás haya implementado Reuniones & [conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora ya está listo para agregar cargas de trabajo de voz y ha decidido usar su propio operador de telefonía para la conectividad de red telefónica conmutada (RTC) mediante Sistema telefónico con enrutamiento directo. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier proveedor de servicios de telefonía.

En este artículo se describen las decisiones básicas de implementación para enrutamiento directo, así como consideraciones adicionales en las que puede pensar, en función de las necesidades de su organización. También debe leer [Planear la solución de voz](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Más información sobre enrutamiento directo

En los artículos siguientes se proporciona más información sobre cómo configurar y usar enrutamiento directo. Configurar enrutamiento directo requiere comprender el diseño de enrutamiento RTC. Debe leer todos estos artículos para comprender cómo planear y configurar enrutamiento directo:

- [Planear el enrutamiento directo](direct-routing-plan.md) 
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)
- [Supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md)

Además, es posible que desee leer los siguientes artículos según sus requisitos:

-  [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md)
-  [Migrar a enrutamiento directo](direct-routing-migrating.md)
-  [Cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vea la siguiente sesión para obtener más información sobre enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las decisiones principales que debe tener en cuenta para enrutamiento directo. 

|Pregúntese lo siguiente:|Action |
| :------------|:-------|
|¿Para qué usuarios habilitaré enrutamiento directo? | Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md). |
¿Tengo las licencias necesarias para enrutamiento directo? | Para obtener más información, vea [Licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones del Controlador de borde de sesión (SBC)

Con enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente a Sistema telefónico. Para obtener una lista de SBC certificados, vea [Controladores de borde de sesión compatibles](direct-routing-border-controllers.md).

|Pregúntese lo siguiente:|Action |
|:------------|:-------|
| ¿Dónde y cómo implementar los SBC? | Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md) | 
¿Tengo varios inquilinos? | Para obtener más información, vea [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Consideraciones de enrutamiento de voz

Tendrá que configurar los Sistema telefónico para enrutar las llamadas a los SBC específicos.

|Pregúntese lo siguiente:|Action |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear? | Para obtener información sobre el enrutamiento de voz, vea [Configurar enrutamiento de voz](direct-routing-configure.md).
| ¿Qué usuarios se asignarán a la directiva de enrutamiento de voz que defina? | Vea los ejemplos en [Configurar enrutamiento de voz](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Asegurarse de que las llamadas entrantes se Teams cliente mediante TeamsUpgradePolicy

El enrutamiento directo solo es compatible con Microsoft Teams. Para recibir llamadas RTC a través del enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciben en Teams. Los usuarios deben estar en modo TeamsOnly, que puede hacer asignándolos la instancia "UpgradeToTeams" de TeamsUpgradePolicy. 

|Pregúntese lo siguiente:|Action |
|:------------|:-------|
|¿Qué significa el modo TeamsOnly? | Para obtener más información, vea [Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md).|
|||


