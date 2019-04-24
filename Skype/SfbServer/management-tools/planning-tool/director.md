---
title: Director (Planning Tool)
ms.reviewer: ''
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
description: Un Director es un servidor que ejecuta Skype para el software de comunicaciones empresariales Server 2015 que puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario.
ms.openlocfilehash: b6cdecd01183f8e249aaf97e6b4e7bbbbfcbe7cd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217274"
---
# <a name="director-planning-tool"></a><span data-ttu-id="ad43a-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="ad43a-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="ad43a-104">Un Director es un servidor que ejecuta Skype para el software de comunicaciones empresariales Server 2015 que puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="ad43a-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="ad43a-105">Este rol es opcional, que decide implementar un Director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad43a-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="ad43a-106">Si habilita el acceso de usuarios externos mediante la implementación de los servidores perimetrales, también debe implementar un Director.</span><span class="sxs-lookup"><span data-stu-id="ad43a-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="ad43a-107">En este escenario, el Director autentica a los usuarios externos y, a continuación, pasa el tráfico de sesión en los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="ad43a-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="ad43a-108">Cuando se usa un Director para autenticar a los usuarios externos, se liberan los servidores del grupo de servidores Front-End de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad43a-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="ad43a-109">También ayuda a aislar los grupos de Front-End internos de tráfico malintencionado como ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="ad43a-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="ad43a-110">Si la red se desborda con el tráfico externo no válido en este tipo de ataque, este tráfico termina en el Director.</span><span class="sxs-lookup"><span data-stu-id="ad43a-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="ad43a-111">Si implementa varios grupos de servidores Front-End en un sitio central, mediante la adición de un Director para ese sitio puede optimizar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad43a-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="ad43a-112">En este escenario, todas las solicitudes van primeros al Director, que enruta al grupo de servidores Front-End correcto.</span><span class="sxs-lookup"><span data-stu-id="ad43a-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

