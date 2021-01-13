---
title: Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825830"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="03324-103">Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="03324-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="03324-104">Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="03324-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="03324-105">Para implementar Telefonía IP empresarial, se requieren los siguientes componentes en la topología.</span><span class="sxs-lookup"><span data-stu-id="03324-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="03324-106">Uno o más servidores de mediación, que traducen señalización y, en algunas configuraciones, medios entre su Skype Empresarial Server interno, una infraestructura de Telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco sip (Protocolo de inicio de sesión).</span><span class="sxs-lookup"><span data-stu-id="03324-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="03324-107">Los servidores de mediación son el componente más fundamental en la implementación Telefonía IP empresarial cliente.</span><span class="sxs-lookup"><span data-stu-id="03324-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="03324-108">Para obtener más información, vea el componente [del servidor de mediación en Skype Empresarial Server.](mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="03324-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="03324-109">Los servidores de mediación pueden instalarse con servidores front-end o instalarse como servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="03324-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="03324-110">Componentes de conectividad RTC, que pueden incluir troncos SIP o puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="03324-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="03324-111">Para obtener más información, vea [componentes de conectividad rtc en Skype Empresarial Server.](pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="03324-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="03324-112">Servidores perimetrales, lo que permite el uso de Telefonía IP empresarial por parte de los usuarios cuando están fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="03324-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="03324-113">El servicio perimetral de acceso proporciona señalización SIP para llamadas de usuarios de Skype Empresarial que están fuera del firewall de su organización.</span><span class="sxs-lookup"><span data-stu-id="03324-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="03324-114">El servicio perimetral A/V permite el cruce de medios de NAT y firewalls.</span><span class="sxs-lookup"><span data-stu-id="03324-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="03324-115">Un llamador que usa un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo depende del servicio perimetral A/V para llamadas individuales y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="03324-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="03324-116">El servicio de autenticación A/V se incluye con el servicio perimetral A/V y proporciona servicios de autenticación para el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="03324-116">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="03324-117">Los usuarios externos que intentan conectarse al servicio perimetral A/V requieren un token de autenticación proporcionado por el servicio de autenticación A/V antes de que puedan pasar las llamadas.</span><span class="sxs-lookup"><span data-stu-id="03324-117">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="03324-118">Además, algunos componentes Telefonía IP empresarial se ejecutan en servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="03324-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="03324-119">Para obtener más información sobre estos componentes, consulte [Componentes VoIP del servidor front-end para Skype Empresarial Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="03324-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

