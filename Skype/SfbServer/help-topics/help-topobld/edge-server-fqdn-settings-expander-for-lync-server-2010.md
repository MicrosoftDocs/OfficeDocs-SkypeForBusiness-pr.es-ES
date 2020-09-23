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
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades en Configuración externa, configure lo siguiente:'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218251"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="17f63-103">Expansor de configuración FQDN de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="17f63-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="17f63-104">Para definir las propiedades en **Configuración externa**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17f63-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="17f63-105">Marque la casilla de verificación **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** si desea definir direcciones IP y FQDN del grupo de servidores diferentes para conferencia web y audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="17f63-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17f63-106">Si opta por no activar la casilla de verificación de direcciones IP y FQDN independientes, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="17f63-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="17f63-107">El único nombre de dominio completo que se va a configurar es el FQDN asociado con el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="17f63-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="17f63-108">Active la casilla de verificación **servicio perimetral a/v con NAT habilitada** si desea que el servicio perimetral a/v use una configuración y una dirección IP de traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="17f63-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="17f63-109">Para los servicios perimetrales habilitados, escriba un **FQDN de grupo de servidores** y un puerto en **Puertos**</span><span class="sxs-lookup"><span data-stu-id="17f63-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="17f63-110">Defina el FQDN de grupo de servidores del **Servicio perimetral de acceso** y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="17f63-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="17f63-111">Defina el FQDN de grupo de servidores del **Servicio perimetral de conferencia web** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="17f63-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="17f63-112">Defina el FQDN de grupo de servidores del **Servicio perimetral A/V** (si no está seleccionada la opción Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V) y un puerto que identifique el servicio de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="17f63-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="17f63-113">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17f63-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="17f63-114">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17f63-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="17f63-115">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="17f63-115">**Help** Displays this help screen.</span></span>
  

