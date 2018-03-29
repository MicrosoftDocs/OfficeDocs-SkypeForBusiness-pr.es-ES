---
title: Ampliador de configuración General de aplicación externo
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
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="f78f7-103">Ampliador de configuración General de aplicación externo</span><span class="sxs-lookup"><span data-stu-id="f78f7-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="f78f7-104">Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f78f7-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="f78f7-105">Hay dos secciones que se pueden modificar:</span><span class="sxs-lookup"><span data-stu-id="f78f7-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="f78f7-106">Configuración general</span><span class="sxs-lookup"><span data-stu-id="f78f7-106">General settings</span></span>
    
> <span data-ttu-id="f78f7-107">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="f78f7-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="f78f7-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="f78f7-108">General Settings</span></span>

<span data-ttu-id="f78f7-109">Puede modificar el nombre de dominio completo (FQDN) actual para el grupo de servidor de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="f78f7-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="f78f7-110">Edite el nombre del FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="f78f7-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="f78f7-111">Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes que los clientes o servidores pueden conectarse al nuevo nombre de grupo.</span><span class="sxs-lookup"><span data-stu-id="f78f7-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="f78f7-112">Seleccione **Habilitar la replicación de datos de configuración a este grupo** si es necesario tener la replicación de datos de configuración para este grupo.</span><span class="sxs-lookup"><span data-stu-id="f78f7-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="f78f7-113">Desactive la casilla de verificación si no desea replicar los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="f78f7-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="f78f7-114">Configuración de salto siguiente</span><span class="sxs-lookup"><span data-stu-id="f78f7-114">Next Hop Settings</span></span>

<span data-ttu-id="f78f7-115">Puede especificar el servidor del próximo salto del grupo de aplicaciones de confianza servidor seleccionando el servidor Front End un servidor Standard Edition o Enterprise Edition Front-End grupo definido en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f78f7-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="f78f7-116">Un Director o Director de grupo no es una selección válida para un salto siguiente del servidor de aplicaciones de confianza y no aparecerá en la lista.</span><span class="sxs-lookup"><span data-stu-id="f78f7-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  
## 

<span data-ttu-id="f78f7-117">Haga clic en **Aceptar** para aceptar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f78f7-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="f78f7-118">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f78f7-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

