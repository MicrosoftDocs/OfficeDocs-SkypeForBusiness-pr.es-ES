---
title: Director (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.
ms.openlocfilehash: 0c76fb5290715bb394b4c84ffadad3a2e9dd74db
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801100"
---
# <a name="director-planning-tool"></a><span data-ttu-id="0f732-103">Director (Herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="0f732-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="0f732-104">Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="0f732-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="0f732-105">Este rol es opcional, elegiría implementar un director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f732-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="0f732-106">Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director.</span><span class="sxs-lookup"><span data-stu-id="0f732-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="0f732-107">En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="0f732-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="0f732-108">Cuando se usa un director para autenticar usuarios externos, libera a los servidores del grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="0f732-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="0f732-109">También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f732-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="0f732-110">Si la red está saturada con tráfico externo no válido, este tráfico llega al director.</span><span class="sxs-lookup"><span data-stu-id="0f732-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="0f732-111">Si implementa varios grupos de servidores front-end en un sitio central, si agrega un director a ese sitio, puede simplificar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0f732-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="0f732-112">En este escenario, todas las solicitudes van primero al director, que las enruta al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="0f732-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

