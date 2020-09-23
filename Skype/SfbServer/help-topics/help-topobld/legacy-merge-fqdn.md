---
title: FQDN de combinación de información heredada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: El FQDN interno del grupo de servidores perimetrales de acceso se usa para diversos escenarios en los que los usuarios internos se comunican con usuarios externos para la Federación, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública. Si en el entorno heredado se había implementado un servidor perimetral con equilibrio de carga, especifique el nombre de dominio completo del equilibrador de carga interno.
ms.openlocfilehash: 7060527c513a5dd469f08f628dd9e5415bde09d4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218461"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="6b97c-104">FQDN de combinación de información heredada</span><span class="sxs-lookup"><span data-stu-id="6b97c-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="6b97c-p102">El **Nombre de dominio completo interno de grupo de servidores perimetrales de acceso** se usa en una serie de situaciones en que los usuarios internos se comunican con usuarios externos para federación, acceso de usuario remoto y conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="6b97c-p102">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity. If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="6b97c-p103">El valor del **Puerto de acceso SIP interno** de **5061**  es el puerto TCP de SIP predeterminado para la comunicación con clientes, servidores y grupos de servidores front-end heredados. Si no se usó el valor predeterminado, actualice el valor de **Puerto de acceso SIP interno:**.</span><span class="sxs-lookup"><span data-stu-id="6b97c-p103">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers. If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

