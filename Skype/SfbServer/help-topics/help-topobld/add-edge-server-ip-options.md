---
title: Agregar opciones de IP del servidor de borde
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: '2013 de Microsoft Lync Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz del servidor de borde y fondo de borde. Para ello, siga este procedimiento:'
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="2c4aa-104">Agregar opciones de IP del servidor de borde</span><span class="sxs-lookup"><span data-stu-id="2c4aa-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="2c4aa-105">2013 de Microsoft Lync Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz del servidor de borde y fondo de borde.</span><span class="sxs-lookup"><span data-stu-id="2c4aa-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="2c4aa-106">Para ello, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="2c4aa-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="2c4aa-107">**Habilitar IPv4 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz interna del grupo de borde</span><span class="sxs-lookup"><span data-stu-id="2c4aa-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="2c4aa-108">**Habilitar IPv6 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz interna del grupo de borde</span><span class="sxs-lookup"><span data-stu-id="2c4aa-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="2c4aa-109">**Habilitar IPv4 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz externa del grupo de borde</span><span class="sxs-lookup"><span data-stu-id="2c4aa-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="2c4aa-110">**Habilitar IPv6 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz externa del grupo de borde</span><span class="sxs-lookup"><span data-stu-id="2c4aa-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="2c4aa-111">También puede configurar el servidor perimetral o un grupo de servidores de borde para utilizar una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="2c4aa-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="2c4aa-112">Para ello, activando la casilla de verificación **NAT traduce la dirección IP externa de este grupo de borde**.</span><span class="sxs-lookup"><span data-stu-id="2c4aa-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="2c4aa-113">Compatibilidad con NAT.</span><span class="sxs-lookup"><span data-stu-id="2c4aa-113">NAT support.</span></span> <span data-ttu-id="2c4aa-114">Traducción de direcciones de red (NAT) no se admite cuando se utiliza hardware equilibrio de carga, por lo que no se seleccione la opción NAT si va a implementar una agrupación de servidor perimetral con equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2c4aa-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

