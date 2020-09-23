---
title: Expansor de configuración general de aplicación externa
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218141"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="a8520-103">Expansor de configuración general de aplicación externa</span><span class="sxs-lookup"><span data-stu-id="a8520-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="a8520-104">Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="a8520-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="a8520-105">Hay dos secciones que puede modificar:</span><span class="sxs-lookup"><span data-stu-id="a8520-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="a8520-106">Configuración general</span><span class="sxs-lookup"><span data-stu-id="a8520-106">General settings</span></span>
> 
> <span data-ttu-id="a8520-107">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="a8520-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="a8520-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="a8520-108">General Settings</span></span>

<span data-ttu-id="a8520-p101">Puede modificar el nombre de dominios completo (FQDN) actual del grupo de servidores de aplicaciones de confianza. Edite el nombre del FQDN del grupo de servidores. Los registros de host (A) del sistema de nombres de dominio debe existir para la nueva entrada para que los clientes o servidores puedan conectarse con el nuevo nombre de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a8520-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="a8520-p102">Seleccione **Habilitar replicación de datos de configuración en este grupo de servidores**si necesita replicar los datos de configuración en este grupo de servidores. Quite la marca de la casilla si no desea replicar los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8520-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="a8520-114">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="a8520-114">Next Hop Settings</span></span>

<span data-ttu-id="a8520-115">Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza seleccionando el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a8520-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="a8520-116">Un servidor o un grupo de servidores Director no son una selección válida para el siguiente salto de un servidor de aplicaciones de confianza; por lo tanto, no figurarán en la lista.</span><span class="sxs-lookup"><span data-stu-id="a8520-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="a8520-117">Haga clic en **Aceptar** para aceptar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a8520-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="a8520-118">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a8520-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

