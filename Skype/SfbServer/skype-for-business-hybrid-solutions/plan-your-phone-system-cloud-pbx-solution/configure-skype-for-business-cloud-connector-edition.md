---
title: Configuración y administración de Skype Empresarial Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Obtenga información sobre cómo configurar Skype para Business Edition de conector de en la nube, una topología mínima local para habilitar la integración de la infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (en la nube PBX) de Skype para profesionales en línea.
ms.openlocfilehash: 6cbf01b5b155fd3e234ef2a1827eb52580d22d2f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6e26d-103">Configuración y administración de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6e26d-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="6e26d-104">Obtenga información sobre cómo configurar Skype para Business Edition de conector de en la nube, una topología mínima local para habilitar la integración de la infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (en la nube PBX) de Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="6e26d-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="6e26d-105">Antes de comenzar, debe revisar los requisitos previos de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="6e26d-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6e26d-106">Los pasos incluidos en este tema se aplican solamente a Cloud Connector Edition 1.4.1. y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6e26d-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="6e26d-107">Si aún no ha actualizado a la nube conector Edition 2.1, consulte [actualizar a una nueva versión del conector en la nube](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6e26d-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="6e26d-108">Puede descargar el archivo de instalación de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="6e26d-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6e26d-109">Pasos para configurar Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6e26d-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="6e26d-110">En la siguiente tabla se indican los pasos que necesitará seguir para instalar y configurar Skype Empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="6e26d-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="6e26d-111">**Paso**</span><span class="sxs-lookup"><span data-stu-id="6e26d-111">**Step**</span></span>|<span data-ttu-id="6e26d-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6e26d-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6e26d-113">Preparar el dispositivo de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="6e26d-114">Descargue el archivo de instalación, preparar los certificados, configurar Hyper-V y preparar su entorno para la implementación de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="6e26d-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-115">Implementar un sitio de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="6e26d-116">Cree un sitio en su implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6e26d-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-117">Implementar varios sitios de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="6e26d-118">Agregue sitios a la implementación y aprenda acerca de las diferencias entre implementaciones de un único sitio o de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="6e26d-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-119">Configurar la integración de conector en la nube con el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="6e26d-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="6e26d-120">Agregue registros de DNS, configure la conectividad híbrida, configure las puertas de enlace RTC y habilite a los usuarios para el correo de voz del Sistema telefónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e26d-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-121">Validar la implementación del conector de la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6e26d-122">Asegúrese de que la implementación funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="6e26d-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-123">Actualizar a una nueva versión del conector de la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="6e26d-124">Actualice la implementación existente de Cloud Connector a la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="6e26d-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-125">Modificar la configuración de una implementación existente de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6e26d-126">Cambiar la configuración en la nube Connector después de que ya está implementado.</span><span class="sxs-lookup"><span data-stu-id="6e26d-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-127">Implementar el desvío de medios en la nube conector Edition</span><span class="sxs-lookup"><span data-stu-id="6e26d-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="6e26d-128">Aprenda a implementar la omisión de medios en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6e26d-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-129">Referencia del cmdlet de conector de nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="6e26d-130">Aprenda acerca de los cmdlets de PowerShell usados en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6e26d-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6e26d-131">Solución de problemas de la implementación del conector de la nube</span><span class="sxs-lookup"><span data-stu-id="6e26d-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6e26d-132">Soluciones para problemas comunes encontrados con una implementación de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="6e26d-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

