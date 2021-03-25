---
title: 'Microsoft 365 Government: implementaciones de GCC'
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Microsoft 365 en entidades que administran datos sujetos a la normativa gubernamental de EE. UU.
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
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="389c7-103">Planear las implementaciones de Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="389c7-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="389c7-104">Esta guía es para los profesionales de TI que están impulsando implementaciones de Microsoft 365 en entidades gubernamentales federales, estatales, locales, tribales o territoriales u otras entidades que administran datos sujetos a normativas y requisitos gubernamentales, donde el uso de Microsoft 365 Government - GCC es adecuado para cumplir estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="389c7-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="389c7-105">Nuevo 26 de marzo de 2020: No se pierda nuestra guía de inicio rápido descargable [para GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)</span><span class="sxs-lookup"><span data-stu-id="389c7-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="389c7-106">Microsoft Teams está experimentando un pico tremendo en llamadas en línea y conferencias de audio y vídeo debido a la pandemia de coronavirus (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="389c7-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="389c7-107">En respuesta al aumento sin precedentes de llamadas y para garantizar la continuidad y la disponibilidad, Microsoft permite que los servidores de audio y vídeo GCC de Microsoft Teams aprovechen la capacidad de procesamiento en nuestros centros de datos comerciales, así como en nuestros centros de datos gubernamentales.</span><span class="sxs-lookup"><span data-stu-id="389c7-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="389c7-108">Estos servidores de audio y vídeo se encuentran dentro de los servidores límite de acreditación de Microsoft Azure FedRAMP High en los Estados Unidos y no almacenan contenido de los clientes.</span><span class="sxs-lookup"><span data-stu-id="389c7-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="389c7-109">Sin embargo, estos servidores están procesando audio y vídeo para llamadas y conferencias y operan bajo nuestro personal comercial durante este período provisional.</span><span class="sxs-lookup"><span data-stu-id="389c7-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="389c7-110">El personal cualificado y con pantalla supervisa estos servidores para obtener acceso potencial a los datos de los clientes revisando los inicios de sesión interactivos en estos servidores.</span><span class="sxs-lookup"><span data-stu-id="389c7-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="389c7-111">El personal cualificado cumple los requisitos de GCC para acceder al contenido del cliente.</span><span class="sxs-lookup"><span data-stu-id="389c7-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="389c7-112">Para obtener más información sobre los requisitos de detección, vea la [descripción del servicio GCC.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="389c7-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="389c7-113">Gracias por su soporte mientras tomamos medidas para garantizar que nuestros servicios sigan estando disponibles y confiables en estos momentos extraordinarios.</span><span class="sxs-lookup"><span data-stu-id="389c7-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="389c7-114">Si su organización ya ha cumplido los requisitos de elegibilidad de Microsoft 365 Government - GCC y ha solicitado y se ha aceptado en el programa, puede omitir los pasos 1 y 2 e ir directamente al paso 3.</span><span class="sxs-lookup"><span data-stu-id="389c7-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="389c7-115">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="389c7-115">Step 1.</span></span> <span data-ttu-id="389c7-116">Determine si su organización necesita Microsoft 365 Government - GCC y cumple los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="389c7-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="389c7-117">El entorno Gobierno de Microsoft 365 : GCC proporciona cumplimiento con los requisitos del gobierno de EE. UU. para los servicios en la nube, incluidos FedRAMP Moderado, y los requisitos para la justicia penal y los sistemas de información fiscal federal (tipos de datos CJI y FTI).</span><span class="sxs-lookup"><span data-stu-id="389c7-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="389c7-118">Además de disfrutar de las características y capacidades de Microsoft 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 Government : GCC:</span><span class="sxs-lookup"><span data-stu-id="389c7-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="389c7-119">El contenido de clientes de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Microsoft 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="389c7-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="389c7-120">El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="389c7-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="389c7-121">El acceso al contenido de clientes de su organización está restringido al personal de Microsoft con pantalla.</span><span class="sxs-lookup"><span data-stu-id="389c7-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="389c7-122">Microsoft 365 Government: GCC cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="389c7-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="389c7-123">Puede encontrar más información sobre la oferta de Microsoft 365 Government - GCC para los clientes del gobierno de EE. UU. en los planes gubernamentales de [Microsoft 365,](https://products.office.com/government/compare-office-365-government-plans)incluidos los [requisitos de elegibilidad.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="389c7-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="389c7-124">La descripción del servicio del gobierno de Los Estados Unidos de [Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describe las ventajas de la plataforma, que se centra en cumplir los requisitos de cumplimiento dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="389c7-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="389c7-125">Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: Relevante para mi organización **Y/N** y Satisface las necesidades de mi organización **Y/N**.</span><span class="sxs-lookup"><span data-stu-id="389c7-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="389c7-126">Después, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="389c7-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="389c7-128">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="389c7-128">Decision points</span></span>|<ul><li><span data-ttu-id="389c7-129">Decida si Microsoft 365 Government - GCC es adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="389c7-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="389c7-130">Confirme que su organización cumple los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="389c7-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="389c7-131">Microsoft 365 Government: GCC solo está disponible en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="389c7-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="389c7-132">Los clientes que no son del gobierno de EE. UU. pueden elegir entre varios planes de [Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="389c7-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="389c7-133">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="389c7-133">Step 2.</span></span> <span data-ttu-id="389c7-134">Solicitar Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="389c7-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="389c7-135">Después de haber decidido que este servicio es adecuado para su organización, inicie el proceso de solicitar [este servicio aquí.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="389c7-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="389c7-136">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="389c7-136">Step 3.</span></span> <span data-ttu-id="389c7-137">Comprender la configuración de seguridad predeterminada de Microsoft 365 Government: GCC.</span><span class="sxs-lookup"><span data-stu-id="389c7-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="389c7-138">Le recomendamos que se tome [](enable-features-office-365.md) un tiempo para revisar detenidamente la configuración de seguridad y administración antes de modificarlas, y tenga en cuenta los impactos en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="389c7-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="389c7-140">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="389c7-140">Decision point</span></span>|<ul><li><span data-ttu-id="389c7-141">Decida si va a modificar alguna de las opciones predeterminadas de configuración de seguridad de Microsoft 365 Government - GCC, resolviendo primero el impacto de los cambios que pueda realizar.</span><span class="sxs-lookup"><span data-stu-id="389c7-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="389c7-142">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="389c7-142">Step 4.</span></span> <span data-ttu-id="389c7-143">Comprender qué capacidades no están disponibles o deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="389c7-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="389c7-144">Para adaptarse a los requisitos de nuestros clientes en la nube gubernamentales, hay algunas diferencias entre los planes de Microsoft 365 Government - GCC y Enterprise.</span><span class="sxs-lookup"><span data-stu-id="389c7-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="389c7-145">Consulte la tabla siguiente para ver qué características están disponibles.</span><span class="sxs-lookup"><span data-stu-id="389c7-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="389c7-146">Descripción del servicio de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="389c7-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="389c7-147">Una vez que otras cargas de trabajo estén totalmente disponibles en la nube de GCC, estarán disponibles en Teams cuando se complete todo el trabajo de integración adicional.</span><span class="sxs-lookup"><span data-stu-id="389c7-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="389c7-149">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="389c7-149">Decision point</span></span>|<ul><li><span data-ttu-id="389c7-150">Decida si el conjunto de características de Teams satisface las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="389c7-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="389c7-151">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="389c7-151">Step 5.</span></span> <span data-ttu-id="389c7-152">Plan de gobernanza</span><span class="sxs-lookup"><span data-stu-id="389c7-152">Plan for governance</span></span>

<span data-ttu-id="389c7-153">Determine sus requisitos de gobernanza y cómo puede cumplirlos.</span><span class="sxs-lookup"><span data-stu-id="389c7-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="389c7-154">Vaya a [Planear el gobierno en Teams](plan-teams-governance.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="389c7-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="389c7-156">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="389c7-156">Decision point</span></span>|<ul><li><span data-ttu-id="389c7-157">Determine y documente los requisitos de gobernanza siguiendo las directrices de [Plan de gobernanza en Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="389c7-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="389c7-158">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="389c7-158">Step 6.</span></span> <span data-ttu-id="389c7-159">Implementar Teams para colaboración</span><span class="sxs-lookup"><span data-stu-id="389c7-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="389c7-160">Después de incorporarse a Microsoft 365 Government : GCC, siga la ruta de implementación recomendada que se describe en Cómo implementar [Microsoft Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="389c7-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="389c7-161">Asegúrese de participar con su equipo de adopción y administración de cambios y con los campeones de Teams.</span><span class="sxs-lookup"><span data-stu-id="389c7-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="389c7-162">También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o su partner elegido para incorporar el servicio.</span><span class="sxs-lookup"><span data-stu-id="389c7-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="389c7-163">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="389c7-163">Step 7.</span></span> <span data-ttu-id="389c7-164">Implementar Teams para reuniones y voz</span><span class="sxs-lookup"><span data-stu-id="389c7-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="389c7-165">Este también es un buen momento para usar Teams con su grupo de partes interesadas más amplio para empezar a planear la puesta en marcha de reuniones y características [de voz en la nube.](./cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="389c7-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>