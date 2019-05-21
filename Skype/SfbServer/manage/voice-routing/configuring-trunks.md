---
title: Configuración de troncos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más homólogos para proporcionar conectividad de red telefónica conmutada (RTC) a los clientes y dispositivos de telefonía empresarial de su organización.
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275006"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="689c1-103">Configuración de troncos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="689c1-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="689c1-104">Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:</span><span class="sxs-lookup"><span data-stu-id="689c1-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="689c1-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="689c1-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="689c1-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="689c1-106">PSTN gateway</span></span>
- <span data-ttu-id="689c1-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="689c1-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="689c1-108">Para obtener más información, consulte [planear la conectividad RTC en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="689c1-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="689c1-109">Antes de comenzar con la configuración troncal, verifique que se haya creado la topología y que el servidor de mediación y sus pares se hayan configurado y asociado entre sí.</span><span class="sxs-lookup"><span data-stu-id="689c1-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="689c1-110">Para obtener más información, vea [definir una puerta de enlace en el generador de topologías de Skype empresarial Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="689c1-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="689c1-111">Como parte de la configuración troncal, puede habilitar la característica de omisión de medios de Skype empresarial Server, que permite a los medios eludir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="689c1-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="689c1-112">Los troncos se pueden configurar con o sin omisión de medios habilitados, pero le recomendamos encarecidamente que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="689c1-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="689c1-113">Para obtener más información, consulte [planear la omisión de medios en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="689c1-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
