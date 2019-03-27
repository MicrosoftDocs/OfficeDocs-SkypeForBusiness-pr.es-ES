---
title: Configuración y administración de Skype Empresarial Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Obtenga información sobre cómo configurar Skype para Business Edition de conector de en la nube, una topología mínima local para habilitar la integración de la infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (en la nube PBX) de Skype para profesionales en línea.
ms.openlocfilehash: 5d057a299e51bfb83bd6711fcf1fbe8b4ee98f02
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898001"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="30fc5-103">Configuración y administración de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="30fc5-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="30fc5-104">Obtenga información sobre cómo configurar Skype para Business Edition de conector de en la nube, una topología mínima local para habilitar la integración de la infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (en la nube PBX) de Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="30fc5-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="30fc5-105">Antes de comenzar, debe revisar los requisitos previos de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="30fc5-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="30fc5-106">Los pasos incluidos en este tema se aplican solamente a Cloud Connector Edition 1.4.1. y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="30fc5-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="30fc5-107">Si aún no ha actualizado a Cloud Connector Edition 2.1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="30fc5-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="30fc5-108">Puede descargar el archivo de instalación de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="30fc5-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="30fc5-109">Pasos para configurar Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="30fc5-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="30fc5-110">En la siguiente tabla se indican los pasos que necesitará seguir para instalar y configurar Skype Empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="30fc5-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="30fc5-111">**Paso**</span><span class="sxs-lookup"><span data-stu-id="30fc5-111">**Step**</span></span>|<span data-ttu-id="30fc5-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="30fc5-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="30fc5-113">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="30fc5-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="30fc5-114">Descargue el archivo de instalación, preparar los certificados, configurar Hyper-V y preparar su entorno para la implementación de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="30fc5-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="30fc5-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="30fc5-116">Cree un sitio en su implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="30fc5-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-117">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="30fc5-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="30fc5-118">Agregue sitios a la implementación y aprenda acerca de las diferencias entre implementaciones de un único sitio o de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="30fc5-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="30fc5-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="30fc5-120">Agregue registros de DNS, configure la conectividad híbrida, configure las puertas de enlace RTC y habilite a los usuarios para el correo de voz del Sistema telefónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="30fc5-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="30fc5-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="30fc5-122">Asegúrese de que la implementación funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="30fc5-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="30fc5-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="30fc5-124">Actualice la implementación existente de Cloud Connector a la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="30fc5-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="30fc5-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="30fc5-126">Cambiar la configuración en la nube Connector después de que ya está implementado.</span><span class="sxs-lookup"><span data-stu-id="30fc5-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-127">Implementar el desvío de medios en la nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="30fc5-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="30fc5-128">Aprenda a implementar la omisión de medios en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="30fc5-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="30fc5-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="30fc5-130">Aprenda acerca de los cmdlets de PowerShell usados en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="30fc5-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="30fc5-131">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="30fc5-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="30fc5-132">Soluciones para problemas comunes encontrados con una implementación de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="30fc5-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

