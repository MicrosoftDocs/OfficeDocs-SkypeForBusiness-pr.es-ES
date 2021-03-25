---
title: 'Microsoft 365 Government: implementaciones de GCC High'
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que administran datos sujetos a la normativa gubernamental de EE. UU.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117848"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Planear las implementaciones de Office 365 Government - GCC High

Esta guía es para los profesionales de TI que están impulsando implementaciones de Office 365 en entidades gubernamentales federales de EE. UU. u otras entidades que administran datos sujetos a normativas y requisitos gubernamentales, donde el uso de Office 365 Government - GCC High es adecuado para cumplir estos requisitos.

> [!NOTE]
> Si su organización ya ha cumplido los requisitos de elegibilidad de Office 365 Government : GCC High eligibility requirements and applied for and been accepted into the program, puede omitir los pasos 1 y 2 y ir directamente al paso 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Office 365 Government - GCC High y cumple los requisitos de elegibilidad. 

El entorno Office 365 Government - GCC High proporciona el cumplimiento de los requisitos del gobierno de EE. UU. para los servicios en la nube. Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Office 365 Government: GCC High:

- El contenido de clientes de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.
- El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
- El acceso al contenido de clientes de su organización está restringido al personal de Microsoft con pantalla.
- Office 365 Government: GCC High cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de EE. UU.

Puede encontrar más información sobre la oferta Office 365 Government – GCC High para los clientes del gobierno de EE. UU. en los planes de [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluidos los [requisitos de elegibilidad.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La descripción del servicio de [Office 365 Us Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describe las ventajas de la plataforma, que se centra en cumplir los requisitos de cumplimiento dentro de los Estados Unidos.


> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: Relevante para mi organización **Y/N** y Satisface las necesidades de mi organización **Y/N**. Después, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Office 365 Government - GCC High es adecuado para su organización.</li><li>Confirme que su organización cumple los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Office 365 Government: GCC High solo está disponible en Estados Unidos. Los clientes que no son del gobierno de EE. UU. pueden elegir entre varios planes [de Office 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>Paso 2. Solicitar Office 365 Government - GCC High

Después de haber decidido que este servicio es adecuado para su organización, inicie el proceso de solicitud [de este servicio.](https://products.office.com/government/eligibility-validation)


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>Paso 3. Comprender la configuración de seguridad predeterminada de Office 365 Government: GCC High default.

Le recomendamos que se tome [](enable-features-office-365.md) un tiempo para revisar detenidamente la configuración de seguridad y administración antes de modificarlas, y tenga en cuenta los impactos en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si tendrá que modificar alguna de las opciones predeterminadas de Office 365 Government : GCC High security settings( Administración pública predeterminada: GCC) y resuelva primero el impacto de los cambios que pueda realizar.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>Paso 4. Comprender qué capacidades de Teams están disponibles actualmente en Office 365 Government - GCC High

Para adaptarse a los requisitos de nuestros clientes en la nube del gobierno, hay algunas diferencias entre Teams en Office 365 Government : GCC High y Teams en los planes enterprise. Consulte la tabla siguiente para ver qué características están disponibles.

[Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Paso 5. Plan de gobernanza

Determine sus requisitos de gobernanza y cómo puede cumplirlos. Vaya a [Planear el gobierno en Teams](plan-teams-governance.md) para obtener más información.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Punto de decisión |<ul><li>Determine y documente los requisitos de gobernanza siguiendo las directrices de [Plan de gobernanza en Teams.](plan-teams-governance.md) </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para colaboración

Después de incorporarse a Office 365 Government: GCC High, siga la ruta de implementación recomendada que se describe en Cómo implementar [Microsoft Teams.](./deploy-overview.md) Asegúrese de participar con su equipo de adopción y administración de cambios y con los campeones de Teams.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o su partner elegido para incorporar el servicio.

> [!NOTE]
> El cliente de Mac Teams para entornos GCCH aún no es compatible.