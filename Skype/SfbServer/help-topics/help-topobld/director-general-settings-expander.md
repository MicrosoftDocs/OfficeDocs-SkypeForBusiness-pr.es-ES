---
title: Director General configuración del Ampliador
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para modificar la configuración de un Director existente, se presentan con las siguientes secciones:'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="91d87-103">Director General configuración del Ampliador</span><span class="sxs-lookup"><span data-stu-id="91d87-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="91d87-104">Para modificar la configuración de un Director existente, se presentan con las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="91d87-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="91d87-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="91d87-105">General settings</span></span>
    
- <span data-ttu-id="91d87-106">Servicios web</span><span class="sxs-lookup"><span data-stu-id="91d87-106">Web services</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="91d87-107">Configuración general</span><span class="sxs-lookup"><span data-stu-id="91d87-107">General settings</span></span>

<span data-ttu-id="91d87-108">Nombre de dominio completo (FQDN) del grupo de Director.</span><span class="sxs-lookup"><span data-stu-id="91d87-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="91d87-109">Edite el FQDN del servidor para cambiar el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="91d87-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="91d87-110">Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="91d87-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="91d87-111">En **Asociaciones**, puede editar o especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91d87-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="91d87-112">Recurso compartido de archivos para el grupo de Director que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="91d87-112">File share for the Director pool to use.</span></span> <span data-ttu-id="91d87-113">Seleccione un recurso de archivo existente que ya se ha definido en el generador de topología, o haga clic en **nuevo** para crear una nueva definición de recurso compartido de archivo.</span><span class="sxs-lookup"><span data-stu-id="91d87-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="91d87-114">Supervisión de almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91d87-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="91d87-115">Antes de publicar la nueva topología que se ha definido, el servidor especificado necesitará existir y estar incorporado en el dominio.</span><span class="sxs-lookup"><span data-stu-id="91d87-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="91d87-116">Si ha creado un nuevo recurso compartido de archivo, debe crearse el recurso compartido de archivos en el servidor que usted designe.</span><span class="sxs-lookup"><span data-stu-id="91d87-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="91d87-117">Servicios web</span><span class="sxs-lookup"><span data-stu-id="91d87-117">Web services</span></span>

<span data-ttu-id="91d87-118">Para modificar o especificar opciones adicionales para los servicios Web en el grupo de directores, modificar o especificar la configuración de los servicios de Web interno y los servicios Web externos.</span><span class="sxs-lookup"><span data-stu-id="91d87-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="91d87-119">Para **servicios web de interno** puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91d87-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="91d87-120">Si tiene más de un grupo de servidores Front-End o servidor Front-End los servicios Web externos FQDN debe ser único.</span><span class="sxs-lookup"><span data-stu-id="91d87-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="91d87-121">Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede utilizar **pool01.contoso.com** para otro grupo de servidores Front-End o un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="91d87-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="91d87-122">Si también está implementando directores, externo FQDN definido para cualquier Director de los servicios Web o grupo de directores debe ser única de cualquier otro Director o Director pool, así como cualquier grupo de servidores Front-End o un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="91d87-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="91d87-123">Si decide reemplazar los servicios web interno con un FQDN de definición propia, cada FQDN debe ser único de cualquier otro grupo de servidores frontales, Director o un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="91d87-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="91d87-124">Si selecciona reemplazar FQDN, puede especificar un FQDN diferente para la identidad de servicios de Web interno en el grupo.</span><span class="sxs-lookup"><span data-stu-id="91d87-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="91d87-125">De forma predeterminada, la configuración es el nombre del grupo actual tal como se define para el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="91d87-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="91d87-126">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación.</span><span class="sxs-lookup"><span data-stu-id="91d87-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="91d87-127">La configuración predeterminada del puerto 80 para HTTP y el puerto 443 para HTTPS es la configuración más común y normalmente no es necesario cambiar a menos que tenga requisitos específicos dentro de su organización y el diseño de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="91d87-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="91d87-128">Para los **servicios web externos**, se puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91d87-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="91d87-129">Puede definir el nombre de dominio completo de los servicios Web externos.</span><span class="sxs-lookup"><span data-stu-id="91d87-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="91d87-130">El FQDN especificado aquí se definirá normalmente según los requisitos de la conexión externa, como el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="91d87-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="91d87-131">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiere su implementación.</span><span class="sxs-lookup"><span data-stu-id="91d87-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="91d87-132">La configuración predeterminada del puerto 8080 para HTTP y el puerto 4443 para HTTPS se define inicialmente.</span><span class="sxs-lookup"><span data-stu-id="91d87-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="91d87-133">Puede cambiar estos valores para los puertos de escucha en función de los requisitos de proxy inverso y de red externa.</span><span class="sxs-lookup"><span data-stu-id="91d87-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="91d87-134">Los puertos publicados se establecen en el valor predeterminado es el puerto 80 para HTTP y el puerto 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91d87-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="91d87-135">Estos valores determinan qué puertos del grupo Director o servidor Director escuchará las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="91d87-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="91d87-136">Normalmente, estos no es necesario cambiarlo, a menos que haya conflicto de requisitos de puerto en el grupo.</span><span class="sxs-lookup"><span data-stu-id="91d87-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="91d87-137">Se esperan que puertos publicados internos y externos que utilizan los mismos valores de puerto.</span><span class="sxs-lookup"><span data-stu-id="91d87-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="91d87-138">No es un conflicto.</span><span class="sxs-lookup"><span data-stu-id="91d87-138">This is not a conflict.</span></span>
  

