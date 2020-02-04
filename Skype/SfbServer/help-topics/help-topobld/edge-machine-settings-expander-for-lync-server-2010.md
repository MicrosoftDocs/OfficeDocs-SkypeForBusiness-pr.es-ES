---
title: Expansor de configuración de equipo perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos de servidor perimetral como un solo servidor perimetral o como equipos miembro en un grupo Edge, configure las opciones de configuración de nombre de servidor y dirección IP:'
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684783"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="246c9-103">Expansor de configuración de equipo perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="246c9-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="246c9-104">Para editar las propiedades de los equipos de servidor perimetral como un solo servidor perimetral o como equipos miembro en un grupo Edge, configure las opciones de **configuración de nombre de servidor y dirección IP** :</span><span class="sxs-lookup"><span data-stu-id="246c9-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="246c9-105">**Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="246c9-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="246c9-106">**Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red (NIC) interna de este equipo.</span><span class="sxs-lookup"><span data-stu-id="246c9-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="246c9-107">Configure la **dirección IPv4 externa** del **servicio perimetral de acceso** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="246c9-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="246c9-108">Si seleccionó usar una única dirección IP para la configuración del servidor perimetral, solo podrá editar la dirección IPv4 externa para el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="246c9-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="246c9-109">Los otros servicios perimetrales compartirán la misma dirección IPv4 que el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="246c9-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="246c9-110">Si está disponible para editar, configure la **dirección IPv4 externa** del **servicio de conferencias web** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="246c9-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="246c9-111">Si está disponible para editar, configure el **servicio perimetral a/V** **dirección IPv4 externa** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="246c9-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="246c9-112">Si está disponible para editar, configure la **dirección IPv4 pública habilitada para NAT** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="246c9-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="246c9-113">La propiedad de configuración de una **dirección IPv4 pública habilitada para NAT** solo estará disponible para su edición si elige proporcionar la traducción de direcciones de red (NAT) para el servicio perimetral de a/V</span><span class="sxs-lookup"><span data-stu-id="246c9-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="246c9-114">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="246c9-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="246c9-115">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="246c9-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="246c9-116">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="246c9-116">**Help** Displays this help screen.</span></span>
  

