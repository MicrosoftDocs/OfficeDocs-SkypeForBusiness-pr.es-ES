---
title: Enrutamiento directo del sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre enrutamiento directo, como la configuración, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031826"
---
# <a name="phone-system-direct-routing"></a>Enrutamiento directo del sistema telefónico

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [Reuniones & conferencia.](deploy-meetings-microsoft-teams-landing-page.md) Ahora está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar su propio operador de telefonía para la conectividad de red telefónica conmutada (RTC) con el enrutamiento directo del sistema telefónico. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier proveedor de servicios de telefonía.

En este artículo se describen las decisiones básicas de implementación de enrutamiento directo, así como consideraciones adicionales que quizás quiera tener en cuenta en función de las necesidades de su organización. También debe leer [Cloud Voice en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Más información sobre enrutamiento directo

En los artículos siguientes se proporciona más información sobre cómo configurar y usar el enrutamiento directo de sistema telefónico. Para configurar el enrutamiento directo es necesario comprender el diseño del enrutamiento RTC. Debe leer todos estos artículos para comprender cómo planear y configurar el enrutamiento directo:

- [Planear el enrutamiento directo](direct-routing-plan.md) 
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)
- [Supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md)

Además, es posible que desee leer los artículos siguientes según sus requisitos:

-  [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md)
-  [Migrar a enrutamiento directo](direct-routing-migrating.md)
-  [Cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vea la siguiente sesión para obtener más información sobre enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las decisiones básicas que debe tener en cuenta para el enrutamiento directo. 

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
|¿Para qué usuarios habilitaré enrutamiento directo? | Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo.](direct-routing-configure.md) |
¿Tengo las licencias necesarias para enrutamiento directo? | Para obtener más información, vea [Licencias y otros requisitos.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones del controlador de borde de sesión (SBC)

Con el enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.  Para obtener una lista de los SBC certificados, consulte Controladores de borde [de sesión compatibles.](direct-routing-border-controllers.md)

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Dónde y cómo implementaré los SBC? | Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md) | 
¿Tengo varios inquilinos? | Para obtener más información, vea [Configurar un controlador de borde de sesión para varios inquilinos.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Consideraciones de enrutamiento de voz

Tendrá que configurar Sistema telefónico para enrutar las llamadas a los SBC específicos.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear? | Para obtener información sobre el enrutamiento de voz, [vea Configurar el enrutamiento de voz.](direct-routing-configure.md)
| ¿Qué usuarios se asignarán a la directiva de enrutamiento de voz que defina? | Vea los ejemplos en Configurar [enrutamiento de voz.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Asegurarse de que las llamadas entrantes se des fijos en el cliente de Teams con TeamsUpgradePolicy

El enrutamiento directo solo se admite con Microsoft Teams. Para recibir llamadas RTC a través del enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciben en Teams. Los usuarios deben estar en modo Solo equipos, lo que puede hacer si les asigna la instancia "UpgradeToTeams" de TeamsUpgradePolicy. 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué significa el modo Solo en Teams? | Para obtener más información, vea las instrucciones de migración e interoperabilidad para las [organizaciones que usan Teams junto con Skype Empresarial.](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)|
|||

## <a name="additional-deployment-considerations"></a>Consideraciones de implementación adicionales

Es posible que quiera tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:

| Pregúntese lo siguiente:| Acción |
| :------------|:-------|
| ¿Tiene una implementación existente de Skype Empresarial Server con conectividad híbrida configurada? |  Para comprender cómo se aprovisionan y administran las cuentas de usuario en un entorno híbrido, vea Cuentas de usuario en un entorno híbrido [con conectividad con RTC.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| ¿Va a migrar al enrutamiento directo desde un plan de llamadas o desde un entorno local de Skype Empresarial? | Para obtener más información sobre cómo migrar a Enrutamiento directo desde un entorno existente, vea [Migrar a Enrutamiento directo.](direct-routing-migrating.md) |
|||
