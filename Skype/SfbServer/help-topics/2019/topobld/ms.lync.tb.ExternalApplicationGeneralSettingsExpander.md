---
title: Expansor de configuración General de aplicación externa
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 4104b9cf22a3db36afd159c0b7d9812142112ece
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="14162-103">Expansor de configuración General de aplicación externa</span><span class="sxs-lookup"><span data-stu-id="14162-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="14162-104">Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="14162-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="14162-105">Hay dos secciones que se pueden modificar:</span><span class="sxs-lookup"><span data-stu-id="14162-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="14162-106">Configuración general</span><span class="sxs-lookup"><span data-stu-id="14162-106">General settings</span></span>
    
> <span data-ttu-id="14162-107">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="14162-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="14162-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="14162-108">General Settings</span></span>

<span data-ttu-id="14162-109">Puede modificar el nombre de dominio completo (FQDN) actual para el grupo de servidores de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="14162-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="14162-110">Edite el nombre del FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="14162-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="14162-111">Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes que los clientes o servidores pueden conectar con el nuevo nombre de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="14162-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="14162-112">Si necesita tener la replicación de datos de configuración para este grupo de servidores, seleccione **Habilitar la replicación de datos de configuración para este grupo de servidores** .</span><span class="sxs-lookup"><span data-stu-id="14162-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="14162-113">Desactive la casilla de verificación si no desea replicar los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="14162-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="14162-114">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="14162-114">Next Hop Settings</span></span>

<span data-ttu-id="14162-115">Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza mediante la selección de la definido grupo de servidores Front-End de Enterprise Edition o Standard Edition front-end de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="14162-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="14162-116">Un Director o el Director de grupo de servidores no es una selección válida para una aplicación de confianza próximo salto del servidor y no aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="14162-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  
## 

<span data-ttu-id="14162-117">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="14162-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="14162-118">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="14162-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

