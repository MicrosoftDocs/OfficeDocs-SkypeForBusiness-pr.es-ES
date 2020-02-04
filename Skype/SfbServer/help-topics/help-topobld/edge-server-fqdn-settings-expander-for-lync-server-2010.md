---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en configuración externa, configure lo siguiente:'
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684763"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b61e1-103">Expansor de configuración FQDN de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b61e1-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b61e1-104">Para definir las propiedades en **configuración externa**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b61e1-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="b61e1-105">Seleccione las casillas de verificación **Habilitar FQDN e dirección IP para las conferencias web y a/V** si desea definir distintas direcciones IP y FQDN de grupo para conferencias web y audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="b61e1-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b61e1-106">Si decide no activar la casilla de verificación de direcciones FQDN e IP separadas, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b61e1-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="b61e1-107">El único nombre de dominio completo que debe configurarse es el FQDN asociado con el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="b61e1-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="b61e1-108">Active la casilla de verificación el **servicio de borde a/v es NAT habilitado** si quiere que el servicio perimetral a/v use una configuración y una dirección IP de traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="b61e1-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="b61e1-109">Para los servicios perimetrales habilitados, escriba un **FQDN de grupo** y un puerto en **puertos**</span><span class="sxs-lookup"><span data-stu-id="b61e1-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="b61e1-110">Defina el FQDN del grupo de **servicio perimetral de Access** y un puerto que identifique de forma única el servicio.</span><span class="sxs-lookup"><span data-stu-id="b61e1-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b61e1-111">Defina el FQDN del grupo de **servicios perimetrales de conferencia web** (si habilitar la dirección IP y el FQDN separados para conferencias web, y a/V no está seleccionada) y un puerto que identifique de manera única el servicio.</span><span class="sxs-lookup"><span data-stu-id="b61e1-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b61e1-112">Defina el FQDN del grupo de **servicios perimetrales a/V** (si habilitar el FQDN y la dirección IP separados para las conferencias web y no se selecciona a/V) y un puerto que identifique de forma única el servicio.</span><span class="sxs-lookup"><span data-stu-id="b61e1-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="b61e1-113">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b61e1-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b61e1-114">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b61e1-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b61e1-115">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="b61e1-115">**Help** Displays this help screen.</span></span>
  

