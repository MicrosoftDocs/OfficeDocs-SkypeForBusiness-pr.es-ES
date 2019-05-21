---
title: Expansor de configuración general de aplicación externa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292783"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="ff3a9-103">Expansor de configuración general de aplicación externa</span><span class="sxs-lookup"><span data-stu-id="ff3a9-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="ff3a9-104">Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="ff3a9-105">Hay dos secciones que puede modificar:</span><span class="sxs-lookup"><span data-stu-id="ff3a9-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="ff3a9-106">Configuración general</span><span class="sxs-lookup"><span data-stu-id="ff3a9-106">General settings</span></span>
> 
> <span data-ttu-id="ff3a9-107">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="ff3a9-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="ff3a9-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="ff3a9-108">General Settings</span></span>

<span data-ttu-id="ff3a9-109">Puede modificar el nombre de dominio completo (FQDN) actual del grupo de servidores de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="ff3a9-110">Edite el nombre del FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="ff3a9-111">Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes de que los clientes o los servidores puedan conectarse al nuevo nombre de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="ff3a9-112">Seleccione **Habilitar la replicación de datos de configuración en este grupo** si necesita tener replicación de datos de configuración en este grupo.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="ff3a9-113">Desactive la casilla si no desea replicar los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="ff3a9-114">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="ff3a9-114">Next Hop Settings</span></span>

<span data-ttu-id="ff3a9-115">Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza seleccionando el grupo de servidores front-end de Enterprise Edition o el servidor front-end Standard Edition en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="ff3a9-116">Un director o grupo de directores no es una selección válida para el próximo salto de un servidor de aplicaciones de confianza y no aparecerá en la lista.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="ff3a9-117">Haga clic en **Aceptar** para aceptar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="ff3a9-118">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="ff3a9-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

