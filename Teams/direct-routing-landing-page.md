---
title: Enrutamiento directo de teléfono del sistema
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de destino de enrutamiento directo
appliesto: Microsoft Teams
ms.openlocfilehash: 6aeff0f79dfbc6cd7b3ba3cddefee382673d24eb
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353269"
---
# <a name="phone-system-direct-routing"></a>Enrutamiento directo de teléfono del sistema

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar las cargas de trabajo de voz de la nube y ha decidido utilizar su propio operador de telefonía para la conectividad pública red de telefónica conmutada (RTC) mediante el uso de enrutamiento directo de teléfono del sistema. Con el enrutamiento directo, puede usar el sistema telefónico con prácticamente cualquier operador de telefonía.

En este artículo se describe la implementación las decisiones principales para el enrutamiento directo, así como consideraciones adicionales que es posible que desea configurar, en función de las necesidades de su organización.  También debe leer [En la nube de voz en los equipos de Microsoft](cloud-voice-landing-page.md) para obtener más información acerca de las ofertas de voz de la nube de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Encontrará más información acerca del enrutamiento directo


Los artículos siguientes proporcionan más información sobre cómo configurar y usar enrutamiento directo de teléfono del sistema. Configurar el enrutamiento directo requiere conocimientos de diseño de enrutamiento de RTC. Debe leer todos estos artículos para aprender a planear y configurar el enrutamiento directo:

- [Planear el enrutamiento directo](direct-routing-plan.md) 
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)
- [Supervisar y solucionar problemas de enrutamiento directo](direct-routing-monitor-and-troubleshoot.md)

Además, es posible que desee leer los artículos según los requisitos siguientes:

-  [Configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md)
-  [Migrar a enrutamiento directo](direct-routing-migrating.md)
-  [Cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vea la sesión siguiente para obtener más información acerca del enrutamiento directo: [El enrutamiento directo en los equipos de Microsoft](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estos son las decisiones principales a tener en cuenta para el enrutamiento directo. 


|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
|¿Para los usuarios que habilitará el enrutamiento directo? | Para obtener más información, vea [Habilitar usuarios para el servicio de enrutamiento directo](direct-routing-configure.md#enable-users-for-direct-routing-service). |
¿Tienen las licencias necesarias para el enrutamiento directo? | Para obtener más información, vea [Licensing y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Consideraciones de controlador de borde (SBC) de sesión

Con el enrutamiento directo, se conecta su propio controlador de borde de sesión (SBC) directamente al sistema telefónico.  Para obtener una lista de SBCs certificadas, vea [Admite controladores de borde de sesión](direct-routing-border-controllers.md).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Dónde y cómo va a implementar SBCs? | Para obtener más información, vea [Configurar el enrutamiento directo](direct-routing-configure.md) | 
¿Hay varios inquilinos? | Para obtener más información, vea [configurar un controlador de borde de sesión para varios inquilinos](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Consideraciones del enrutamiento de voz

Debe configurar el sistema telefónico para enrutar las llamadas a la SBCs específicos.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Qué directivas de enrutamiento de voz, el uso de RTC y rutas de voz necesito para crear? | Para obtener información de enrutamiento de voz, vea [Configurar el enrutamiento de voz](direct-routing-configure.md#configure-voice-routing).
| ¿Los usuarios que se asignará a la directiva de enrutamiento de voz que define? | Vea los ejemplos de [Configuración de enrutamiento de voz](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="calling-and-interop-policies"></a>Directivas de llamada y de interoperabilidad

Enrutamiento directo sólo es compatible con Microsoft Teams. Para realizar o recibir llamadas de RTC a través de enrutamiento directa, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciben en los equipos. Puede configurar usuarios para establecer los equipos como su cliente preferido para las llamadas, puede configurar el usuario para el modo de sólo los equipos o configurar los equipos como cliente preferido llamado mediante la asignación de la TeamsCallingPolicy y la TeamsInteropPolicy.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Cómo va a establecer los equipos como cliente preferido para las llamadas? | Para obtener más información, vea [establecer los equipos de Microsoft como el preferido llamar al cliente para los usuarios](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Consideraciones de implementación adicionales

Es posible que desee tener en cuenta los siguientes valores, en función de las necesidades de su organización y la configuración:

| Pregúntese lo siguiente:| Acción |
| :------------|:-------|
| ¿Tiene un Skype existente para la implementación de servidor empresarial con conectividad híbrida configurada? |  Para comprender cómo se aprovisionan cuentas de usuario en un entorno híbrido y administrados, vea [cuentas de usuario en un entorno híbrido con conectividad RTC](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| ¿Está migrando a enrutamiento directo de planeación de una llamada a o desde un Skype para entorno local de negocio? | Para saber más acerca de la migración para el enrutamiento directo desde un entorno existente, consulte [migración a enrutamiento directo](direct-routing-migrating.md). |
|||
