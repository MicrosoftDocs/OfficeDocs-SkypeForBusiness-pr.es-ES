---
title: Implementaciones de Microsoft 365 administración pública de DoD
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que controlan datos sujetos a la normativa DoD de Estados Unidos.
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
ms.openlocfilehash: 33c3afcde009a6a8cedb1226dbc6383e29e76730
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137800"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="bd085-103">Plan para implementaciones de Microsoft 365 administración pública</span><span class="sxs-lookup"><span data-stu-id="bd085-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="bd085-104">Esta guía es para los profesionales de ti que están implantando implementaciones de Office 365 en entidades de gobierno federal de Estados Unidos u otras entidades que tratan datos sujetos a reglamentaciones gubernamentales y requisitos, donde el uso de la administración pública de Microsoft 365 es adecuado para cumplir con estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="bd085-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="bd085-105">Si su organización ya cumple con los requisitos de elegibilidad de los DoD de Microsoft 365, y ha sido solicitado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3.</span><span class="sxs-lookup"><span data-stu-id="bd085-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="bd085-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="bd085-106">Step 1.</span></span> <span data-ttu-id="bd085-107">Determine si su organización necesita Microsoft 365 gobierno-DoD y cumple con los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="bd085-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="bd085-108">El entorno Microsoft 365 Government-DoD ofrece cumplimiento de los requisitos del gobierno de los Estados Unidos para servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="bd085-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="bd085-109">Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 administración pública: DoD:</span><span class="sxs-lookup"><span data-stu-id="bd085-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="bd085-110">El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd085-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="bd085-111">El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd085-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="bd085-112">El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="bd085-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="bd085-113">Microsoft 365 Government – DoD cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd085-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="bd085-114">Puede encontrar más información sobre la oferta de administración pública de Microsoft 365, para clientes del gobierno de los Estados Unidos en [Office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="bd085-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="bd085-115">La [Descripción del servicio del gobierno de Office 365 Estados](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Unidos describe los beneficios de la plataforma, que están centrados en cumplir los requisitos de cumplimiento de las normas de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd085-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="bd085-116">Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**.</span><span class="sxs-lookup"><span data-stu-id="bd085-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="bd085-117">Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="bd085-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="bd085-119">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="bd085-119">Decision points</span></span>|<ul><li><span data-ttu-id="bd085-120">Decida si Microsoft 365 Government-DoD es adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="bd085-120">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="bd085-121">Confirme que su organización cumple con los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="bd085-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="bd085-122">Microsoft 365 Government-DoD solo está disponible en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd085-122">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="bd085-123">Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="bd085-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="bd085-124">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="bd085-124">Step 2.</span></span> <span data-ttu-id="bd085-125">Solicitar Microsoft 365 administración pública-DoD</span><span class="sxs-lookup"><span data-stu-id="bd085-125">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="bd085-126">Tras haber decidido que este servicio es adecuado para su organización, inicie el proceso de [solicitud de este servicio](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="bd085-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="bd085-127">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="bd085-127">Step 3.</span></span> <span data-ttu-id="bd085-128">Comprender la configuración de seguridad predeterminada de Microsoft 365 administración pública.</span><span class="sxs-lookup"><span data-stu-id="bd085-128">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="bd085-129">Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bd085-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="bd085-131">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="bd085-131">Decision point</span></span>|<ul><li><span data-ttu-id="bd085-132">Decida si necesita modificar cualquiera de los valores predeterminados de la configuración de seguridad de Microsoft 365 gubernamentales-DoD, resolviendo primero el impacto de los cambios que puede realizar.</span><span class="sxs-lookup"><span data-stu-id="bd085-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="bd085-133">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="bd085-133">Step 4.</span></span> <span data-ttu-id="bd085-134">Comprender qué capacidades de Teams están disponibles actualmente en Microsoft 365 gobierno-DoD</span><span class="sxs-lookup"><span data-stu-id="bd085-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="bd085-135">Para cumplir con los requisitos de nuestros clientes gubernamentales de la nube, existen algunas diferencias entre los equipos de Microsoft 365 gubernamentales-DoD y los equipos de los planes empresariales.</span><span class="sxs-lookup"><span data-stu-id="bd085-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="bd085-136">Consulte la tabla siguiente para ver qué características están disponibles.</span><span class="sxs-lookup"><span data-stu-id="bd085-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="bd085-137">Descripción del servicio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd085-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="bd085-138">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="bd085-138">Step 5.</span></span> <span data-ttu-id="bd085-139">Planear la gobernanza</span><span class="sxs-lookup"><span data-stu-id="bd085-139">Plan for governance</span></span>

<span data-ttu-id="bd085-140">Determina los requisitos de gobierno y cómo puedes reunirse.</span><span class="sxs-lookup"><span data-stu-id="bd085-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="bd085-141">Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="bd085-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="bd085-142">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="bd085-142">Decision point</span></span> |<ul><li><span data-ttu-id="bd085-143">Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="bd085-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="bd085-144">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="bd085-144">Step 6.</span></span> <span data-ttu-id="bd085-145">Implementar Teams para la colaboración</span><span class="sxs-lookup"><span data-stu-id="bd085-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="bd085-146">Después de que se haya incorporado a Microsoft 365 Government, consulte la ruta de implementación recomendada que se describe en [cómo implementar Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bd085-146">After you've been onboarded to Microsoft 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="bd085-147">Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.</span><span class="sxs-lookup"><span data-stu-id="bd085-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="bd085-148">También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bd085-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
