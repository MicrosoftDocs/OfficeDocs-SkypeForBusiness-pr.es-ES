---
title: Expansor de configuración FQDN de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en Configuración externa, configure lo siguiente:'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807100"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9761b-103">Expansor de configuración FQDN de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9761b-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="9761b-104">Para definir las propiedades en **Configuración externa**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9761b-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="9761b-105">Marque la casilla de verificación **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** si desea definir direcciones IP y FQDN del grupo de servidores diferentes para conferencia web y audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="9761b-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9761b-106">Si decide no activar la casilla para direcciones IP y FQDN independientes, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="9761b-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="9761b-107">El único nombre de dominio completo que se va a configurar es el FQDN asociado al servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="9761b-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="9761b-108">Active la casilla de verificación Servicio perimetral **A/V** con NAT habilitada si desea que el servicio perimetral A/V use una configuración y una dirección IP de traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="9761b-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="9761b-109">Para los servicios perimetrales habilitados, escriba un **FQDN de grupo de servidores** y un puerto en **Puertos**</span><span class="sxs-lookup"><span data-stu-id="9761b-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="9761b-110">Defina el FQDN de grupo de servidores del **Servicio perimetral de acceso** y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="9761b-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="9761b-111">Defina el FQDN de grupo de servidores del **Servicio perimetral de conferencia web** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="9761b-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="9761b-112">Defina el FQDN de grupo de servidores del **Servicio perimetral A/V** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="9761b-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="9761b-113">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9761b-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="9761b-114">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9761b-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="9761b-115">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="9761b-115">**Help** Displays this help screen.</span></span>
  

