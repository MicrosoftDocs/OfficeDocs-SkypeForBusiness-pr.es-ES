---
title: Director (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director es un servidor que ejecuta Skype para software de comunicaciones de Business Server que se puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario.
ms.openlocfilehash: a1920d11ed354cab3409a9f2a1fd39280ce2d29d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975991"
---
# <a name="director-planning-tool"></a><span data-ttu-id="e29b1-103">Director (herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="e29b1-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="e29b1-104">Un Director es un servidor que ejecuta Skype para software de comunicaciones de Business Server que se puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e29b1-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="e29b1-105">Este rol es opcional, que decide implementar un Director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="e29b1-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="e29b1-106">Si habilita el acceso de usuarios externos mediante la implementación de los servidores perimetrales, también debe implementar un Director.</span><span class="sxs-lookup"><span data-stu-id="e29b1-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="e29b1-107">En este escenario, el Director autentica a los usuarios externos y, a continuación, pasa el tráfico de sesión en los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="e29b1-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="e29b1-108">Cuando se usa un Director para autenticar a los usuarios externos, se liberan los servidores del grupo de servidores Front-End de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="e29b1-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="e29b1-109">También ayuda a aislar los grupos de Front-End internos de tráfico malintencionado como ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e29b1-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="e29b1-110">Si la red se desborda con el tráfico externo no válido en este tipo de ataque, este tráfico termina en el Director.</span><span class="sxs-lookup"><span data-stu-id="e29b1-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="e29b1-111">Si implementa varios grupos de servidores Front-End en un sitio central, mediante la adición de un Director para ese sitio puede optimizar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e29b1-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="e29b1-112">En este escenario, todas las solicitudes van primeros al Director, que enruta al grupo de servidores Front-End correcto.</span><span class="sxs-lookup"><span data-stu-id="e29b1-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

