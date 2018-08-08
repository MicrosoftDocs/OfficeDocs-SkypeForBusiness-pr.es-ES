---
title: Implementación de Enterprise Voice en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumen: Obtenga información sobre cómo implementar Enterprise Voice para Skype para Business Server en un sitio central.'
ms.openlocfilehash: db1048e4050ec5f9d58436bba5d5c3282f0c4b7f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968486"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="00749-103">Implementación de Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-103">Deploy Enterprise Voice in Skype for Business Server</span></span> 
 
<span data-ttu-id="00749-104">**Resumen:** Obtenga información sobre cómo implementar Enterprise Voice para Skype para Business Server en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="00749-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>
  
<span data-ttu-id="00749-105">Utilice este tema para implementar Enterprise Voice en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="00749-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="00749-106">Para implementar Enterprise Voice en un sitio de sucursal, pase a la [Implementación de sitios de sucursal](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="00749-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="00749-107">En esta sección se incluye procedimientos para las implementaciones en que un servidor de mediación se combina en cada servidor Front-End o Standard Edition, como se recomienda y también para las implementaciones con un grupo de servidores de mediación independiente. Puede omitir el contenido siguiente si utiliza el generador de topología para definir y publicar una topología que coloca un servidor de mediación en cada servidor Front-End o Standard Edition, debido a que el Asistente para la implementación instalado ya automáticamente los archivos para Servidor de mediación cuando instala los archivos para el grupo de servidores de Front-End o un servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="00749-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="00749-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="00749-108">In this section</span></span>

- [<span data-ttu-id="00749-109">Requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="00749-110">Implementar un servidor de mediación en el generador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="00749-111">Definir una puerta de enlace en el generador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="00749-112">Definición de troncos adicionales en el generador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="00749-113">Instalar los archivos para el servidor de mediación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="00749-114">Configuración de troncos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="00749-115">Crear o modificar una regla de conversión para la presentación del identificador de autor de la llamada de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="00749-116">Crear o modificar una regla de conversión para llamado presentación del identificador de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="00749-117">Crear o modificar una regla de normalización en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="00749-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="00749-118">Crear o modificar un plan de marcado de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)
    
- [<span data-ttu-id="00749-119">Configurar directivas de voz, registros de uso de RTC y rutas de voz de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="00749-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="00749-120">Habilitar a usuarios para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="00749-121">Implementación de características avanzadas de Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="00749-122">Implementar las características de administración de llamadas de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="00749-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="00749-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="00749-123">See also</span></span>

[<span data-ttu-id="00749-124">Planeación de Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="00749-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

