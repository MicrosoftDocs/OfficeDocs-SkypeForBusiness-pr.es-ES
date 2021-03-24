---
title: Implementar Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Summary: Learn how to deploy Telefonía IP empresarial for Skype for Business Server at a central site.'
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104976"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="c145c-103">Implementar Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="c145c-104">**Resumen:** Obtenga información sobre cómo implementar Telefonía IP empresarial para Skype Empresarial Server en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="c145c-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="c145c-105">Use este tema para implementar Telefonía IP empresarial en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="c145c-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="c145c-106">Para implementar Telefonía IP empresarial en un sitio de sucursal, vaya a [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span><span class="sxs-lookup"><span data-stu-id="c145c-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="c145c-107">En esta sección se incluyen procedimientos para implementaciones en las que se coloca un servidor de mediación en cada servidor front-end o servidor Standard Edition, como se recomienda, y también para implementaciones con un grupo de servidores de mediación independiente. Puede omitir el siguiente contenido si usó el Generador de topologías para definir y publicar una topología que coloca un servidor de mediación en cada servidor front-end o servidor Standard Edition, ya que el Asistente para implementación ya instaló automáticamente los archivos para el servidor de mediación al instalar archivos para el grupo de servidores front-end o el servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="c145c-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="c145c-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c145c-108">In this section</span></span>

- [<span data-ttu-id="c145c-109">Requisitos previos de seguridad y configuración Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="c145c-110">Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="c145c-111">Definir una puerta de enlace en topology Builder en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="c145c-112">Definir troncos adicionales en topology Builder en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="c145c-113">Instalar los archivos para el servidor de mediación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="c145c-114">Configurar troncos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="c145c-115">Crear o modificar una regla de traducción para la presentación del identificador de autor de la llamada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="c145c-116">Crear o modificar una regla de traducción para la presentación de id. denominada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="c145c-117">Crear o modificar una regla de normalización en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c145c-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="c145c-118">Crear o modificar un plan de marcado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="c145c-119">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c145c-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="c145c-120">Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="c145c-121">Implementar características Telefonía IP empresarial avanzadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="c145c-122">Implementar características de administración de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c145c-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="c145c-123">Ver también</span><span class="sxs-lookup"><span data-stu-id="c145c-123">See also</span></span>

[<span data-ttu-id="c145c-124">Planeación de Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c145c-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)