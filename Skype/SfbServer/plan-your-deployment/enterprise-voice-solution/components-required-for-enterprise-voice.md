---
title: Componentes necesarios de la Telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="0319a-103">Componentes necesarios de la Telefonía IP empresarial en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0319a-103">Components required for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0319a-104">Un resumen de los componentes de Telefonía IP empresarial en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0319a-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="0319a-105">Para implementar la Telefonía IP empresarial, son necesarios los siguientes componentes en su topología.</span><span class="sxs-lookup"><span data-stu-id="0319a-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="0319a-106">Uno o más servidores de mediación, que convierte las señales y, en algunas configuraciones, media entre el interno Skype para Business Server, la infraestructura de Telefonía IP empresarial y una puerta de enlace de telefonía pública conmutada (PSTN) de la red o un protocolo de inicio de sesión Tronco (SIP).</span><span class="sxs-lookup"><span data-stu-id="0319a-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="0319a-107">Los servidores de mediación son el componente más crucial en la implementación de Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="0319a-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="0319a-108">Para obtener más información, vea [componentes de servidor de mediación en Skype para Business Server 2015](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="0319a-108">For more information, see [Mediation Server component in Skype for Business Server 2015](mediation-server.md).</span></span>
    
    <span data-ttu-id="0319a-109">Servidores de mediación pueden ser colocados con servidores frontales o instalados como servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="0319a-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="0319a-110">Componentes de conectividad con RTC, que pueden incluir troncos SIP o puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="0319a-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="0319a-111">Para obtener más información, vea [componentes de conectividad PSTN en Skype para Business Server 2015](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="0319a-111">For more information, see [PSTN connectivity components in Skype for Business Server 2015](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="0319a-112">Servidores de borde, que permite el uso de las características de Telefonía IP empresarial por los usuarios cuando se encuentran fuera del cortafuegos de su organización.</span><span class="sxs-lookup"><span data-stu-id="0319a-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="0319a-113">El servicio de servidor perimetral de acceso proporciona la señalización SIP para las llamadas de Skype para usuarios profesionales que se encuentran fuera del cortafuegos de su organización.</span><span class="sxs-lookup"><span data-stu-id="0319a-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="0319a-114">El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls.</span><span class="sxs-lookup"><span data-stu-id="0319a-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="0319a-115">Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0319a-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="0319a-p104">El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.</span><span class="sxs-lookup"><span data-stu-id="0319a-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="0319a-118">Además, algunos componentes de Telefonía IP empresarial se ejecutan en servidores frontales.</span><span class="sxs-lookup"><span data-stu-id="0319a-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="0319a-119">Para obtener más información acerca de estos componentes, vea [componentes de VoIP de Front End servidor de Skype para Business Server 2015](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="0319a-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server 2015](front-end-server-voip.md)</span></span>
    

