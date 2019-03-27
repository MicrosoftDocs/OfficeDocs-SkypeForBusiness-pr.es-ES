---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en configuración externa, configure lo siguiente:'
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882351"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="bc233-103">Expansor de configuración FQDN de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bc233-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="bc233-104">Para definir las propiedades en **configuración externa**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc233-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="bc233-105">Seleccione el **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** casilla de verificación si desea definir distintos IP y FQDN del grupo de direcciones para conferencias web y audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="bc233-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc233-106">Si opta por no active la casilla de verificación para separe las direcciones IP y FQDN, debe proporcionar los puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="bc233-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="bc233-107">El nombre de dominio completo sólo que consiste en configurar es el FQDN asociado con el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="bc233-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="bc233-108">Seleccione el **A / servicio perimetral A/v está habilitado para NAT** casilla de verificación si desea que el / servicio perimetral A/v para usar una red dirección dirección IP de traducción (NAT) y la configuración.</span><span class="sxs-lookup"><span data-stu-id="bc233-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="bc233-109">Para los Servicios perimetrales habilitados, se escribe un **FQDN del grupo de servidores** y un puerto en **puertos**</span><span class="sxs-lookup"><span data-stu-id="bc233-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="bc233-110">Definir el FQDN del grupo de **servicio de servidor perimetral de acceso** y un puerto que identifica el servicio.</span><span class="sxs-lookup"><span data-stu-id="bc233-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="bc233-111">Definir el FQDN del grupo de servidores de **servicio perimetral de conferencia Web** (si habilitar separar el FQDN y la dirección IP para la conferencia web y / V no está seleccionada) y un puerto que identifica el servicio.</span><span class="sxs-lookup"><span data-stu-id="bc233-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="bc233-112">Definir la **A / servicio perimetral A/v** FQDN del grupo de servidores (si habilitar separar el FQDN y la dirección IP para la conferencia web y / V no está seleccionada) y un puerto que identifica el servicio.</span><span class="sxs-lookup"><span data-stu-id="bc233-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="bc233-113">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bc233-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bc233-114">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bc233-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bc233-115">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="bc233-115">**Help** Displays this help screen.</span></span>
  

