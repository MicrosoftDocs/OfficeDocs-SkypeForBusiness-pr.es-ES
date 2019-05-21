---
title: Configuración y administración de Skype Empresarial Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
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
description: Aprenda a configurar la edición de Skype empresarial Cloud Connector, una topología local mínima para habilitar la integración de su infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (PBX en la nube) en Skype empresarial online.
ms.openlocfilehash: 49c0ce1a67b579a566e2dd22b9b345c1d6a4afdd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287401"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="3311f-103">Configuración y administración de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="3311f-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="3311f-104">Aprenda a configurar la edición de Skype empresarial Cloud Connector, una topología local mínima para habilitar la integración de su infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (PBX en la nube) en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="3311f-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="3311f-105">Antes de empezar, debe revisar los requisitos previos de [plan de Skype empresarial Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="3311f-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3311f-106">Los pasos incluidos en este tema se aplican solamente a Cloud Connector Edition 1.4.1. y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3311f-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="3311f-107">Si aún no ha actualizado a Cloud Connector Edition 2.1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="3311f-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="3311f-108">Puede descargar el archivo de instalación de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="3311f-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="3311f-109">Pasos para configurar Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="3311f-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="3311f-110">En la siguiente tabla se indican los pasos que necesitará seguir para instalar y configurar Skype Empresarial Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="3311f-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="3311f-111">**Paso**</span><span class="sxs-lookup"><span data-stu-id="3311f-111">**Step**</span></span>|<span data-ttu-id="3311f-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3311f-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3311f-113">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3311f-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="3311f-114">Descargue el archivo de instalación, prepare certificados, configure Hyper-V y Prepare su entorno para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3311f-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="3311f-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3311f-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="3311f-116">Cree un sitio en su implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3311f-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="3311f-117">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3311f-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="3311f-118">Agregue sitios a la implementación y aprenda acerca de las diferencias entre implementaciones de un único sitio o de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="3311f-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="3311f-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="3311f-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="3311f-120">Agregue registros de DNS, configure la conectividad híbrida, configure las puertas de enlace RTC y habilite a los usuarios para el correo de voz del Sistema telefónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3311f-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="3311f-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="3311f-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3311f-122">Asegúrese de que la implementación funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="3311f-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="3311f-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3311f-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="3311f-124">Actualice la implementación existente de Cloud Connector a la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="3311f-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="3311f-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="3311f-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3311f-126">Cambie la configuración en Cloud Connector después de que ya se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="3311f-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="3311f-127">Implementación de omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="3311f-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="3311f-128">Aprenda a implementar la omisión de medios en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3311f-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="3311f-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="3311f-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="3311f-130">Aprenda acerca de los cmdlets de PowerShell usados en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3311f-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="3311f-131">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3311f-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3311f-132">Soluciones a problemas comunes relacionados con la implementación de un conector de nube.</span><span class="sxs-lookup"><span data-stu-id="3311f-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

