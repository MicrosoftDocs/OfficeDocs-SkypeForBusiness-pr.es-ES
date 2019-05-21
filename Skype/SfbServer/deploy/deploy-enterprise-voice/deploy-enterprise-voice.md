---
title: Implementar la telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumen: Aprenda a implementar la telefonía IP empresarial para Skype empresarial Server en un sitio central.'
ms.openlocfilehash: c5995570d8d3cf775b2837bb6ddfc170860d57dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291245"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2ecb7-103">Implementar la telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="2ecb7-104">**Resumen:** Aprenda a implementar la telefonía IP empresarial para Skype empresarial Server en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="2ecb7-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="2ecb7-105">Use este tema para implementar la telefonía IP empresarial en un sitio central.</span><span class="sxs-lookup"><span data-stu-id="2ecb7-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="2ecb7-106">Para implementar la telefonía IP empresarial en un sitio de sucursal, vaya a [implementar sitios de sucursales](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ecb7-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="2ecb7-107">En esta sección se incluyen procedimientos para implementaciones en las que un servidor de mediación se encuentra en cada servidor front-end o servidor Standard Edition, como se recomienda, y también para implementaciones con un grupo de servidores de mediación independiente. Puede omitir el siguiente contenido si usó el generador de topología para definir y publicar una topología que collocates un servidor de mediación en cada servidor front-end o un servidor Standard Edition, ya que el Asistente para la implementación ya instaló automáticamente los archivos para Servidor de mediación al instalar archivos para el grupo de servidores front-end o el servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="2ecb7-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="2ecb7-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ecb7-108">In this section</span></span>

- [<span data-ttu-id="2ecb7-109">Requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="2ecb7-110">Implementar un servidor de mediación en el generador de topología en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="2ecb7-111">Definir una puerta de enlace en el generador de topologías de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="2ecb7-112">Definir más troncos en el generador de topología en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="2ecb7-113">Instalar los archivos para el servidor de mediación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="2ecb7-114">Configurar troncos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="2ecb7-115">Crear o modificar una regla de traducción para la presentación de identificación de llamadas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="2ecb7-116">Crear o modificar una regla de traducción para la presentación de identificador llamada en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="2ecb7-117">Crear o modificar una regla de normalización en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="2ecb7-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="2ecb7-118">Crear o modificar un plan de marcado en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="2ecb7-119">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="2ecb7-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="2ecb7-120">Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="2ecb7-121">Implementar características avanzadas de telefonía empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="2ecb7-122">Implementar características de administración de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="2ecb7-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="2ecb7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ecb7-123">See also</span></span>

[<span data-ttu-id="2ecb7-124">Planear la telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ecb7-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

