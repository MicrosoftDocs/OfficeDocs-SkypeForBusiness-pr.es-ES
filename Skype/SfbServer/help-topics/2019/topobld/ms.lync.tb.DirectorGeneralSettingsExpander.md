---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de un Director existente, le presentamos las secciones siguientes:'
ms.openlocfilehash: 9d400f44fd3b0ee288de2e3f91eebfb6e90604c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879086"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="04b0d-103">Expansor de configuración general de director</span><span class="sxs-lookup"><span data-stu-id="04b0d-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="04b0d-104">Para editar la configuración de un Director existente, le presentamos las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="04b0d-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="04b0d-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="04b0d-105">General settings</span></span>
    
- <span data-ttu-id="04b0d-106">Servicios web</span><span class="sxs-lookup"><span data-stu-id="04b0d-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="04b0d-107">Configuración general</span><span class="sxs-lookup"><span data-stu-id="04b0d-107">General settings</span></span>

<span data-ttu-id="04b0d-108">Nombre de dominio completo (FQDN) del grupo de servidores Director.</span><span class="sxs-lookup"><span data-stu-id="04b0d-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="04b0d-109">Edite el FQDN del servidor para cambiar el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="04b0d-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="04b0d-110">Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="04b0d-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="04b0d-111">En **Asociaciones**, puede editar o especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04b0d-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="04b0d-112">Recurso compartido de archivos para el grupo de Director debe usar.</span><span class="sxs-lookup"><span data-stu-id="04b0d-112">File share for the Director pool to use.</span></span> <span data-ttu-id="04b0d-113">Seleccione un recurso compartido archivo existente que ya se ha definido en el generador de topología, o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivo.</span><span class="sxs-lookup"><span data-stu-id="04b0d-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="04b0d-114">Supervisión del almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04b0d-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04b0d-115">Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.</span><span class="sxs-lookup"><span data-stu-id="04b0d-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="04b0d-116">Si ha creado un nuevo recurso compartido de archivos, el recurso compartido de archivos debe crearse en el servidor que designe.</span><span class="sxs-lookup"><span data-stu-id="04b0d-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="04b0d-117">Servicios web</span><span class="sxs-lookup"><span data-stu-id="04b0d-117">Web services</span></span>

<span data-ttu-id="04b0d-118">Para editar o especificar opciones adicionales para los servicios Web en el grupo de directores, modificar o especificar la configuración en los servicios Web internos y los servicios Web externos.</span><span class="sxs-lookup"><span data-stu-id="04b0d-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="04b0d-119">Para **servicios web de interno** puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04b0d-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="04b0d-120">Si tiene más de un grupo de servidores Front-End o servidor Front-End los servicios Web externos FQDN debe ser único.</span><span class="sxs-lookup"><span data-stu-id="04b0d-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="04b0d-121">Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores Front-End o servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="04b0d-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="04b0d-122">Si va a implementar también los directores, la externa FQDN definido para cualquier Director de los servicios Web o debe ser único de cualquier otro grupo de directores Director o Director del grupo de servidores, así como cualquier otro grupo de servidores Front-End o un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="04b0d-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="04b0d-123">Si decide reemplazar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores Front-End, Director o un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="04b0d-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="04b0d-124">Si selecciona FQDN de reemplazo, puede especificar un nombre de dominio completo distinto para la identidad de Servicios web internos en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="04b0d-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="04b0d-125">De forma predeterminada, el valor es el nombre del grupo actual, tal como se define para el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="04b0d-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="04b0d-126">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere la implementación.</span><span class="sxs-lookup"><span data-stu-id="04b0d-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="04b0d-127">La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS es la configuración más comunes y normalmente no es necesario que cambiarse a menos que tengan requisitos específicos dentro de la organización y el diseño de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="04b0d-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="04b0d-128">Para los **servicios web externos**, puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04b0d-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="04b0d-129">Puede definir el FQDN de los servicios Web externos.</span><span class="sxs-lookup"><span data-stu-id="04b0d-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="04b0d-130">El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="04b0d-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="04b0d-131">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere la implementación.</span><span class="sxs-lookup"><span data-stu-id="04b0d-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="04b0d-132">La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente.</span><span class="sxs-lookup"><span data-stu-id="04b0d-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="04b0d-133">Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa.</span><span class="sxs-lookup"><span data-stu-id="04b0d-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="04b0d-134">Se establecen los puertos publicados en valor predeterminado de puerto 80 para HTTP y el puerto 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="04b0d-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="04b0d-135">Estos valores determinan qué puertos de servidor de Director o el grupo de directores escuchará para las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="04b0d-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="04b0d-136">Normalmente, estos no es necesario que debe cambiar, a menos que haya conflicto de los requisitos de puerto en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="04b0d-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="04b0d-137">Se esperan puertos publicados internos y externos que usan los mismos valores de puerto.</span><span class="sxs-lookup"><span data-stu-id="04b0d-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="04b0d-138">No es un conflicto.</span><span class="sxs-lookup"><span data-stu-id="04b0d-138">This is not a conflict.</span></span>
  

