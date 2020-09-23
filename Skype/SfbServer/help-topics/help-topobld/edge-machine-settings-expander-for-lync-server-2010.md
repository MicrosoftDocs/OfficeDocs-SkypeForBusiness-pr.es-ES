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
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos del servidor perimetral como un solo servidor perimetral o como equipos miembros en un grupo de servidores perimetrales, configure las opciones de configuración de nombre del servidor y dirección IP:'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218931"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d8b96-103">Expansor de configuración de equipo perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d8b96-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d8b96-104">Para editar las propiedades de los equipos del servidor perimetral como un solo servidor perimetral o como equipos miembros en un grupo de servidores perimetrales, configure las opciones de **configuración de nombre del servidor y dirección IP** :</span><span class="sxs-lookup"><span data-stu-id="d8b96-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="d8b96-105">**Nombre interno o FQDN**: escriba el nombre del equipo tal como aparece en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="d8b96-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="d8b96-106">**Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) de este equipo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="d8b96-107">Configure la **dirección IPv4 externa** del **servicio perimetral de acceso** asociada con este equipo</span><span class="sxs-lookup"><span data-stu-id="d8b96-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8b96-108">Si seleccionó usar una única dirección IP para la configuración del servidor perimetral, solo podrá editar la dirección IPv4 externa para el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="d8b96-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="d8b96-109">Los demás servicios perimetrales compartirán la misma dirección IPv4 que el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="d8b96-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="d8b96-110">Si está disponible para edición, configure la **dirección IPv4 externa** de **servicio de conferencia web** asociada a este equipo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="d8b96-111">Si está disponible para edición, configure la **dirección IPv4 externa** del **servicio perimetral a/V** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="d8b96-112">Si está disponible para edición, configure la **Dirección IPv4 habilitada para NAT** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8b96-113">La propiedad de configuración de la **dirección IPv4 pública habilitada para NAT** solo estará disponible para su edición si elige proporcionar la traducción de direcciones de red (NAT) para el servicio perimetral a/V.</span><span class="sxs-lookup"><span data-stu-id="d8b96-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="d8b96-114">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d8b96-115">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8b96-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d8b96-116">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="d8b96-116">**Help** Displays this help screen.</span></span>
  

