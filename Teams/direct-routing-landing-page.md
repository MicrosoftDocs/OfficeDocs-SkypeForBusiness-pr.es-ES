---
title: Enrutamiento directo del Sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de aterrizaje para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: decbe74eaece7508c2118175bd25f8acab200cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572195"
---
# <a name="phone-system-direct-routing"></a>Enrutamiento directo del Sistema telefónico

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar cargas de trabajo de voz de nube y ha decidido usar su propio operador de telefonía para conectividad de red telefónica conmutada (RTC) con enrutamiento directo de sistema telefónico. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier operador de telefonía.

En este artículo se describen las decisiones básicas de implementación para el enrutamiento directo, así como otras consideraciones adicionales, según las necesidades de la organización. También debe leer [la voz de nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de nube de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Más información sobre el enrutamiento directo

Los artículos siguientes proporcionan más información sobre cómo configurar y usar el enrutamiento directo del sistema telefónico. La configuración del enrutamiento directo requiere comprender el diseño de enrutamiento de RTC. Debe leer todos estos artículos para comprender cómo planificar y configurar el enrutamiento directo:

- [Planear el enrutamiento directo](direct-routing-plan.md) 
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)
- [Supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md)

Además, es posible que desee leer los artículos siguientes según sus necesidades:

-  [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md)
-  [Migrar a enrutamiento directo](direct-routing-migrating.md)
-  [Cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vea la siguiente sesión para obtener más información sobre el enrutamiento directo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las decisiones básicas para considerar el enrutamiento directo. 

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
|¿Para qué usuarios habilitaría el enrutamiento directo? | Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md#enable-users-for-direct-routing-service). |
¿Tengo las licencias necesarias para el enrutamiento directo? | Para obtener más información, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones del controlador de borde de sesión (SBC)

Con el enrutamiento directo, conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.  Para obtener una lista de SBCs certificado, consulte [controladores de borde de sesión admitidos](direct-routing-border-controllers.md).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Dónde y cómo implementar SBCs? | Para obtener más información, consulte [configurar el enrutamiento directo](direct-routing-configure.md) | 
¿Tengo varios inquilinos? | Para obtener más información, vea [configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Consideraciones de enrutamiento de voz

Tendrá que configurar el sistema telefónico para enrutar las llamadas al SBCs específico.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, uso de RTC y rutas de voz necesito crear? | Para obtener información sobre el enrutamiento de voz, vea [configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).
| ¿Qué usuarios se asignarán a la Directiva de enrutamiento de voz que definio? | Consulte los ejemplos de [configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Asegurarse de que las llamadas entrantes estén en el cliente de Teams mediante TeamsUpgradePolicy

El enrutamiento directo solo es compatible con Microsoft Teams. Para recibir llamadas RTC mediante enrutamiento directo, debe configurar TeamsUpgradePolicy para asegurarse de que las llamadas entrantes se reciban en Teams. Los usuarios deben estar en el modo solo de equipos, que puede hacer asignando la instancia "UpgradeToTeams" de TeamsUpgradePolicy. 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué significa el modo solo de Teams? | Para obtener más información, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Consideraciones de implementación adicionales

Es posible que desee tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:

| Pregúntese lo siguiente:| Acción |
| :------------|:-------|
| ¿Tiene una implementación existente de Skype empresarial Server con una conectividad híbrida configurada? |  Para comprender cómo se suministran y administran las cuentas de usuario en un entorno híbrido, consulte [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| ¿Va a migrar el enrutamiento directo desde el plan de llamadas o desde un entorno local de Skype empresarial? | Para obtener más información sobre cómo migrar para dirigir el enrutamiento desde un entorno existente, consulte [migrar a enrutamiento directo](direct-routing-migrating.md). |
|||
