---
title: Microsoft 365 Government - Implementaciones GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Guía para profesionales de TI para impulsar las implementaciones de Microsoft 365 en entidades que administran datos sujetos a las normas gubernamentales de EE. UU.
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
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085614"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan para Microsoft 365 Government - Implementaciones GCC

Esta guía es para profesionales de TI que impulsan las implementaciones de Microsoft 365 en estados unidos, estado, locales, entidades gubernamentales u otras entidades que administran datos sujetos a normativas y requisitos gubernamentales, donde el uso de Microsoft 365 Government - GCC es adecuado para cumplir con estos requisitos. Nuevo 26 de marzo de 2020: No se pierda nuestra guía de inicio rápido [descargable para GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams está experimentando un enorme pico en las llamadas en línea y las conferencias de audio y vídeo debido a la pandemia coronavirus (COVID-19).<br/>
> 
>En respuesta al aumento considerable de llamadas y para garantizar la continuidad y la disponibilidad, Microsoft permite que los servidores de audio y vídeo GCC de Microsoft Teams aprovechen la capacidad de procesamiento de nuestros centros de datos comerciales, así como de nuestros centros de datos de la administración.<br/>
> 
>Estos servidores de audio/vídeo se encuentran dentro de los servidores de límites grandes de Microsoft Azure FedRAMP en Estados Unidos y no almacenan ningún contenido de cliente. Sin embargo, estos servidores están procesando audio y vídeo para llamadas y conferencias y operan bajo nuestro personal comercial durante este período provisional.<br/>
> 
>El personal cualificado y con pantalla supervisa estos servidores para obtener un posible acceso a los datos de los clientes revisando cualquier inicio de sesión interactivo en estos servidores. El personal cualificado cumple los requisitos de GCC para acceder al contenido del cliente. Para obtener más información sobre los requisitos de filtrado, consulte la [descripción del servicio GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Gracias por tu apoyo mientras tomamos medidas para asegurarnos de que nuestros servicios siguen estando disponibles y fiables en estos periodos extraordinarias.<br/>


> [!NOTE]
> Si tu organización ya cumple los requisitos de elegibilidad de Microsoft 365 Government- GCC, y has solicitado y aceptado en el programa, puedes omitir los pasos 1 y 2 e ir directamente al paso 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 Government - GCC y cumple los requisitos de elegibilidad. 

El entorno microsoft 365 Administración Pública - GCC proporciona el cumplimiento de los requisitos del gobierno de EE. UU. para los servicios en la nube, incluidos fedRAMP moderado y los requisitos para sistemas fiscales federales y fiscales federales (CJI y tipos de datos FTI).

Además de disfrutar de las características y capacidades de Microsoft 365, las organizaciones se benefician de las siguientes características exclusivas de Microsoft 365 Government - GCC:

-   El contenido de cliente de la organización se separa lógicamente del contenido del cliente en los servicios comerciales de Microsoft 365.
-   El contenido de cliente de su organización se almacena en Estados Unidos.
-   El acceso al contenido de cliente de su organización está restringido al personal de Microsoft con pantalla.
-   Microsoft 365 Government - GCC cumple con las certificaciones y los procesos necesarios para los clientes del sector público de EE. UU.

Puedes encontrar más información sobre la oferta de Microsoft 365 Government - GCC para clientes de US Government en los planes de [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluidos los requisitos [de elegibilidad.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La descripción del servicio [Microsoft 365 US Government](https://technet.microsoft.com/library/mt774581.aspx) describe las ventajas de la plataforma, centrada en cumplir los requisitos de cumplimiento en Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: Relevante para mi organización **Y/N** y cumple las necesidades de mi organización **Y/N.** Después, puede revisar esta lista con sus compañeros para confirmar que este servicio cumple las necesidades de su organización.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 Government - GCC es adecuado para su organización.</li><li>Confirma que tu organización cumple los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC solo está disponible en Estados Unidos. Los clientes de administración público que no son de EE. UU. pueden elegir entre varios [planes de Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Paso 2. Solicitar para Microsoft 365 Government - GCC

Después de decidir que este servicio es adecuado para su organización, inicie el proceso de [solicitar este servicio aquí.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Información sobre la configuración de seguridad predeterminada de Microsoft 365 Government: GCC.

Le recomendamos que se tome [](enable-features-office-365.md) un tiempo para revisar detenidamente la configuración de seguridad y administrador antes de modificarla, y que considere las consecuencias en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si va a modificar alguna de las opciones predeterminadas de configuración de seguridad Microsoft 365 Government - GCC, resolviendo primero el impacto de los cambios que puede realizar.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 4. Comprender qué funciones no están disponibles o deshabilitadas de forma predeterminada.

Para adaptarse a los requisitos de nuestros clientes de la nube de la administración pública, hay algunas diferencias entre los planes Microsoft 365 Government - GCC y Enterprise. Consulte la tabla siguiente para ver qué características están disponibles.

[Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Cuando otras cargas de trabajo estén completamente disponibles en la nube GCC, estarán disponibles en Teams cuando se complete todo el trabajo adicional de integración.


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si el conjunto de características de Teams se ajusta a las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Plan de gobernanza

Determine sus requisitos para el gobierno y cómo puede cumplirlos. Vaya a [Plan para el gobierno en Teams](plan-teams-governance.md) para obtener más información.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Determine y documente sus requisitos de gobierno siguiendo las directrices de [Plan de gobernanza en Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para la colaboración

Una vez que se haya incorporado a Microsoft 365 Government: GCC, siga la ruta de implementación recomendada que se describe en Cómo implementar [Microsoft Teams.](How-to-roll-out-teams.md) Asegúrese de colaborar con su equipo de adopción y administración de cambios y con los campeones de Teams.

También puede trabajar con [FastTrack o](https://www.microsoft.com/fasttrack) con su partner elegido para incorporar el servicio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Paso 7. Implementar Teams para reuniones y voz

Este también es un buen momento para usar Teams con el grupo de participantes más amplio para empezar a planear el desarrollo de reuniones y características de [voz en la nube.](cloud-voice-deployment.md)

