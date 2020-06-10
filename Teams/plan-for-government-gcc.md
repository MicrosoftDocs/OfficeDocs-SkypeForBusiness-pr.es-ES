---
title: Implementaciones de Office 365 administración pública-GCC
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
ms.openlocfilehash: b93762c92d9681074124ba8ddb3fd066bdf8a60a
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665232"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="8b6b5-103">Planear las implementaciones de Office 365 Administrator-GCC</span><span class="sxs-lookup"><span data-stu-id="8b6b5-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="8b6b5-104">Esta guía está orientada a los profesionales de ti que están implantando implementaciones de Office 365 en entidades gubernamentales de Estados Unidos, Estados, locales, tribal o territoriales u otras entidades que administran datos que están sujetos a los requisitos y las reglamentaciones gubernamentales, donde el uso de Office 365 gobierno-GCC es adecuado para cumplir con estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="8b6b5-105">Nuevo 26 de marzo de 2020: no pierdamos nuestra [Guía de inicio rápido](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)descargable para GCC.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b6b5-106">Microsoft Teams está experimentando un enorme aumento en las llamadas en línea y las conferencias de audio y videollamadas debido a la coronavirus (COVID-19) Pandemic.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="8b6b5-107">En respuesta al aumento sin precedentes de las llamadas, y para garantizar la continuidad y la disponibilidad, Microsoft permite que Microsoft Teams GCC/audio/vídeo saque el máximo partido de la capacidad de procesamiento de nuestros centros de proceso de ventas comerciales, así como de nuestros centros de administración gubernamentales.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="8b6b5-108">Estos servidores de audio y vídeo se encuentran dentro de los servidores de límite de acreditación alta de Microsoft Azure FedRAMP en los Estados Unidos y no almacenan ningún contenido de cliente.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="8b6b5-109">Sin embargo, estos servidores están procesando el audio y el vídeo de las llamadas y las conferencias, y están operando bajo nuestro personal comercial durante este período provisional.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="8b6b5-110">El personal con pantalla calificada está supervisando estos servidores para obtener acceso potencial a los datos de los clientes revisando los inicios de sesión interactivos en estos servidores.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="8b6b5-111">El personal cualificado cumple con los requisitos de GCC para acceder al contenido de los clientes.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="8b6b5-112">Para obtener más información sobre los requisitos de filtrado, consulte la [Descripción del servicio GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="8b6b5-113">Gracias por tu ayuda a la hora de tomar medidas para asegurarnos de que nuestros servicios estén disponibles y sean confiables en estas extraordinarias horas.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="8b6b5-114">Si su organización ya cumple con los requisitos de idoneidad de Office 365 Government-GCC y ha sido aplicado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="8b6b5-115">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-115">Step 1.</span></span> <span data-ttu-id="8b6b5-116">Determine si su organización necesita Office 365 pública-GCC y cumple con los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="8b6b5-117">El entorno de Office 365 administración pública-GCC ofrece cumplimiento de los requisitos del gobierno de los Estados Unidos para servicios en la nube, incluidos FedRAMP moderado, y requisitos para los sistemas de información de la justicia y los impuestos federales (CJI y FTI tipos de datos).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="8b6b5-118">Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Office 365 administración pública-GCC:</span><span class="sxs-lookup"><span data-stu-id="8b6b5-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="8b6b5-119">El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="8b6b5-120">El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="8b6b5-121">El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="8b6b5-122">Office 365 Government-GCC cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="8b6b5-123">Puede encontrar más información sobre la oferta de Office 365 administración pública-GCC para los clientes del gobierno de los Estados Unidos en [office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="8b6b5-124">La [Descripción del servicio del gobierno de Office 365 Estados](https://technet.microsoft.com/library/mt774581.aspx) Unidos describe los beneficios de la plataforma, que se centran en los requisitos de cumplimiento de las reuniones de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="8b6b5-125">Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="8b6b5-126">Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8b6b5-128">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="8b6b5-128">Decision points</span></span>|<ul><li><span data-ttu-id="8b6b5-129">Decida si Office 365 Government-GCC es adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="8b6b5-130">Confirme que su organización cumple con los requisitos de elegibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="8b6b5-131">Office 365 Government-GCC solo está disponible en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="8b6b5-132">Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="8b6b5-133">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-133">Step 2.</span></span> <span data-ttu-id="8b6b5-134">Solicitar Office 365 administración pública-GCC</span><span class="sxs-lookup"><span data-stu-id="8b6b5-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="8b6b5-135">Tras haber decidido que este servicio es adecuado para su organización, aquí tiene que iniciar el proceso de [solicitar este servicio](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="8b6b5-136">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-136">Step 3.</span></span> <span data-ttu-id="8b6b5-137">Comprender la configuración de seguridad predeterminada de Office 365 administración pública GCC.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="8b6b5-138">Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8b6b5-140">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="8b6b5-140">Decision point</span></span>|<ul><li><span data-ttu-id="8b6b5-141">Decida si modificará cualquiera de la configuración de seguridad predeterminada de Office 365 administración pública-GCC y tendrá que comprender primero cuál es el impacto de los cambios que puede realizar.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="8b6b5-142">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-142">Step 4.</span></span> <span data-ttu-id="8b6b5-143">Comprender qué características no están disponibles o deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="8b6b5-144">Para cumplir con los requisitos de nuestros clientes gubernamentales de la nube, existen algunas diferencias entre los planes de Office 365 gubernamentales-GCC y Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="8b6b5-145">Consulte la tabla siguiente para ver qué características están disponibles.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="8b6b5-146">Descripción del servicio Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b6b5-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="8b6b5-147">Una vez que otras cargas de trabajo estén completamente disponibles en la nube de GCC, estarán disponibles en Teams cuando se complete todo el trabajo de integración adicional.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8b6b5-149">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="8b6b5-149">Decision point</span></span>|<ul><li><span data-ttu-id="8b6b5-150">Decida si el conjunto de características de Teams cumple con las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="8b6b5-151">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-151">Step 5.</span></span> <span data-ttu-id="8b6b5-152">Planear la gobernanza</span><span class="sxs-lookup"><span data-stu-id="8b6b5-152">Plan for governance</span></span>

<span data-ttu-id="8b6b5-153">Determina los requisitos de gobierno y cómo puedes reunirse.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="8b6b5-154">Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="8b6b5-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8b6b5-156">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="8b6b5-156">Decision point</span></span>|<ul><li><span data-ttu-id="8b6b5-157">Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="8b6b5-158">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-158">Step 6.</span></span> <span data-ttu-id="8b6b5-159">Implementar Teams para la colaboración</span><span class="sxs-lookup"><span data-stu-id="8b6b5-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="8b6b5-160">Después de que se haya incorporado a Office 365 Government – GCC, siga la ruta de implementación recomendada, [que se describe en cómo implementar Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="8b6b5-161">Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="8b6b5-162">También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="8b6b5-163">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="8b6b5-163">Step 7.</span></span> <span data-ttu-id="8b6b5-164">Implementar equipos para reuniones y voz</span><span class="sxs-lookup"><span data-stu-id="8b6b5-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="8b6b5-165">Este es también un buen momento para usar Teams con su grupo más amplio de participantes para empezar a planear la implementación de reuniones y [características de voz en la nube](cloud-voice-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="8b6b5-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

