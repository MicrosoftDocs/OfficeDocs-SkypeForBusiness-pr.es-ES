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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de aterrizaje para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dca9fda99973931cff70301da089f6d0c3f4a9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236592"
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

### <a name="calling-and-interop-policies"></a>Directivas de llamadas y interoperabilidad

El enrutamiento directo solo es compatible con Microsoft Teams. Para realizar o recibir llamadas RTC mediante enrutamiento directo, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciban en Teams. Puede configurar los usuarios para que establezcan equipos como su cliente preferido para las llamadas, ya sea configurando el usuario para el modo solo de Teams o configurando Teams como el cliente de llamadas preferido asignando el TeamsCallingPolicy y TeamsInteropPolicy.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Cómo establezco Teams como el cliente preferido para las llamadas? | Para obtener más información, vea [establecer Microsoft Teams como el cliente de llamadas preferido para los usuarios](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Consideraciones de implementación adicionales

Es posible que desee tener en cuenta lo siguiente, en función de las necesidades y la configuración de su organización:

| Pregúntese lo siguiente:| Acción |
| :------------|:-------|
| ¿Tiene una implementación existente de Skype empresarial Server con una conectividad híbrida configurada? |  Para comprender cómo se suministran y administran las cuentas de usuario en un entorno híbrido, consulte [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| ¿Va a migrar el enrutamiento directo desde el plan de llamadas o desde un entorno local de Skype empresarial? | Para obtener más información sobre cómo migrar para dirigir el enrutamiento desde un entorno existente, consulte [migrar a enrutamiento directo](direct-routing-migrating.md). |
|||
