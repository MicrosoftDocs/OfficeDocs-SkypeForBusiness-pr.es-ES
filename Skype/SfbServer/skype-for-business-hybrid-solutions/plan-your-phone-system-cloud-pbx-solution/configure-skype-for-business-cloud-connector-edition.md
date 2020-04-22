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
description: Obtenga información sobre cómo configurar Skype empresarial Cloud Connector Edition, una topología local mínima para habilitar la integración de su infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (PBX en la nube) en Skype empresarial online.
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779166"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="4ba76-103">Configuración y administración de Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ba76-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="4ba76-104">Obtenga información sobre cómo configurar Skype empresarial Cloud Connector Edition, una topología local mínima para habilitar la integración de su infraestructura de voz local con el sistema telefónico en los servicios de voz de Office 365 (PBX en la nube) en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="4ba76-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="4ba76-105">Antes de empezar, debe revisar los requisitos previos de [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="4ba76-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ba76-106">Los pasos de este tema solo se aplican a Cloud Connector Edition 1.4.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ba76-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="4ba76-107">Si aún no ha actualizado a Cloud Connector Edition 2,1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4ba76-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="4ba76-108">Puede descargar el archivo de instalación desde [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="4ba76-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="4ba76-109">Pasos para configurar Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ba76-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="4ba76-110">En la siguiente tabla se enumeran los pasos necesarios para instalar y configurar Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="4ba76-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="4ba76-111">**Paso**</span><span class="sxs-lookup"><span data-stu-id="4ba76-111">**Step**</span></span>|<span data-ttu-id="4ba76-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4ba76-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4ba76-113">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="4ba76-114">Descargue el archivo de instalación, prepare los certificados, configure Hyper-V y consiga que el entorno esté preparado para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ba76-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-115">Implementar un solo sitio en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="4ba76-116">Cree un sitio en la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ba76-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-117">Implementar varios sitios en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="4ba76-118">Agregue sitios a la implementación y obtenga información sobre las diferencias entre las implementaciones de un único sitio y de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="4ba76-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-119">Configurar la integración de Cloud Connector con la organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba76-119">Configure Cloud Connector integration with your Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="4ba76-120">Agregue registros DNS, configure Hybrid, configure puertas de enlace RTC y habilite a los usuarios para el sistema telefónico en el correo de voz de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ba76-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-121">Validar la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4ba76-122">Asegúrese de que la implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ba76-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-123">Actualizar a una nueva versión de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="4ba76-124">Actualice la implementación existente de Cloud Connector a la versión 2,1.</span><span class="sxs-lookup"><span data-stu-id="4ba76-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-125">Modificación de la configuración de una implementación existente de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4ba76-126">Cambie la configuración en Cloud Connector después de que ya se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="4ba76-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-127">Implementación de la omisión de medios en Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ba76-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="4ba76-128">Obtenga información sobre cómo implementar la omisión de medios en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ba76-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-129">Referencia del cmdlet de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="4ba76-130">Obtenga información sobre los cmdlets de PowerShell que se usan en Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ba76-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="4ba76-131">Solución de problemas de la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ba76-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4ba76-132">Soluciones a problemas comunes encontrados con una implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ba76-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

