---
title: Configurar Sistema telefónico en su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Guía paso a paso que detalla cómo configurar Teams Phone System para su organización en Microsoft 365.
ms.openlocfilehash: beb82fd78fa58a4a3339dc1b7a5f54ceb5117479
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999545"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar Sistema telefónico en su organización

Este artículo proporciona un plan de desarrollo del contenido para la configuración del sistema telefónico: la tecnología de Microsoft para habilitar el control de llamadas y las funcionalidades de central de centrales privadas (PBX) en la nube de Microsoft 365. Los vínculos a información más detallada están disponibles al final de cada paso.

Antes de leer este artículo, asegúrate de que has leído [Qué es sistema telefónico](what-is-phone-system-in-office-365.md) y [esto es lo que obtienes con Sistema telefónico](here-s-what-you-get-with-phone-system.md). En estos dos últimos artículos se describen los requisitos y características del sistema telefónico.

En este artículo se describen los siguientes pasos:

- [Paso 1: Comprar y asignar una licencia de Sistema telefónico](#step-1-buy-and-assign-a-phone-system-license)
- [Paso 2: Elegir una opción de conectividad con RTC](#step-2-choose-a-pstn-connectivity-option)
- [Paso 3: Obtener números de teléfono para los usuarios](#step-3-get-phone-numbers-for-your-users)
- [Paso 4: Obtener números de teléfono para los servicios](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Paso 5: Si desea configurar una cola de llamadas](#step-5-if-you-want-to-set-up-a-call-queue)
- [Paso 6: Si desea configurar un operador automático](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Paso 7: Configurar créditos de comunicación para números gratuitos](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Paso 1: Comprar y asignar una licencia de Sistema telefónico

Para asignar una licencia de Sistema telefónico a un solo usuario, los pasos son los mismos que para asignar una licencia de Microsoft 365. También puede asignar licencias a varios usuarios de forma masiva. Para obtener más información sobre las licencias disponibles de Phone System y cómo adquirir y asignar licencias, consulte [Licencias de complementos de Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) y [Asignar licencias de complementos de Microsoft Teams](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Paso 2. Elegir una opción de conectividad con RTC

Para permitir que los usuarios realicen y reciban llamadas externas, deberá conectar el sistema telefónico a la red telefónica conmutada (RTC). Microsoft ofrece varias opciones para conectarse a LA RTC, entre las que se incluyen:

- Plan de llamadas. Una solución todo en la nube con Microsoft como su operador de RTC.

- Operador Conectar. Si su operador actual participa en el programa Microsoft Operator Connect, puede administrar las llamadas RTC y los controladores de borde de sesión (SFC) por usted.

- Enrutamiento directo. Use su propio operador RTC conectando sus SBCs a Phone System.

Para obtener más información sobre todas las opciones de conectividad, vea [Opciones de conectividad de RTC](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Paso 3: Obtener números de teléfono para los usuarios

[] Para poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe usar el Centro de administración de Skype Empresarial para obtener los números de teléfono.

Para obtener información sobre cómo administrar los números de teléfono de los usuarios, vea los artículos siguientes. La forma de administrar los números de un usuario depende de la opción de conectividad con RTC que elija.

- [Administrar números de teléfono para su organización](manage-phone-numbers-landing-page.md) : proporciona información general sobre los tipos de números de teléfono con vínculos a artículos específicos para adquirir y administrar números en función de la opción de conectividad con RTC.
Describe los dos tipos de [números de teléfono de usuario](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Asignar, cambiar o quitar un número de teléfono a un usuario](assign-change-or-remove-a-phone-number-for-a-user.md) : describe cómo asignar y administrar los números de teléfono que ha adquirido.

- [Cuántos números de teléfono puede obtener](how-many-phone-numbers-can-you-get.md) : describe cuántos números de teléfono puede obtener, dependiendo de los tipos de números de teléfono y tipos de licencias que haya comprado y asignado.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Paso 4: Obtener números de teléfono para los servicios (colas de llamadas, operadores automáticos)

Además de obtener números de teléfono para los usuarios, puede adquirir números de teléfono de pago o gratuitos para servicios como operadores automáticos y colas de llamadas. Un número de servicio puede administrar cientos de llamadas simultáneamente, mientras que el número de teléfono de un usuario solo puede atender algunas llamadas simultáneamente.

Puede obtener números de servicio de Microsoft incluidos en su licencia. Si tiene conectividad CON RTC a través de Operator Connect o Direct Routing, puede usar los números de servicio proporcionados por su propio operador o operador.

Para obtener más información, vea:

- [Administrar números de teléfono para su organización](manage-phone-numbers-landing-page.md) : proporciona información general sobre los tipos de números de teléfono con vínculos a artículos específicos para adquirir y administrar números en función de la opción de conectividad con RTC.
Describe los [números de teléfono de servicio](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponibles de Microsoft que se incluyen en la licencia. Para obtener información sobre los números de servicio proporcionados por el operador Conectar o enrutamiento directo, póngase en contacto con su proveedor.

- [Cuántos números de teléfono puede obtener](how-many-phone-numbers-can-you-get.md) : describe cuántos números de teléfono puede obtener, dependiendo de los tipos de números de teléfono y tipos de licencias que haya comprado y asignado.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Paso 5: Si desea configurar una cola de llamadas

Las colas de llamadas incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la posibilidad de buscar el siguiente agente de llamada disponible para administrar la llamada. Puede crear una o varias colas de llamadas para su organización.

Para obtener más información sobre las colas de llamadas, consulte [Crear una cola de llamadas](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Paso 6: Si desea configurar un operador automático

Los operadores automáticos permiten a las personas que llaman a su organización navegar por un sistema de menús para que lleguen al departamento, la cola de llamadas, la persona o el operador adecuados.

Para obtener información sobre cómo configurar operadores automáticos, vea [Configurar un operador automático](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Paso 7: Configurar créditos de comunicaciones para números gratuitos

Si desea usar números gratuitos con Microsoft Teams, tendrá que configurar créditos de comunicaciones. Las llamadas gratuitas se facturan por minuto y requieren un saldo positivo de créditos de comunicaciones.

Los créditos de comunicaciones son una forma cómoda de agregar números gratuitos para usarlos de la siguiente manera:

- Con números de servicio para aplicaciones de voz, como operadores automáticos o colas de llamadas.

- Para marcar cualquier número de teléfono internacional cuando tiene suscripciones a Planes de llamadas nacionales o más allá de lo que se incluye en una suscripción de Plan de llamadas nacionales e internacionales.

- Para llamar y pagar por minuto una vez que hayas agotado la asignación de minutos mensuales.

- Para llamar y pagar por minuto todas las llamadas salientes, si tiene un plan de llamadas de pago por uso.

Para obtener más información, consulte [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar los créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).

## <a name="related-articles"></a>Artículos relacionados

- [¿Qué es el Sistema telefónico?](what-is-phone-system-in-office-365.md)

- [Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

- [Administrar los números de teléfono para su organización](manage-phone-numbers-landing-page.md)
