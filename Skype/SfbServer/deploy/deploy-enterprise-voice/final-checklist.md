---
title: Llame a la lista de comprobación de final de implementación de control de admisión de Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de comprobación final para la implementación de Control de admisión llamar (CAC) en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="cf8c5-103">Implementar el servicio de control de admisión de llamadas: lista de comprobación final para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cf8c5-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cf8c5-104">Lista de comprobación final para la implementación de Control de admisión llamar (CAC) en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="cf8c5-105">Use la siguiente lista de comprobación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el Servicio de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="cf8c5-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="cf8c5-106">Si uno o más servidores perimetrales están distribuidos, cada dirección IP de interfaz externa debe agregarse a la lista de subredes en la configuración de red, con una máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="cf8c5-107">También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf8c5-108">Servidores de borde no tienen que implementar CAC.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="cf8c5-109">Asegúrese de que está habilitado CAC, como especificado en [Habilitar control de admisión de llamada en Skype para Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="cf8c5-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="cf8c5-110">Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="cf8c5-111">Esto puede hacerse mediante el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="cf8c5-112">Si se genera una advertencia cuando se publica, *no* omitirlo.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="cf8c5-113">Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="cf8c5-114">También es esencial que todas las subredes estén asociados a un sitio de red, como se explica en [implementar regiones de red, sitios y subredes en Skype para negocios 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="cf8c5-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="cf8c5-115">Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

