---
title: Planeación de gobierno de 365 de Microsoft - implementaciones GCC - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Instrucciones para los profesionales de TI a las implementaciones de Office 365 de unidad en las entidades que controlan datos sujetas a regulación gubernamental de EE.
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c54e553edb464dc094c45b4e9dd545827b625d3
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2018
ms.locfileid: "21600520"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planeación de Microsoft 365 gobierno - implementaciones GCC

Esta guía es para los profesionales de TI que están llevando a las implementaciones de Office 365 en federal de Estados Unidos, estado, las entidades de gobierno local, tribal o territoriales u otras entidades que controlan los datos que estén sujetos a reglamentaciones gubernamentales y los requisitos, donde el uso de Microsoft Gobierno 365 - GCC es adecuado para cumplir estos requisitos.

> [!NOTE]
> Si su organización ya tiene cumplen el gobierno de 365 Microsoft - requisitos de idoneidad GCC y para aplicar y se han aceptado en el programa, puede omitir los pasos 1 a 4 y vaya directamente al paso 5 para comenzar la implementación. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determinar si la organización necesita Microsoft 365 gobierno - GCC y que cumpla los requisitos de idoneidad. 

El gobierno de Microsoft 365 - entorno GCC proporciona cumplimiento con US los requisitos de gobierno para servicios de nube, incluyendo FedRAMP moderadas y los requisitos de Justicia penal y sistemas de información de impuesto federal (tipos de datos CJI y FTI).

Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 gobierno - GCC:

-   Contenido de la organización del cliente se aísla lógicamente del contenido del cliente en los servicios de Office 365 comerciales de Microsoft.
-   Contenido de la organización del cliente se almacena dentro de Estados Unidos.
-   Acceso al contenido de la organización del cliente está restringido al personal de Microsoft protegido.
-   Gobierno de Microsoft 365 - GCC cumple con certificaciones y acreditaciones que son necesarios para clientes del Sector público con nosotros.

Puede encontrar más información sobre el gobierno de 365 Microsoft - GCC que ofrece para los clientes de gobierno de Estados Unidos en [que planes de gobierno de Office 365](https://products.office.com/en-us/government/compare-office-365-government-plans), incluidos [los requisitos de idoneidad](https://products.office.com/en-us/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio de gobierno de Estados Unidos de Office 365](https://technet.microsoft.com/en-us/library/mt774581.aspx) describe las ventajas de la plataforma, que se centran en cumplimiento de requisitos dentro de los Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información en la descripción del servicio a un libro de Excel y agregue dos columnas: **pertinente para mi organización Y o N** y **satisfaga las necesidades de mi organización Y o N**. A continuación, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si Microsoft 365 gobierno - GCC es adecuada para su organización.</li><li>Confirme que la organización cumpla con los requisitos de idoneidad.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>Comprender las funciones proporcionadas por Microsoft 365 gobierno - GCC.</li></ul>|

> [!Note]
> Gobierno de Microsoft 365 - GCC sólo está disponible en los Estados Unidos. Los clientes de gobierno de los EE: no pueden elegir entre un número de [planes de gobierno de Office 365](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 2. Comprender las características que actualmente no están disponibles o deshabilitados de forma predeterminada. 

Para dar cabida a los requisitos de nuestros clientes de nube de gobierno, existen algunas diferencias entre Microsoft 365 gobierno - GCC y planes de empresa. Las características que aparecen en la tabla siguiente no están disponibles.

| Característica                     | Motivo            |
|-----------------------------|-------------------|
| Llamada y la grabación de la reunión  | Grabación depende de Microsoft Stream, que estará disponible en los planes de gobierno de Estados Unidos en el futuro. |
| Aplicaciones       | Aplicaciones (por ejemplo, bots, las fichas y los conectores) no estarán disponibles inicialmente, pero trabajamos para ponerlos a disposición tan pronto como todos los componentes de sus cumplen la barra de cumplimiento de normas FedRAMP moderadas. |
| Un canal de correo electrónico             | La arquitectura de la característica actual no es compatible con los planes de gobierno. |
| Presencia unificada            | Estamos trabajo acabado para nuestros clientes empresariales primero para que esta característica importante. Estará disponible para los clientes de gobierno en el futuro. |
| Notificaciones de correo electrónico         | La arquitectura de la característica actual no es compatible con los planes de gobierno de Estados Unidos. Trabajo está en curso para permitir esta característica esté disponible para los clientes de plan de gobierno de Estados Unidos en el futuro. |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si el gobierno de 365 Microsoft - conjunto de características GCC cumple las necesidades de su organización.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>Comprender la configuración de seguridad predeterminada.</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Descripción de Microsoft 365 gobierno - configuración de seguridad predeterminada GCC.

Se recomienda que tenga tiempo para revisar detenidamente la [configuración de administración y seguridad](enable-features-office-365.md) antes de modificarlos y considere la posibilidad de impactos en cumplimiento antes de realizar cualquier cambio en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si va modificar cualquiera del valor predeterminado de Microsoft 365 gobierno - configuración de seguridad GCC, resolver en primer lugar comprender el impacto de los cambios que es posible que realice.</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>Paso 4. Aplicar para Microsoft 365 gobierno - GCC

Tener decidido que este servicio es el adecuado para su organización, iniciar el proceso de la [aplicación para este servicio aquí](https://products.office.com/en-us/government/eligibility-validation).

## <a name="step-5-deploy-teams-for-collaboration"></a>Paso 5. Implementación de los equipos para colaboración

Una vez que se ha estado onboarded a Microsoft 365 gobierno - GCC, puede seguir el enfoque de implementación estándar de usar [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq) y su socio elegido incorporado para el servicio.

Cuando esté listo, implemente los equipos para [Permitir la colaboración dentro de la organización a través de los equipos y los canales](teams-overview.md). Asegúrese de integrarse con su equipo de adopción y administración de cambios o Campeones de los equipos.

## <a name="step-6-deploy-teams-for-meetings-and-voice"></a>Paso 6. Implementación de los equipos para las reuniones y voz

También es un buen momento para usar los equipos con el grupo más amplio de los participantes para empezar a planear para implantar las reuniones y [las características de voz en la nube](cloud-voice-deployment.md).

