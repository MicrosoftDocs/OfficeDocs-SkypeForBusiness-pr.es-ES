---
title: Configuración de borde servidor FQDN Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir las propiedades de configuración externo, configure lo siguiente:'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b2c0f-103">Configuración de borde servidor FQDN Expander para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b2c0f-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b2c0f-104">Para definir las propiedades de **configuración externo**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2c0f-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="b2c0f-105">Seleccione el **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** casilla de verificación si desea definir diferentes IP y FQDN del grupo de direcciones para audio y vídeo y conferencias por Internet.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2c0f-106">Si decide no seleccionar la casilla de verificación separe las direcciones IP y FQDN, debe proporcionar puertos distintos para cada uno de los tres servicios proporcionados por el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="b2c0f-107">El único nombre de dominio completo que va a configurar es el FQDN asociado con el servicio de servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="b2c0f-108">Seleccione el **A / servicio V perimetral es NAT habilitado** casilla de verificación si desea que el servicio borde V a utilizar una red la dirección de dirección IP de traducción (NAT) y la configuración.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="b2c0f-109">Para los servicios habilitados de borde, escribe un **Pool FQDN** y un puerto en la ficha **puertos**</span><span class="sxs-lookup"><span data-stu-id="b2c0f-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="b2c0f-110">Definir un puerto que identifica de forma única el servicio y el FQDN del grupo de servidores de **servicio de servidor perimetral de acceso** .</span><span class="sxs-lookup"><span data-stu-id="b2c0f-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b2c0f-111">Definir el FQDN del grupo de **servicio perimetral de conferencia Web** (si permiten separar el FQDN y la dirección IP para conferencias por Internet y A / V no está seleccionada) y un puerto que identifica el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="b2c0f-112">Definir la **A / servicio perimetral V** Pool FQDN (si permiten separar el FQDN y la dirección IP para conferencias por Internet y A / V no está seleccionada) y un puerto que identifica el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
 <span data-ttu-id="b2c0f-113">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="b2c0f-114">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="b2c0f-115">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="b2c0f-115">**Help** Displays this help screen.</span></span>
  

