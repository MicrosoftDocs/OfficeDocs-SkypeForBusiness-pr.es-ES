---
title: Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276464"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="73d0b-103">Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="73d0b-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="73d0b-104">Decisiones necesarias para planear una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="73d0b-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="73d0b-105">Antes de configurar Skype empresarial para E9-1-1, necesita planear la implementación de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="73d0b-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="73d0b-106">Algunas de las cuestiones que necesitas tener en cuenta son:</span><span class="sxs-lookup"><span data-stu-id="73d0b-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="73d0b-107">**¿Cuáles son las obligaciones legales y directivas de la organización en relación con el E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="73d0b-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="73d0b-108">Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la terminología de E9-1-1) difieren de un estado a otro.</span><span class="sxs-lookup"><span data-stu-id="73d0b-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="73d0b-109">Debe consultar a su equipo legal para comprender las obligaciones que se pueden aplicar a su implementación de Skype empresarial en sus aspectos geográficos relevantes.</span><span class="sxs-lookup"><span data-stu-id="73d0b-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="73d0b-110">**¿Qué áreas de la empresa necesitan habilitarse para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="73d0b-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="73d0b-p103">Puedes habilitar E9-1-1 para determinadas ubicaciones o para toda la empresa. Por ejemplo, puedes tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="73d0b-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="73d0b-113">**¿Cómo implementará E9-1-1 en las sucursales?**</span><span class="sxs-lookup"><span data-stu-id="73d0b-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="73d0b-114">La resistencia de voz es un concepto que es importante tener en cuenta al implementar E9-1-1 en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="73d0b-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="73d0b-115">Si tienes troncos de E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicación o para conectar con el proveedor de servicios de servicios de emergencias.</span><span class="sxs-lookup"><span data-stu-id="73d0b-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="73d0b-116">Skype empresarial ofrece varias estrategias para manejar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="73d0b-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="73d0b-117">Para obtener más información, mira [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="73d0b-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="73d0b-118">**¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**</span><span class="sxs-lookup"><span data-stu-id="73d0b-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="73d0b-119">La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9 de Skype empresarial cuando no estén locales.</span><span class="sxs-lookup"><span data-stu-id="73d0b-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="73d0b-120">Por ejemplo, ¿permitirás a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente?</span><span class="sxs-lookup"><span data-stu-id="73d0b-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="73d0b-121">Si un cliente se encuentra fuera de la red empresarial, puede configurarse para solicitar al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="73d0b-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="73d0b-122">Pero como estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de redirigir la llamada al punto de respuesta de seguridad pública (PSAP).</span><span class="sxs-lookup"><span data-stu-id="73d0b-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="73d0b-123">Los clientes de Skype empresarial que se conectan a la red de la organización mediante VPN pueden retomar información interna de la dirección IP, pero estas direcciones no se pueden usar para identificar la ubicación real del usuario, por lo que es esencial que se excluyan las subredes VPN desde el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="73d0b-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="73d0b-124">**¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**</span><span class="sxs-lookup"><span data-stu-id="73d0b-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="73d0b-p106">Puede que quieras proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, crea un sitio y luego asigna directivas de voz a los sitios que hagan referencia a un uso de RTC que redirige la llamada a través de la puerta de enlace RTC local.</span><span class="sxs-lookup"><span data-stu-id="73d0b-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


