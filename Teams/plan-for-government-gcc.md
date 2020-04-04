---
title: Implementaciones de Microsoft 365 administración pública-GCC
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que controlan datos sujetos a la normativa del gobierno de Estados Unidos
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab398d4d76eb0c1ae6bac37b7c9c198ebc82d86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137816"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan para implementaciones de Microsoft 365 administración pública-GCC

Esta guía está orientada a los profesionales de ti que están implantando implementaciones de Office 365 en entidades gubernamentales de Estados Unidos, Estados, locales, tribal o territoriales u otras entidades que administran datos que están sujetos a los requisitos y las reglamentaciones gubernamentales, donde el uso de Microsoft 365 gobierno-GCC es adecuado para cumplir con estos requisitos. Nuevo 26 de marzo de 2020: no pierdamos nuestra [Guía de inicio rápido](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)descargable para GCC.

> [!IMPORTANT]
> Microsoft Teams está experimentando un enorme aumento en las llamadas en línea y las conferencias de audio y videollamadas debido a la coronavirus (COVID-19) Pandemic.<br/>
> 
>En respuesta al aumento sin precedentes de las llamadas, y para garantizar la continuidad y la disponibilidad, Microsoft permite que Microsoft Teams GCC/audio/vídeo saque el máximo partido de la capacidad de procesamiento de nuestros centros de proceso de ventas comerciales, así como de nuestros centros de administración gubernamentales.<br/>
> 
>Estos servidores de audio y vídeo se encuentran dentro de los servidores de límite de acreditación alta de Microsoft Azure FedRAMP en los Estados Unidos y no almacenan ningún contenido de cliente. Sin embargo, estos servidores están procesando el audio y el vídeo de las llamadas y las conferencias, y están operando bajo nuestro personal comercial durante este período provisional.<br/>
> 
>El personal con pantalla calificada está supervisando estos servidores para obtener acceso potencial a los datos de los clientes revisando los inicios de sesión interactivos en estos servidores. El personal cualificado cumple con los requisitos de GCC para acceder al contenido de los clientes. Para obtener más información sobre los requisitos de filtrado, consulte la [Descripción del servicio GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Gracias por tu ayuda a la hora de tomar medidas para asegurarnos de que nuestros servicios estén disponibles y sean confiables en estas extraordinarias horas.<br/>


> [!NOTE]
> Si su organización ya cumple con los requisitos de idoneidad de Microsoft 365 Government-GCC y ha sido aplicado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 pública-GCC y cumple con los requisitos de elegibilidad. 

El entorno Microsoft 365 Government-GCC ofrece cumplimiento de los requisitos del gobierno de los Estados Unidos para servicios en la nube, incluidos los FedRAMP moderados, y requisitos para los sistemas de información de la justicia y los impuestos federales (CJI y FTI tipos de datos).

Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 administración pública-GCC:

-   El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.
-   El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
-   El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.
-   Microsoft 365 Government-GCC cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.

Puede encontrar más información sobre la oferta de Microsoft 365 administración pública-GCC para clientes del gobierno de los Estados Unidos en [Office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio del gobierno de Office 365 Estados](https://technet.microsoft.com/library/mt774581.aspx) Unidos describe los beneficios de la plataforma, que se centran en los requisitos de cumplimiento de las reuniones de los Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**. Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 Government-GCC es adecuado para su organización.</li><li>Confirme que su organización cumple con los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC solo está disponible en los Estados Unidos. Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Paso 2. Solicitar Microsoft 365 administración pública-GCC

Tras haber decidido que este servicio es adecuado para su organización, aquí tiene que iniciar el proceso de [solicitar este servicio](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Comprender la configuración de seguridad predeterminada de Microsoft 365 Government-GCC.

Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si modificará cualquiera de los valores de seguridad predeterminados de Microsoft 365 administración pública-GCC y se resolverá para comprender primero el impacto de los cambios que puede realizar.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 4. Comprender qué características no están disponibles o deshabilitadas de forma predeterminada.

Para cumplir con los requisitos de nuestros clientes gubernamentales en la nube, existen algunas diferencias entre los planes de Microsoft 365 gubernamentales-GCC y Enterprise. Consulte la tabla siguiente para ver qué características están disponibles.

[Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Una vez que otras cargas de trabajo estén completamente disponibles en la nube de GCC, estarán disponibles en Teams cuando se complete todo el trabajo de integración adicional.


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si el conjunto de características de Teams cumple con las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Planear la gobernanza

Determina los requisitos de gobierno y cómo puedes reunirse. Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para la colaboración

Después de que se haya incorporado a Microsoft 365 administración pública – GCC, siga la ruta de implementación recomendada, [que se describe en cómo implementar Microsoft Teams](How-to-roll-out-teams.md). Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Paso 7. Implementar equipos para reuniones y voz

Este es también un buen momento para usar Teams con su grupo más amplio de participantes para empezar a planear la implementación de reuniones y [características de voz en la nube](cloud-voice-deployment.md).

