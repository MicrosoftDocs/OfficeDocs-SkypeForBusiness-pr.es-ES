---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de un director existente, se muestran las siguientes secciones:'
ms.openlocfilehash: 92d0026f2bc769f32ca635435cd71866efb75d3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280542"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="c518b-103">Expansor de configuración general de director</span><span class="sxs-lookup"><span data-stu-id="c518b-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="c518b-104">Para editar la configuración de un director existente, se muestran las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="c518b-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="c518b-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="c518b-105">General settings</span></span>
    
- <span data-ttu-id="c518b-106">Servicios web</span><span class="sxs-lookup"><span data-stu-id="c518b-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="c518b-107">Configuración general</span><span class="sxs-lookup"><span data-stu-id="c518b-107">General settings</span></span>

<span data-ttu-id="c518b-108">Nombre de dominio completo (FQDN) del grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="c518b-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="c518b-109">Edite el FQDN del servidor para cambiar el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c518b-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="c518b-110">Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="c518b-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="c518b-111">En **Asociaciones**, puede editar o especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c518b-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="c518b-112">Recurso compartido de archivos para el grupo de directores que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c518b-112">File share for the Director pool to use.</span></span> <span data-ttu-id="c518b-113">Seleccione un recurso compartido de archivos existente que ya se haya definido en el generador de topología o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="c518b-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="c518b-114">Supervisar el almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c518b-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c518b-115">Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.</span><span class="sxs-lookup"><span data-stu-id="c518b-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="c518b-116">Si ha creado un nuevo recurso compartido de archivos, el recurso compartido de archivos debe crearse en el servidor que designe.</span><span class="sxs-lookup"><span data-stu-id="c518b-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="c518b-117">Servicios web</span><span class="sxs-lookup"><span data-stu-id="c518b-117">Web services</span></span>

<span data-ttu-id="c518b-118">Para editar o especificar la configuración adicional de los servicios web en el grupo de directores, modifique o especifique la configuración de los servicios Web internos y los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="c518b-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="c518b-119">Para los **servicios Web internos** , puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c518b-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c518b-120">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="c518b-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="c518b-121">Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c518b-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="c518b-122">Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c518b-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="c518b-123">Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="c518b-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="c518b-124">Si selecciona FQDN de reemplazo, puede especificar un nombre de dominio completo distinto para la identidad de Servicios web internos en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c518b-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="c518b-125">De forma predeterminada, la configuración es el nombre de la sección actual definido para el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="c518b-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="c518b-126">Puede especificar puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación.</span><span class="sxs-lookup"><span data-stu-id="c518b-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="c518b-127">La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS son las opciones más comunes y, por lo general, no es necesario cambiarlos a menos que se cumplan los requisitos específicos dentro del diseño de la infraestructura y la organización.</span><span class="sxs-lookup"><span data-stu-id="c518b-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="c518b-128">Para los **servicios web externos**, puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c518b-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="c518b-129">Puede definir el FQDN de los servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="c518b-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="c518b-130">El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c518b-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="c518b-131">Puede especificar puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación.</span><span class="sxs-lookup"><span data-stu-id="c518b-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="c518b-132">La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c518b-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="c518b-133">Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa.</span><span class="sxs-lookup"><span data-stu-id="c518b-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="c518b-134">Los puertos publicados se establecen en los valores predeterminados del puerto 80 para HTTP y el puerto 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c518b-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="c518b-135">Estos valores determinan qué puertos el grupo de directores o el servidor de directores escuchará las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c518b-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="c518b-136">Normalmente, no es necesario cambiar estas opciones, a menos que haya conflictos de requisitos de puertos en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c518b-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="c518b-137">Se esperan los puertos publicados internos y externos que usan los mismos valores de puerto.</span><span class="sxs-lookup"><span data-stu-id="c518b-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="c518b-138">Este no es un conflicto.</span><span class="sxs-lookup"><span data-stu-id="c518b-138">This is not a conflict.</span></span>
  

