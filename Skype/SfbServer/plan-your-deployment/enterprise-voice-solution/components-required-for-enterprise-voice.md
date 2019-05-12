---
title: Componentes necesarios para Enterprise Voice en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes de Enterprise Voice de Skype para Business Server.
ms.openlocfilehash: c37b11af2219d4e6375658e4ae675eff453c2c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925225"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="7ab2f-103">Componentes necesarios para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ab2f-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="7ab2f-104">Un resumen de los componentes de Enterprise Voice de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="7ab2f-105">Para implementar Enterprise Voice, se requieren los siguientes componentes en su topología.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="7ab2f-106">Uno o varios servidores de mediación, que traduce señalización y, en algunas configuraciones, medios entre su Skype interno para Business Server, la infraestructura de Enterprise Voice y una puerta de enlace de telefónica conmutada (RTC) o un protocolo de inicio de sesión Tronco (SIP).</span><span class="sxs-lookup"><span data-stu-id="7ab2f-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="7ab2f-107">Los servidores de mediación son el componente más importante en la implementación de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="7ab2f-108">Para obtener más información, vea [componentes de servidor de mediación en Skype para Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ab2f-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="7ab2f-109">Los servidores de mediación se pueden combinar con los servidores Front-End o instalados como servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="7ab2f-110">Componentes de conectividad con RTC, que pueden incluir troncos SIP o puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="7ab2f-111">Para obtener más información, vea [componentes de conectividad de RTC en Skype para Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7ab2f-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="7ab2f-112">Los servidores perimetrales, lo que permite que el uso de las características de Enterprise Voice por los usuarios cuando se encuentran fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="7ab2f-113">El servicio de servidor perimetral de acceso proporciona la señalización SIP para las llamadas de Skype para usuarios profesionales que están fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="7ab2f-114">El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="7ab2f-115">Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="7ab2f-p104">El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="7ab2f-118">Además, algunos componentes de Enterprise Voice se ejecutan en servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="7ab2f-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="7ab2f-119">Para obtener información detallada acerca de estos componentes, vea [componentes de Front-End Server VoIP para Skype para Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="7ab2f-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

