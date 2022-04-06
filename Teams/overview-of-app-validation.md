---
title: Información general sobre validación de aplicaciones y pruebas de aplicaciones por parte de Microsoft
ms.reviewer: ''
description: Comprender las comprobaciones de calidad, la validación de aplicaciones y los programas de certificación de Teams aplicaciones.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 384a57abb724ee29feb5f93fa171d0bc5ec96f3d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686497"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Comprobaciones y validación realizadas por Microsoft en aplicaciones de Teams

Microsoft requiere que todas las aplicaciones pasen una validación obligatoria antes de aparecer en store para usos finales. Se aplica a todas las aplicaciones (excepto las aplicaciones personalizadas) publicadas en Teams App Store. Además, Microsoft recomienda encarecidamente a los desarrolladores de aplicaciones que participen en una certificación opcional de aplicaciones que indique controles de cumplimiento, seguridad y privacidad mejorados.

Todas las aplicaciones son obligatoriamente necesarias para cumplir las directivas de certificación de aplicaciones de Microsoft. El equipo de la tienda Teams realiza más de 400 pruebas para garantizar que las aplicaciones sean utilizables y cumplan con altos estándares de privacidad y seguridad.

Para conocer las instrucciones de validación detalladas que cumplen los desarrolladores de aplicaciones, consulta [Directrices de validación para desarrolladores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Las instrucciones se basan en las [directivas de certificación de las aplicaciones de Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La validación y las comprobaciones de Microsoft no están disponibles para una aplicación personalizada, ya que se desarrolla dentro de su organización y solo está disponible para los miembros de la organización.

## <a name="app-validation-and-testing"></a>Validación y pruebas de aplicaciones

Ejecutamos más de 400 casos de prueba para cada aplicación antes de que esté disponible en Teams Store. Las pruebas garantizan la funcionalidad, la experiencia del usuario y la seguridad adecuadas, y garantizan que todas las aplicaciones cumplan con las directivas de CMO enumeradas públicamente. A continuación se indican algunas de las pruebas realizadas por el equipo de validación de aplicaciones de Microsoft para cada aplicación antes de su publicación:

* Asegúrese de que Graph permisos solicitados por la aplicación sean realmente los que necesita la funcionalidad de la aplicación y no ningún permiso adicional. Graph permisos de las aplicaciones existentes se comprueban periódicamente para garantizar que una aplicación no requiera permisos adicionales.
* Las aplicaciones que requieren que los usuarios inicien sesión o inicien sesión deben tener una opción de cierre de sesión o cierre de sesión.
* Todos los editores de aplicaciones se someten a un proceso detallado de verificación en el Centro de partners de Microsoft. La verificación incluye la verificación por correo electrónico, la verificación empresarial y mucho más. Para obtener más información sobre la publicación de aplicaciones, consulta [Cómo los desarrolladores crean una cuenta del Centro](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account) de partners, [Guía de envío para desarrolladores](/office/dev/store/add-in-submission-guide) y [Cómo los desarrolladores publican aplicaciones](https://aka.ms/PublishToTeamsStore).
* Solo las aplicaciones de editores comprobados pueden buscar permisos de Graph de los usuarios finales.
* Ninguna aplicación puede descargar un archivo ejecutable.
* Las aplicaciones se prueban para que no contengan anuncios ni promociones para otras aplicaciones
* Las aplicaciones se prueban para que funcionen correctamente sin lenguaje ofensivo, bots de ataque cibernético, correo no deseado o contenido de estafa.
* Todos los vínculos de una aplicación son funcionales y están relacionados solo con la oferta de la aplicación.
* Probamos y evaluamos todas las aplicaciones publicadas de Teams periódicamente como parte de las comprobaciones de estado de la tienda de aplicaciones.
* La directiva de privacidad y los Términos de uso que cubren Teams aplicaciones son publicados por el ISV
* Los datos de contacto del ISV están disponibles en la descripción de Store y en sus respectivas [páginas de atestación de Publisher](/microsoft-365-app-certification/teams/teams-apps).

## <a name="publisher-verification"></a>Publisher verificación

Publisher verificación ayuda a los administradores y usuarios finales a comprender la autenticidad de los desarrolladores de aplicaciones que se integran con el Plataforma de identidad de Microsoft. Tener un editor comprobado significa que el editor ha comprobado su identidad mediante su cuenta de Microsoft Partner Network (MPN) y que ha asociado esta cuenta MPN con el registro de aplicaciones.

Publisher verificación ofrece las siguientes ventajas:

* Mayor transparencia y reducción de riesgos para los clientes: esta función ayuda a los clientes a comprender qué aplicaciones se usan en sus organizaciones las publican los desarrolladores en los que confían.
* Mejora de la personalización de marca: aparece un `verified` distintivo en la Azure Active Directory solicitud de consentimiento, Enterprise página Aplicaciones y otras interfaces de usuario usadas por usuarios finales y administradores.
* Adopción empresarial más fluida: los administradores pueden configurar directivas de consentimiento de usuario, con el estado de verificación del editor como criterio de directiva principal.

Además, Microsoft recomienda a los desarrolladores de aplicaciones que participen en su programa de cumplimiento, que es un enfoque riguroso de dos niveles para garantizar la calidad de las aplicaciones, la seguridad y el cumplimiento normativo. Teams store tiene cientos de aplicaciones que van más allá de cumplir con las ya detalladas directrices de validación y cumplir con estos programas.

## <a name="microsoft-365-app-compliance-program"></a>programa de cumplimiento de Microsoft 365 aplicación

El programa de cumplimiento de Microsoft demuestra que una aplicación se examina con controles derivados de los marcos estándar del sector líderes y que se aplican prácticas de seguridad y cumplimiento sólidos para proteger los datos de los clientes. El programa tiene dos fases:

* Publisher atestación.
* Microsoft 365 certificación.

### <a name="publisher-attestation"></a>atestación de Publisher

El desarrollador de la aplicación debe completar una autoevaluación que incluya preguntas que los clientes o administradores de TI suelen hacer cuando evalúan la seguridad y el cumplimiento de una aplicación. A continuación, Microsoft publica esta información para una evaluación más sencilla y oportuna. La información incluye detalles sobre el tratamiento de datos, la seguridad, el cumplimiento y la privacidad cuando se activa una aplicación en una organización.

Para obtener más información, consulta la [Guía de atestación publicada](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

### <a name="microsoft-365-certification"></a>certificación de Microsoft 365

La certificación de aplicaciones se obtiene a través de la revisión y aprobación de un analista calificado de una evaluación integral centrada en los marcos, procesos y procedimientos de seguridad y cumplimiento de una aplicación. La aplicación se examina con una serie de controles de seguridad derivados de los marcos estándar del sector líderes. El certificado demuestra que se aplican prácticas de seguridad y cumplimiento sólidos para proteger los datos de los clientes cuando la aplicación se activa en una organización.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
