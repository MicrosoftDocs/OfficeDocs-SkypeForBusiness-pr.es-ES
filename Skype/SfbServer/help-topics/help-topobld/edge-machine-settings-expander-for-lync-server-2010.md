---
title: Expansor de configuración de equipo perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, configurar opciones de configuración de dirección IP y de nombre de servidor:'
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891543"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3698c-103">Expansor de configuración de equipo perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3698c-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="3698c-104">Para editar las propiedades de los equipos de servidor perimetral como un único servidor perimetral o como equipos miembros de un grupo de servidores perimetrales, configure la configuración de **nombre del servidor y la configuración de dirección IP** :</span><span class="sxs-lookup"><span data-stu-id="3698c-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="3698c-105">**Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="3698c-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="3698c-106">**Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) para este equipo.</span><span class="sxs-lookup"><span data-stu-id="3698c-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="3698c-107">Configurar el **servicio de servidor perimetral de acceso** **dirección IPv4 externa** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="3698c-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3698c-108">Si seleccionó para utilizar una sola dirección IP para la configuración del servidor perimetral, sólo podrá editar la dirección IPv4 externa para el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="3698c-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="3698c-109">Los otros servicios perimetrales comparten la misma dirección IPv4 como el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="3698c-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="3698c-110">Si está disponible para edición, configure el **servicio de conferencia Web** **dirección IPv4 externa** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="3698c-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="3698c-111">Si está disponible para edición, configure la **A / servicio perimetral A/v** **dirección IPv4 externa** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="3698c-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="3698c-112">Si está disponible para edición, configure la **dirección IPv4 habilitada para NAT** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="3698c-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3698c-113">La propiedad de configuración de **dirección IPv4 habilitada para NAT** sólo estará disponible para edición si opta por proporcionar la traducción de direcciones de red (NAT) en lugar de A / servicio perimetral A/v</span><span class="sxs-lookup"><span data-stu-id="3698c-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="3698c-114">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3698c-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3698c-115">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3698c-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3698c-116">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="3698c-116">**Help** Displays this help screen.</span></span>
  

