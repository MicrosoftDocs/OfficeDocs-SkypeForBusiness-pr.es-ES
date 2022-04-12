---
title: Información general sobre la validación de aplicaciones y las pruebas de aplicaciones de Microsoft
ms.reviewer: ''
description: Comprenda las comprobaciones de calidad y la validación de aplicaciones realizadas para las aplicaciones de Teams.
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
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756996"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Validación realizada por Microsoft para todas las aplicaciones de Teams

Microsoft requiere que todas las aplicaciones pasen una validación obligatoria antes de aparecer en la tienda para usos finales. Se aplica a todas las aplicaciones (excepto las aplicaciones personalizadas) publicadas en la tienda de aplicaciones de Teams. Además, Microsoft anima encarecidamente a los desarrolladores de aplicaciones a participar en una certificación opcional de aplicaciones que indique controles mejorados de cumplimiento, seguridad y privacidad.

Todas las aplicaciones deben cumplir obligatoriamente las directivas de certificación de aplicaciones de Microsoft. El equipo de la tienda de Teams realiza más de 400 pruebas para asegurarse de que las aplicaciones se pueden usar y cumplir los altos estándares de privacidad y seguridad.

Para conocer las directrices de validación detalladas a las que se adhieren los desarrolladores de aplicaciones, consulte [Directrices de validación para desarrolladores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). La guía se basa en las [Directivas de certificación para las aplicaciones de Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La validación y las comprobaciones de Microsoft no están disponibles para una aplicación personalizada, ya que se desarrolla dentro de la organización y solo está disponible para los miembros de la organización.

## <a name="app-validation-and-testing"></a>Validación y pruebas de aplicaciones

Ejecutamos más de 400 casos de prueba para cada aplicación antes de que esté disponible en la tienda Teams. Las pruebas garantizan la funcionalidad, la experiencia del usuario y la seguridad adecuadas, y aseguran que todas las aplicaciones cumplen con las directivas de OCM que se han hecho públicas. Estas son algunas de las pruebas realizadas por el equipo de validación de aplicaciones de Microsoft para cada aplicación antes de que se publique:

* Asegúrese de que los permisos de Graph solicitados por la aplicación son realmente los que necesita la funcionalidad de la aplicación y no los permisos adicionales. Los permisos de Graph para las aplicaciones existentes se comprueban periódicamente para asegurarse de que una aplicación no requiere permisos adicionales.
* Las aplicaciones que requieren que los usuarios inicien sesión tienen una opción de cierre de sesión.
* Todos los editores de aplicaciones se someten a un detallado proceso de verificación en el Centro de partners de Microsoft. La comprobación incluye la verificación por correo electrónico, la comprobación empresarial y mucho más. Para obtener más información sobre la publicación de aplicaciones, consulte [Cómo crean los desarrolladores una cuenta de Centro de partners](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guía de envío para desarrolladores](/office/dev/store/add-in-submission-guide) y [Cómo publican las aplicaciones](https://aka.ms/PublishToTeamsStore).
* Solo las aplicaciones de editores comprobados pueden solicitar permisos de Graph a los usuarios finales.
* Ninguna aplicación puede descargar un archivo ejecutable.
* Las aplicaciones se prueban para que no contengan anuncios o promociones para otras aplicaciones
* Se ha probado que las aplicaciones funcionan correctamente sin lenguaje ofensivo, bots de ciberataques, correo no deseado o contenido de estafa.
* Todos los vínculos de una aplicación son funcionales y solo están relacionados con la oferta de la aplicación.
* Probamos y evaluamos todas las aplicaciones de Teams publicadas periódicamente como parte de las comprobaciones de estado de la tienda de aplicaciones.
* El ISV publica la directiva de privacidad y los Términos de uso que cubren las aplicaciones de Teams
* Los detalles de contacto del ISV están disponibles en la descripción de la tienda y en sus respectivas [Páginas de atestación de Publisher](/microsoft-365-app-certification/teams/teams-apps).

Además, Microsoft anima a los desarrolladores de aplicaciones a participar en su programa de cumplimiento normativo, que es un enfoque riguroso de dos niveles para garantizar la calidad, la seguridad y el cumplimiento de las aplicaciones. La tienda de Teams tiene cientos de aplicaciones que van más allá de cumplir las directrices de validación ya detalladas y cumplir con estos programas.

## <a name="publisher-verification"></a>Verificación del editor

Antes de que un desarrollador de aplicaciones pueda enviar su aplicación a Microsoft, se le pedirá que realice una comprobación. Un publicador comprueba su identidad con su cuenta de Microsoft Partner Network (MPN) y asocia esta cuenta de MPN con el registro de la aplicación. La verificación del publicador ayuda a los administradores y usuarios finales a comprender la autenticidad de los desarrolladores de aplicaciones que se integran en la plataforma de identidad de Microsoft. La comprobación del publicador proporciona las siguientes ventajas:

* Mayor transparencia y reducción de riesgos para los clientes: esta capacidad ayuda a los clientes a comprender qué aplicaciones utilizadas en sus organizaciones son publicadas por desarrolladores en los que confían.
* Mejora de la marca: aparece un distintivo `verified` en la solicitud de consentimiento de Azure Active Directory, en la página de las aplicaciones empresariales y en otras interfaces de usuario utilizadas por los usuarios finales y los administradores.
* Adopción empresarial más fluida: los administradores pueden configurar directivas de consentimiento del usuario, con el estado de comprobación del publicador como criterio de directiva principal.

## <a name="see-also"></a>Vea también

* [Información general para los administradores del programa de cumplimiento de aplicaciones de Microsoft 365](overview-of-app-certification.md)
