---
title: Lista de comprobación final de implementación de control de admisión de llamadas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830840"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="b7205-103">Implementación del control de admisión de llamadas: lista de comprobación final para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b7205-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="b7205-104">Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b7205-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b7205-105">Use la siguiente lista de comprobación para comprobar que ha completado todas las tareas de configuración necesarias para implementar el Control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="b7205-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="b7205-p101">Si implementa uno o más servidores perimetrales, debe agregar cada dirección IP de interfaz externa a la lista de subredes de los parámetros de configuración de red, con una máscara de bits de 32. También debe asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="b7205-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7205-108">Los servidores perimetrales no son necesarios para implementar el CAC.</span><span class="sxs-lookup"><span data-stu-id="b7205-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="b7205-109">Asegúrese de que el CAC está habilitado, como se especifica en Habilitar el control de admisión de [llamadas en Skype Empresarial Server.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="b7205-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="b7205-110">Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="b7205-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="b7205-111">Esto se puede hacer a través del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="b7205-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="b7205-112">Si se genera una advertencia al publicarla,  *no la*  ignore.</span><span class="sxs-lookup"><span data-stu-id="b7205-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="b7205-113">Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="b7205-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="b7205-114">También es esencial que todas las subredes se asocie a un sitio de red, como se explica en Implementar regiones de red, sitios y subredes [en Skype Empresarial.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="b7205-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="b7205-115">Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="b7205-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

