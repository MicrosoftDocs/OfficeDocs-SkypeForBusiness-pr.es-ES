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
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="e70f4-103">Planear las implementaciones de Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="e70f4-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="e70f4-104">Esta guía es para los profesionales de TI que están impulsando implementaciones de Office 365 en entidades gubernamentales federales de EE. UU. u otras entidades que administran datos sujetos a normativas y requisitos gubernamentales, donde el uso de Office 365 Government - GCC High es adecuado para cumplir estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="e70f4-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="e70f4-105">Si su organización ya ha cumplido los requisitos de elegibilidad de Office 365 Government : GCC High eligibility requirements and applied for and been accepted into the program, puede omitir los pasos 1 y 2 y ir directamente al paso 3.</span><span class="sxs-lookup"><span data-stu-id="e70f4-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="e70f4-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="e70f4-106">Step 1.</span></span> <span data-ttu-id="e70f4-107">Determine si su organización necesita Office 365 Government - GCC High y cumple los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70f4-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="e70f4-108">El entorno Office 365 Government - GCC High proporciona el cumplimiento de los requisitos del gobierno de EE. UU. para los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="e70f4-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="e70f4-109">Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Office 365 Government: GCC High:</span><span class="sxs-lookup"><span data-stu-id="e70f4-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="e70f4-110">El contenido de clientes de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e70f4-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="e70f4-111">El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e70f4-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="e70f4-112">El acceso al contenido de clientes de su organización está restringido al personal de Microsoft con pantalla.</span><span class="sxs-lookup"><span data-stu-id="e70f4-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="e70f4-113">Office 365 Government: GCC High cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="e70f4-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="e70f4-114">Puede encontrar más información sobre la oferta Office 365 Government – GCC High para los clientes del gobierno de EE. UU. en los planes de [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluidos los [requisitos de elegibilidad.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="e70f4-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="e70f4-115">La descripción del servicio de [Office 365 Us Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describe las ventajas de la plataforma, que se centra en cumplir los requisitos de cumplimiento dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e70f4-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="e70f4-116">Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: Relevante para mi organización **Y/N** y Satisface las necesidades de mi organización **Y/N**.</span><span class="sxs-lookup"><span data-stu-id="e70f4-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="e70f4-117">Después, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="e70f4-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="e70f4-119">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="e70f4-119">Decision points</span></span>|<ul><li><span data-ttu-id="e70f4-120">Decida si Office 365 Government - GCC High es adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="e70f4-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="e70f4-121">Confirme que su organización cumple los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="e70f4-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="e70f4-122">Office 365 Government: GCC High solo está disponible en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e70f4-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="e70f4-123">Los clientes que no son del gobierno de EE. UU. pueden elegir entre varios planes [de Office 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="e70f4-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="e70f4-124">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="e70f4-124">Step 2.</span></span> <span data-ttu-id="e70f4-125">Solicitar Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="e70f4-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="e70f4-126">Después de haber decidido que este servicio es adecuado para su organización, inicie el proceso de solicitud [de este servicio.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="e70f4-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="e70f4-127">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="e70f4-127">Step 3.</span></span> <span data-ttu-id="e70f4-128">Comprender la configuración de seguridad predeterminada de Office 365 Government: GCC High default.</span><span class="sxs-lookup"><span data-stu-id="e70f4-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="e70f4-129">Le recomendamos que se tome [](enable-features-office-365.md) un tiempo para revisar detenidamente la configuración de seguridad y administración antes de modificarlas, y tenga en cuenta los impactos en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e70f4-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="e70f4-131">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="e70f4-131">Decision point</span></span>|<ul><li><span data-ttu-id="e70f4-132">Decida si tendrá que modificar alguna de las opciones predeterminadas de Office 365 Government : GCC High security settings( Administración pública predeterminada: GCC) y resuelva primero el impacto de los cambios que pueda realizar.</span><span class="sxs-lookup"><span data-stu-id="e70f4-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="e70f4-133">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="e70f4-133">Step 4.</span></span> <span data-ttu-id="e70f4-134">Comprender qué capacidades de Teams están disponibles actualmente en Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="e70f4-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="e70f4-135">Para adaptarse a los requisitos de nuestros clientes en la nube del gobierno, hay algunas diferencias entre Teams en Office 365 Government : GCC High y Teams en los planes enterprise.</span><span class="sxs-lookup"><span data-stu-id="e70f4-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="e70f4-136">Consulte la tabla siguiente para ver qué características están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e70f4-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="e70f4-137">Descripción del servicio de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e70f4-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="e70f4-138">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="e70f4-138">Step 5.</span></span> <span data-ttu-id="e70f4-139">Plan de gobernanza</span><span class="sxs-lookup"><span data-stu-id="e70f4-139">Plan for governance</span></span>

<span data-ttu-id="e70f4-140">Determine sus requisitos de gobernanza y cómo puede cumplirlos.</span><span class="sxs-lookup"><span data-stu-id="e70f4-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="e70f4-141">Vaya a [Planear el gobierno en Teams](plan-teams-governance.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e70f4-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="e70f4-142">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="e70f4-142">Decision point</span></span> |<ul><li><span data-ttu-id="e70f4-143">Determine y documente los requisitos de gobernanza siguiendo las directrices de [Plan de gobernanza en Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="e70f4-144">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="e70f4-144">Step 6.</span></span> <span data-ttu-id="e70f4-145">Implementar Teams para colaboración</span><span class="sxs-lookup"><span data-stu-id="e70f4-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="e70f4-146">Después de incorporarse a Office 365 Government: GCC High, siga la ruta de implementación recomendada que se describe en Cómo implementar [Microsoft Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e70f4-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="e70f4-147">Asegúrese de participar con su equipo de adopción y administración de cambios y con los campeones de Teams.</span><span class="sxs-lookup"><span data-stu-id="e70f4-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="e70f4-148">También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o su partner elegido para incorporar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e70f4-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="e70f4-149">El cliente de Mac Teams para entornos GCCH aún no es compatible.</span><span class="sxs-lookup"><span data-stu-id="e70f4-149">The Mac Teams client for GCCH environments is not yet supported.</span></span>