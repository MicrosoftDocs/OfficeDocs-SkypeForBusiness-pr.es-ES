---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un director es un servidor que ejecuta el software de comunicaciones de Skype empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no aloja ninguna cuenta de usuario.
ms.openlocfilehash: 48b691262dc638faf6f0aa9910a5adac3c1f0e46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685493"
---
# <a name="director-planning-tool"></a><span data-ttu-id="33ce2-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="33ce2-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="33ce2-104">Un director es un servidor que ejecuta el software de comunicaciones de Skype empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no aloja ninguna cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="33ce2-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="33ce2-105">Este rol es opcional y debería elegir implementar un director en los siguientes dos escenarios:</span><span class="sxs-lookup"><span data-stu-id="33ce2-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="33ce2-106">Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director.</span><span class="sxs-lookup"><span data-stu-id="33ce2-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="33ce2-107">En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="33ce2-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="33ce2-108">Cuando se usa un director para autenticar usuarios externos, libera servidores de grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="33ce2-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="33ce2-109">También ayuda a aislar grupos internos de aplicaciones para el usuario contra tráfico malintencionado, como ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="33ce2-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="33ce2-110">Si la red se inunda con tráfico externo no válido en tal ataque, este tráfico finaliza en el director.</span><span class="sxs-lookup"><span data-stu-id="33ce2-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="33ce2-111">Si implementa varios grupos front-end en un sitio central agregando un director a ese sitio, podrá optimizar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="33ce2-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="33ce2-112">En este escenario, todas las solicitudes se dirigen al Director, que a su vez las enruta al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="33ce2-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

