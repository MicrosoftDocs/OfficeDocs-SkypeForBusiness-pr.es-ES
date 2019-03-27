---
title: Configuración de troncos en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o más pares para proporcionar conectividad con telefónica conmutada (RTC) para los clientes de Enterprise Voice y dispositivos de la organización.
ms.openlocfilehash: 5e07f0152aac32c4d57962cf619e56777221c955
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883973"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="d7577-103">Configuración de troncos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d7577-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="d7577-104">Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes elementos del mismo nivel para proporcionar conectividad de telefónica conmutada (RTC) de la red de clientes de Enterprise Voice y dispositivos en su organización:</span><span class="sxs-lookup"><span data-stu-id="d7577-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="d7577-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="d7577-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="d7577-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d7577-106">PSTN gateway</span></span>
- <span data-ttu-id="d7577-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="d7577-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="d7577-108">Para obtener información detallada, consulte [Plan para la conectividad de RTC en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="d7577-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7577-109">Antes de comenzar la configuración del tronco, compruebe que se ha creado la topología y que el servidor de mediación y su mismo nivel han se han configurado y asociados entre sí.</span><span class="sxs-lookup"><span data-stu-id="d7577-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="d7577-110">Para obtener más información, consulte [definir una puerta de enlace en el generador de Skype para Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="d7577-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7577-111">Como parte de la configuración de tronco, puede habilitar la Skype para la característica de omisión de medios Business Server, que permite medios omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d7577-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="d7577-112">Se pueden configurar troncos con o sin desvío de medios habilitado, pero se recomienda encarecidamente que habilite.</span><span class="sxs-lookup"><span data-stu-id="d7577-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="d7577-113">Para obtener información detallada, vea [Plan para los medios de desvío en Skype para la empresa](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d7577-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
