---
title: Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 39397064fe525a2b1324b8ef0a0f0bb1df287653
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114576"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="5d1ae-103">Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5d1ae-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="5d1ae-104">Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="5d1ae-105">Antes de configurar Skype Empresarial para E9-1-1, debe planear la implementación de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="5d1ae-106">Algunas de las preguntas que se deben tener en cuenta son:</span><span class="sxs-lookup"><span data-stu-id="5d1ae-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="5d1ae-107">**¿Cuáles son las obligaciones legales y de directiva de su organización con respecto a E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="5d1ae-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="5d1ae-108">Los requisitos legales de E9-1-1 para PBX (denominados Sistemas telefónicos de varias líneas o MLTS, en la parlancia E9-1-1) difieren de un estado a otro.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="5d1ae-109">Debe consultar con su equipo legal para comprender las obligaciones que pueden aplicarse a la implementación de Skype Empresarial en sus geografías relevantes.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="5d1ae-110">**¿Qué áreas dentro de su empresa deben habilitarse para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="5d1ae-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="5d1ae-111">Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-111">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="5d1ae-112">Por ejemplo, es posible que tenga distintos requisitos E9-1-1 para oficinas en distintos estados o que desee excluir sitios fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-112">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="5d1ae-113">**¿Cómo implementarÁ E9-1-1 en sitios de sucursal?**</span><span class="sxs-lookup"><span data-stu-id="5d1ae-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="5d1ae-114">La resistencia de voz es un concepto importante que se debe comprender al implementar E9-1-1 en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="5d1ae-115">Si tiene troncos SIP E-9-1-1 centralizados y se produce una interrupción de WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicación o conectarse al proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="5d1ae-116">Skype Empresarial proporciona varias estrategias para controlar la resistencia de voz en las sucursales, como tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o insertar llamadas de emergencia a la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="5d1ae-117">Para obtener más información, [vea Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span><span class="sxs-lookup"><span data-stu-id="5d1ae-117">For details, see [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span></span>

 <span data-ttu-id="5d1ae-118">**¿Habilitará E9-1-1 para usuarios que trabajen fuera de la red?**</span><span class="sxs-lookup"><span data-stu-id="5d1ae-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="5d1ae-119">La adquisición automática de ubicación solo está disponible para clientes ubicados dentro de la red de la organización, por lo que su organización debe decidir si admitirá las llamadas E9-1-1 realizadas desde clientes de Skype Empresarial mientras está fuera del entorno local.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="5d1ae-120">Por ejemplo, ¿permitirá a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio de cliente?</span><span class="sxs-lookup"><span data-stu-id="5d1ae-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="5d1ae-121">Si un cliente se encuentra fuera de la red empresarial, se puede configurar para solicitar al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="5d1ae-122">Sin embargo, dado que estas ubicaciones proporcionadas por el usuario no se pueden validar previamente con la Guía principal de direcciones de calle (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de enrutar la llamada al Punto de respuesta de seguridad pública (PSAP).</span><span class="sxs-lookup"><span data-stu-id="5d1ae-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="5d1ae-123">Los clientes de Skype Empresarial de los usuarios que se conectan a la red de su organización mediante VPN pueden recoger información de direcciones IP internas, pero como estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="5d1ae-124">**¿Desea proporcionar un enrutamiento de llamadas de emergencia a sitios fuera de LOS ESTADOS UNIDOS?**</span><span class="sxs-lookup"><span data-stu-id="5d1ae-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="5d1ae-125">Es posible que desee proporcionar enrutamiento de emergencia a áreas de su empresa que no son atendidas por un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales).</span><span class="sxs-lookup"><span data-stu-id="5d1ae-125">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="5d1ae-126">Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.</span><span class="sxs-lookup"><span data-stu-id="5d1ae-126">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>