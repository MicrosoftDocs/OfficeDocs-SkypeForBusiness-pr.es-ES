---
title: Director (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director es un servidor que ejecuta Skype para el software de comunicaciones de Business Server 2015 que puede autenticar las solicitudes de usuario, pero no alberga ninguna cuenta de usuario.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a><span data-ttu-id="8fc90-103">Director (herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="8fc90-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="8fc90-104">Un Director es un servidor que ejecuta Skype para el software de comunicaciones de Business Server 2015 que puede autenticar las solicitudes de usuario, pero no alberga ninguna cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="8fc90-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="8fc90-105">Este rol es opcional, que se elige implementar un Director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="8fc90-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="8fc90-106">Si habilita el acceso de los usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un Director.</span><span class="sxs-lookup"><span data-stu-id="8fc90-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="8fc90-107">En este escenario, el Director autentica a los usuarios externos y, a continuación, pasa el tráfico a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="8fc90-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="8fc90-108">Cuando un Director se utiliza para autenticar a los usuarios externos, libera a servidores de grupo de Front-End de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="8fc90-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="8fc90-109">También ayuda a aislar grupos internos de Front-End de tráfico malintencionado, como los ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="8fc90-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="8fc90-110">Si la red está desborda por el tráfico externo no válido en este tipo de ataque, este tráfico se termina en el Director.</span><span class="sxs-lookup"><span data-stu-id="8fc90-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="8fc90-111">Si implementa varios grupos de servidores Front-End en un sitio central, agregando un Director a ese sitio puede agilizar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8fc90-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="8fc90-112">En este escenario, todas las solicitudes van primeras al Director, que enruta al grupo correcto de Front-End.</span><span class="sxs-lookup"><span data-stu-id="8fc90-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

