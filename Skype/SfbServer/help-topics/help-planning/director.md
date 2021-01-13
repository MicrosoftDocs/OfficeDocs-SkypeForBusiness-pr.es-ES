---
title: Director (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810550"
---
# <a name="director-planning-tool"></a><span data-ttu-id="adf6d-103">Director (Herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="adf6d-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="adf6d-104">Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="adf6d-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="adf6d-105">Este rol es opcional, elegiría implementar un director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="adf6d-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="adf6d-106">Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director.</span><span class="sxs-lookup"><span data-stu-id="adf6d-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="adf6d-107">En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="adf6d-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="adf6d-108">Cuando se usa un director para autenticar usuarios externos, libera a los servidores del grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="adf6d-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="adf6d-109">También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="adf6d-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="adf6d-110">Si la red está saturada con tráfico externo no válido, este tráfico llega al director.</span><span class="sxs-lookup"><span data-stu-id="adf6d-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="adf6d-111">Si implementa varios grupos de servidores front-end en un sitio central, si agrega un director a ese sitio, puede simplificar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="adf6d-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="adf6d-112">En este escenario, todas las solicitudes van primero al director, que las enruta al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="adf6d-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

