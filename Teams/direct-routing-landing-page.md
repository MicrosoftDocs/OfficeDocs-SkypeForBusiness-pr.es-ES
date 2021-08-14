---
title: Teléfono sistema de enrutamiento directo en Teams
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
description: Obtenga información sobre la configuración de enrutamiento directo, las decisiones básicas de implementación necesarias y las consideraciones de enrutamiento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b83e7ea9fd93787f71828141c3e9e3b681d9557b
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234265"
---
# <a name="phone-system-direct-routing"></a>Teléfono sistema de enrutamiento directo

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Puede que haya implementado Reuniones [& conferencias.](deploy-meetings-microsoft-teams-landing-page.md) Ahora ya está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar su propio operador de telefonía para la conectividad de red telefónica conmutada (RTC) mediante Sistema telefónico enrutamiento directo. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier proveedor de servicios de telefonía.

En este artículo se describen las decisiones básicas de implementación para enrutamiento directo, así como consideraciones adicionales en las que puede pensar, en función de las necesidades de su organización. También debe leer Voz en la [nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Más información sobre enrutamiento directo

En los artículos siguientes se proporciona más información sobre cómo configurar y usar Sistema telefónico enrutamiento directo. Configurar enrutamiento directo requiere comprender el diseño de enrutamiento RTC. Debe leer todos estos artículos para comprender cómo planear y configurar enrutamiento directo:

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

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
|¿Para qué usuarios habilitaré enrutamiento directo? | Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo.](direct-routing-configure.md) |
¿Tengo las licencias necesarias para enrutamiento directo? | Para obtener más información, vea [Licencias y otros requisitos.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones del Controlador de borde de sesión (SBC)

Con enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente a Sistema telefónico.  Para obtener una lista de SBC certificados, vea [Controladores de borde de sesión admitidos.](direct-routing-border-controllers.md)

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Dónde y cómo implementar los SBC? | Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md) | 
¿Tengo varios inquilinos? | Para obtener más información, vea [Configurar un controlador de borde de sesión para varios inquilinos.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Consideraciones de enrutamiento de voz

Tendrá que configurar los Sistema telefónico para enrutar las llamadas a los SBC específicos.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear? | Para obtener información sobre el enrutamiento de voz, vea [Configurar enrutamiento de voz.](direct-routing-configure.md)
| ¿Qué usuarios se asignarán a la directiva de enrutamiento de voz que defina? | Vea los ejemplos en [Configurar enrutamiento de voz.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Asegurarse de que las llamadas entrantes se Teams cliente mediante TeamsUpgradePolicy

El enrutamiento directo solo es compatible con Microsoft Teams. Para recibir llamadas RTC a través del enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciben en Teams. Los usuarios deben estar en Teams solo, que puede hacer asignándolos la instancia "UpgradeToTeams" de TeamsUpgradePolicy. 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué significa Teams modo Solo? | Para obtener más información, vea Instrucciones de migración e [interoperabilidad](./migration-interop-guidance-for-teams-with-skype.md)para organizaciones que usan Teams junto con Skype Empresarial .|
|||

## <a name="additional-deployment-considerations"></a>Consideraciones de implementación adicionales

Es posible que desee tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:

| Pregúntese lo siguiente:| Acción |
| :------------|:-------|
| ¿Tiene una implementación de Skype Empresarial Server con conectividad híbrida configurada? |  Para comprender cómo se aprovisionan y administran las cuentas de usuario en un entorno híbrido, vea Cuentas de usuario en un entorno híbrido con [conectividad RTC.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| ¿Va a migrar a Enrutamiento directo desde el plan de llamadas o desde un Skype Empresarial local? | Para obtener más información sobre cómo migrar a Enrutamiento directo desde un entorno existente, vea [Migrar a enrutamiento directo.](direct-routing-migrating.md) |
|||
