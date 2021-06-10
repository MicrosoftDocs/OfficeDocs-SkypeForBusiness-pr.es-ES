---
title: 'Microsoft 365 Gobierno: GCC implementaciones'
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar Microsoft 365 en entidades que administran datos sujetos a la normativa gubernamental de EE. UU.
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
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117838"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan para Microsoft 365 administración local: GCC implementaciones

Esta guía es para los profesionales de TI que están impulsando implementaciones de Microsoft 365 en entidades gubernamentales federales, estatales, locales, tribales o territoriales u otras entidades que administran datos sujetos a normativas y requisitos gubernamentales, donde el uso de Microsoft 365 Government - GCC es adecuado para cumplir estos requisitos. Nuevo 26 de marzo de 2020: No se pierda nuestra guía de inicio rápido descargable para [GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> Microsoft Teams está experimentando un pico tremendo en las llamadas en línea y las conferencias de audio y vídeo debido a la pandemia de coronavirus (COVID-19).<br/>
> 
>En respuesta al aumento sin precedentes de llamadas y para garantizar la continuidad y la disponibilidad, Microsoft permite Microsoft Teams GCC los servidores de audio y vídeo aprovechar la capacidad de procesamiento en nuestros centros de datos comerciales, así como en nuestros centros de datos gubernamentales.<br/>
> 
>Estos servidores de audio y vídeo residen dentro de los Microsoft Azure límites de alta acreditación de FedRAMP en los Estados Unidos y no almacenan ningún contenido de cliente. Sin embargo, estos servidores están procesando audio y vídeo para llamadas y conferencias y operan bajo nuestro personal comercial durante este período provisional.<br/>
> 
>El personal cualificado y con pantalla supervisa estos servidores para obtener acceso potencial a los datos de los clientes revisando los inicios de sesión interactivos en estos servidores. El personal cualificado cumple GCC requisitos de acceso al contenido del cliente. Para obtener más información sobre los requisitos de detección, [vea GCC descripción del servicio](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Gracias por su soporte mientras tomamos medidas para garantizar que nuestros servicios sigan estando disponibles y confiables en estos momentos extraordinarios.<br/>


> [!NOTE]
> Si su organización ya ha cumplido los requisitos de elegibilidad de Microsoft 365 Government - GCC y solicitó y se aceptó en el programa, puede omitir los pasos 1 y 2 e ir directamente al paso 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 gobierno: GCC y cumple los requisitos de elegibilidad. 

El Microsoft 365 de GCC proporciona el cumplimiento de los requisitos del gobierno de EE. UU. para los servicios en la nube, incluidos FedRAMP Moderado, y los requisitos para la justicia penal y los sistemas de información fiscal federal (tipos de datos CJI y FTI).

Además de disfrutar de las características y las capacidades de Microsoft 365, las organizaciones se benefician de las siguientes características que son únicas para Microsoft 365 gobierno: GCC:

-   El contenido de clientes de su organización se separa lógicamente del contenido del cliente en los servicios Microsoft 365 comerciales de Microsoft.
-   El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
-   El acceso al contenido de clientes de su organización está restringido al personal de Microsoft con pantalla.
-   Microsoft 365 Gobierno: GCC cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de EE. UU.

Puede encontrar más información sobre la oferta Microsoft 365 administración pública GCC para [](https://products.office.com/government/compare-office-365-government-plans)los clientes del gobierno de ee. UU. en Microsoft 365 planes gubernamentales, incluidos los [requisitos de elegibilidad.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

En [Microsoft 365 descripción del](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) servicio del gobierno de EE. UU. se describen las ventajas de la plataforma, que se centra en cumplir los requisitos de cumplimiento dentro de los Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio Excel un libro de Excel y agregar dos columnas: Relevante para mi organización **Y/N** y Satisface las necesidades de mi organización **Y/N**. Después, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 gobierno: GCC es adecuado para su organización.</li><li>Confirme que su organización cumple los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Gobierno: GCC solo está disponible en Los Estados Unidos. Los clientes que no son del gobierno de EE. UU. pueden elegir entre una serie [de Microsoft 365 planes gubernamentales.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Paso 2. Solicitar el Microsoft 365 de administración local : GCC

Después de haber decidido que este servicio es adecuado para su organización, inicie el proceso de solicitar [este servicio aquí.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Comprender Microsoft 365 administración pública: GCC configuración de seguridad predeterminada.

Le recomendamos que se tome [](enable-features-office-365.md) un tiempo para revisar detenidamente la configuración de seguridad y administración antes de modificarlas, y tenga en cuenta los impactos en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si va a modificar cualquiera de las opciones predeterminadas de Microsoft 365: GCC de seguridad, resolviendo primero el impacto de los cambios que pueda realizar.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 4. Comprender qué capacidades no están disponibles o deshabilitadas de forma predeterminada.

Para adaptarse a los requisitos de nuestros clientes en la nube del gobierno, hay algunas diferencias entre Microsoft 365 administración pública: GCC y Enterprise planes. Consulte la tabla siguiente para ver qué características están disponibles.

[Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Una vez que otras cargas de trabajo estén totalmente disponibles en la GCC, estarán disponibles en Teams cuando se complete todo el trabajo de integración adicional.


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si el conjunto Teams características cumple las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Plan de gobernanza

Determine sus requisitos de gobernanza y cómo puede cumplirlos. Vaya a [Planear el gobierno en Teams](plan-teams-governance.md) para obtener más información.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Determine y documente los requisitos de gobernanza siguiendo las directrices de Plan de gobernanza [en Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams colaboración

Después de que se haya incorporado a Microsoft 365 Government: GCC, siga la ruta de implementación recomendada que se describe en Cómo implementar [Microsoft Teams](./deploy-overview.md). Asegúrese de participar con su equipo de adopción y administración de cambios y con Teams usuarios.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o su partner elegido para incorporar el servicio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Paso 7. Implementar Teams para reuniones y voz

Este también es un buen momento para usar Teams con su grupo de partes interesadas más amplio para empezar a planear la puesta en marcha de reuniones y características de [voz en la nube.](./cloud-voice-landing-page.md)