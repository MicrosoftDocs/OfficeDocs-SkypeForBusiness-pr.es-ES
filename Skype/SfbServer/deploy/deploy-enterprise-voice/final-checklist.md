---
title: Lista de comprobación de la implementación de control de admisión de llamada final para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281597"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="fb3e5-103">Implementación de control de admisión de llamadas: lista de comprobación final para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fb3e5-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="fb3e5-104">Lista de comprobación final para implementar el control de admisión de llamadas (CAC) en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="fb3e5-105">Use la siguiente lista de comprobación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el Servicio de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="fb3e5-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="fb3e5-106">Si se implementan uno o varios servidores perimetrales, cada dirección IP de la interfaz externa debe agregarse a la lista de subred en la configuración de red, con una máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="fb3e5-107">También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb3e5-108">No es necesario que los servidores perimetrales implementen CAC.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="fb3e5-109">Asegúrese de que CAC está habilitado, como se especifica en [Habilitar control de admisión de llamadas en Skype empresarial Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb3e5-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="fb3e5-110">Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="fb3e5-111">Esto se puede hacer a través del generador de topología.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="fb3e5-112">Si se genera una advertencia al publicarla, *no* la pase por alto.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="fb3e5-113">Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="fb3e5-114">También es esencial que cada subred esté asociada a un sitio de red, como se explica en [implementar regiones, sitios y subredes de red en Skype empresarial](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="fb3e5-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="fb3e5-115">Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="fb3e5-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

