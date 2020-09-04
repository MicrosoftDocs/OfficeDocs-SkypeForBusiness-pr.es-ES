---
title: Configuración y administración de Skype empresarial Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Obtenga información sobre cómo configurar Skype empresarial Cloud Connector Edition, una topología local mínima para habilitar la integración de su infraestructura de voz local con los servicios de voz de sistema telefónico (PBX en la nube) en Skype empresarial online.
ms.openlocfilehash: e30fcb4cad44bffed495f1191e5e5cae73bb18cc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358796"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="ba252-103">Configuración y administración de Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ba252-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="ba252-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ba252-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="ba252-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="ba252-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="ba252-106">Obtenga información sobre cómo configurar Skype empresarial Cloud Connector Edition, una topología local mínima para habilitar la integración de su infraestructura de voz local con los servicios de voz de sistema telefónico (PBX en la nube) en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ba252-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="ba252-107">Antes de empezar, debe revisar los requisitos previos de [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="ba252-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba252-108">Los pasos de este tema solo se aplican a Cloud Connector Edition 1.4.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ba252-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="ba252-109">Si aún no ha actualizado a Cloud Connector Edition 2,1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="ba252-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="ba252-110">Puede descargar el archivo de instalación desde [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="ba252-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="ba252-111">Pasos para configurar Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ba252-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="ba252-112">En la siguiente tabla se enumeran los pasos necesarios para instalar y configurar Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="ba252-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="ba252-113">**Paso**</span><span class="sxs-lookup"><span data-stu-id="ba252-113">**Step**</span></span>|<span data-ttu-id="ba252-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ba252-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ba252-115">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="ba252-116">Descargue el archivo de instalación, prepare los certificados, configure Hyper-V y consiga que el entorno esté preparado para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba252-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="ba252-117">Implementar un solo sitio en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="ba252-118">Cree un sitio en la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba252-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="ba252-119">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="ba252-120">Agregue sitios a la implementación y obtenga información sobre las diferencias entre las implementaciones de un único sitio y de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="ba252-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="ba252-121">Configurar la integración de Cloud Connector con la organización de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="ba252-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="ba252-122">Agregue registros DNS, configure una implementación híbrida, configure puertas de enlace RTC y habilite a los usuarios para el correo de voz del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="ba252-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="ba252-123">Validar la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ba252-124">Asegúrese de que la implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba252-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="ba252-125">Actualizar a una versión nueva de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="ba252-126">Actualice la implementación existente de Cloud Connector a la versión 2,1.</span><span class="sxs-lookup"><span data-stu-id="ba252-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="ba252-127">Modificar la configuración de una implementación de Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="ba252-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ba252-128">Cambie la configuración en Cloud Connector después de que ya se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="ba252-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="ba252-129">Implementación de la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ba252-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="ba252-130">Obtenga información sobre cómo implementar la omisión de medios en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba252-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="ba252-131">Referencia de cmdlets de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="ba252-132">Obtenga información sobre los cmdlets de PowerShell que se usan en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba252-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="ba252-133">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ba252-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ba252-134">Soluciones a problemas comunes encontrados con una implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba252-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

