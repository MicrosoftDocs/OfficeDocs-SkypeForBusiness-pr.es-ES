---
title: Borde máquina configuración Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de equipos servidor perimetral como un único servidor perimetral o equipos miembros de un grupo de borde, configurar el nombre del servidor y la configuración de dirección IP:'
ms.openlocfilehash: d1bc35683ff70e1666a46d478aa97b3bcc3d5593
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="be2b1-103">Borde máquina configuración Expander para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="be2b1-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="be2b1-104">Para editar las propiedades de equipos servidor perimetral como un único servidor perimetral o equipos miembros de un grupo de borde, configurar **nombre del servidor** y la configuración de dirección IP:</span><span class="sxs-lookup"><span data-stu-id="be2b1-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="be2b1-105">**Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="be2b1-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="be2b1-106">**Dirección IPv4 interno**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) para este equipo.</span><span class="sxs-lookup"><span data-stu-id="be2b1-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="be2b1-107">Configurar el **servicio acceso perimetral de** **dirección IPv4 externos** asociados a este equipo</span><span class="sxs-lookup"><span data-stu-id="be2b1-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="be2b1-108">Si ha seleccionado utilizar una única dirección IP para la configuración del servidor de borde, sólo podrá modificar la dirección IPv4 externa para el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="be2b1-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="be2b1-109">Los demás servicios de borde compartirán la misma dirección IPv4 como el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="be2b1-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="be2b1-110">Si está disponible para editar, configurar el **servicio de conferencias Web** **dirección IPv4 externos** asociados a este equipo</span><span class="sxs-lookup"><span data-stu-id="be2b1-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="be2b1-111">Si disponible para editar, configurar el **A / servicio perimetral V** **dirección IPv4 externos** asociados a este equipo</span><span class="sxs-lookup"><span data-stu-id="be2b1-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="be2b1-112">Si está disponible para editar, configure la **dirección IPv4 pública habilitado para NAT** asociada con este equipo.</span><span class="sxs-lookup"><span data-stu-id="be2b1-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="be2b1-113">Sólo estará disponible para modificar si opta por proporcionar la traducción de direcciones de red (NAT) en lugar de A la propiedad de configuración de **dirección IPv4 pública habilitado para NAT** / servicio perimetral V</span><span class="sxs-lookup"><span data-stu-id="be2b1-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
 <span data-ttu-id="be2b1-114">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="be2b1-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="be2b1-115">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="be2b1-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="be2b1-116">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="be2b1-116">**Help** Displays this help screen.</span></span>
  

