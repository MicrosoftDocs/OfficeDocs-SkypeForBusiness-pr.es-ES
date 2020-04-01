---
title: Plan para Microsoft 365 Administración Pública - Implementaciones de alta disponibilidad de GCC - Microsoft Teams
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que controlan datos sujetos a la normativa del gobierno de Estados Unidos.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7be9916a1c51b7e98467d1e8c44a18dd6d227d35
ms.sourcegitcommit: 4e1647d19501b37860d9fc79370fa4347f76f85f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43079422"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a>Plan para implementaciones altas de Microsoft 365 administración pública-GCC

Esta guía está orientada a los profesionales de ti que están implantando implementaciones de Office 365 en entidades de administración pública de Estados Unidos u otras entidades que tratan datos que están sujetos a los requisitos y las reglamentaciones gubernamentales, donde el uso de Microsoft 365 Government – GCC High es adecuado para cumplir con estos requisitos.

> [!NOTE]
> Si su organización ya cumple con los requisitos de elegibilidad elevados de Microsoft 365, y ha sido solicitado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 pública-GCC High y cumple con los requisitos de elegibilidad. 

El entorno alto de Microsoft 365 Government-GCC proporciona el cumplimiento de los requisitos gubernamentales de los Estados Unidos para los servicios en la nube. Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 administración pública – GCC High:

- El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.
- El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
- El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.
- Microsoft 365 Government – GCC High cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.

Puede encontrar más información sobre la administración pública 365 de GCC para clientes del gobierno de los Estados Unidos en [Office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio del gobierno de Office 365 Estados](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Unidos describe los beneficios de la plataforma, que están centrados en cumplir los requisitos de cumplimiento de las normas de los Estados Unidos.


> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**. Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 Government-GCC High es adecuado para su organización.</li><li>Confirme que su organización cumple con los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC High solo está disponible en los Estados Unidos. Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a>Paso 2. Solicitar Microsoft 365 administración pública-GCC High

Tras haber decidido que este servicio es adecuado para su organización, inicie el proceso de [solicitud de este servicio](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a>Paso 3. Comprender la configuración de seguridad predeterminada alta de Microsoft 365 pública-GCC.

Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si necesita modificar cualquiera de las opciones predeterminadas de alta seguridad de Microsoft 365 gubernamentales-GCC, resolviendo para comprender primero el impacto de los cambios que puede realizar.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a>Paso 4. Comprender qué capacidades de Teams están disponibles actualmente en Microsoft 365 pública-GCC High

Para cumplir con los requisitos de nuestros clientes gubernamentales de la nube, existen algunas diferencias entre los equipos de Microsoft 365 gubernamentales-GCC High y Teams en los planes empresariales. Consulte la tabla siguiente para ver qué características están disponibles.

[Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Paso 5. Planear la gobernanza

Determina los requisitos de gobierno y cómo puedes reunirse. Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Punto de decisión |<ul><li>Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para la colaboración

Después de que se haya incorporado a Microsoft 365 administración pública – GCC High, siga la ruta de implementación recomendada que se describe en [cómo implementar Microsoft Teams](How-to-roll-out-teams.md). Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.

