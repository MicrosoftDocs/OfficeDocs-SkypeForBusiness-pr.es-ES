---
title: Configuración de troncos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más homólogos para proporcionar conectividad de red telefónica conmutada (RTC) a los clientes y dispositivos de telefonía empresarial de su organización.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817020"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="d8bb7-103">Configuración de troncos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8bb7-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="d8bb7-104">Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:</span><span class="sxs-lookup"><span data-stu-id="d8bb7-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="d8bb7-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="d8bb7-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="d8bb7-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d8bb7-106">PSTN gateway</span></span>
- <span data-ttu-id="d8bb7-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="d8bb7-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="d8bb7-108">Para obtener más información, consulte [planear la conectividad RTC en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="d8bb7-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8bb7-109">Antes de comenzar con la configuración troncal, verifique que se haya creado la topología y que el servidor de mediación y sus pares se hayan configurado y asociado entre sí.</span><span class="sxs-lookup"><span data-stu-id="d8bb7-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="d8bb7-110">Para obtener más información, vea [definir una puerta de enlace en el generador de topologías de Skype empresarial Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="d8bb7-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d8bb7-111">Como parte de la configuración troncal, puede habilitar la característica de omisión de medios de Skype empresarial Server, que permite a los medios eludir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d8bb7-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="d8bb7-112">Los troncos se pueden configurar con o sin omisión de medios habilitados, pero le recomendamos encarecidamente que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="d8bb7-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="d8bb7-113">Para obtener más información, consulte [planear la omisión de medios en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d8bb7-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
