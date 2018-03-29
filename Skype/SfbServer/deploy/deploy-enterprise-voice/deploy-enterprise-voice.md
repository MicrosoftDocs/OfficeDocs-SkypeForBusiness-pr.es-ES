---
title: Implementar la telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumen: Conozca cómo implementar la Telefonía IP empresarial de Skype para Business Server 2015 en un sitio central.'
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="29041-103">Implementar la telefonía IP empresarial en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="29041-104">**Resumen:** Aprenda a implementar la Telefonía IP empresarial de Skype para Business Server 2015 en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="29041-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="29041-105">Utilice este tema para implementar la Telefonía IP empresarial en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="29041-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="29041-106">Para implementar la Telefonía IP empresarial en un sitio de sucursal, vaya al [Implementar sitios de sucursal](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="29041-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="29041-107">Esta sección incluye los procedimientos para las implementaciones en que un servidor de mediación se combina en cada servidor Standard Edition o de servidor Front-End, como se recomienda y también para las implementaciones con un grupo de servidor de mediación de independiente. Puede omitir el contenido siguiente si utiliza el generador de topología para definir y publicar una topología que coloca un servidor de mediación en cada servidor Front-End o Standard Edition server, porque el Asistente para implementación automáticamente ya instalados los archivos de Servidor de mediación cuando instala los archivos para su grupo de servidor Front-End o un servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="29041-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="29041-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="29041-108">In this section</span></span>

- [<span data-ttu-id="29041-109">Requisitos previos de configuración y seguridad para Telefonía IP empresarial en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="29041-110">Implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="29041-111">Definir una puerta de enlace en el generador de topología en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="29041-112">Definir los troncos adicionales en el generador de topología en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="29041-113">Instalar los archivos de servidor de mediación en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="29041-114">Configurar los troncos en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="29041-115">Crear o modificar una regla de traducción para la presentación de ID del llamador en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="29041-116">Crear o modificar una regla de traducción para llamado presentación de ID en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="29041-117">Crear o modificar una regla de normalización en Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="29041-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="29041-118">Crear o modificar un plan de marcado de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="29041-119">Configurar directivas de voz, registros de uso PSTN y rutas de voz de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="29041-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="29041-120">Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="29041-121">Implementar las funciones avanzadas de Telefonía IP empresarial en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="29041-122">Implementar características de administración de llamadas de Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="29041-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="29041-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="29041-123">See also</span></span>

#### 

[<span data-ttu-id="29041-124">Plan para Telefonía IP empresarial en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="29041-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

