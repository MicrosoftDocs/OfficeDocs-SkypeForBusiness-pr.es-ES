---
title: Expansor de configuración general de director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de un Director existente, le presentamos las secciones siguientes:'
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822630"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="4e33d-103">Expansor de configuración general de director</span><span class="sxs-lookup"><span data-stu-id="4e33d-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="4e33d-104">Para editar la configuración de un Director existente, le presentamos las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e33d-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="4e33d-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="4e33d-105">General settings</span></span>
    
- <span data-ttu-id="4e33d-106">Servicios web</span><span class="sxs-lookup"><span data-stu-id="4e33d-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="4e33d-107">Configuración general</span><span class="sxs-lookup"><span data-stu-id="4e33d-107">General settings</span></span>

<span data-ttu-id="4e33d-p101">Nombre de dominio completo (FQDN) del grupo de Directores. Edite el FQDN del servidor para cambiar ese valor. Debe tener un registro de host (A) de sistema de nombres de dominio (DNS) que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="4e33d-111">En **Asociaciones** puede editar o especificar los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e33d-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="4e33d-112">El recurso compartido de archivos que debe usar el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="4e33d-112">File share for the Director pool to use.</span></span> <span data-ttu-id="4e33d-113">Seleccione un recurso compartido de archivos existente que ya se haya definido en el Generador de topologías o haga clic en Nuevo **para** crear una nueva definición de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="4e33d-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="4e33d-114">Supervisión del almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e33d-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e33d-p103">Antes de publicar la topología definida recientemente, el servidor que especifique debe existir y se debe unir al dominio. Si crea un nuevo recurso compartido de archivos, debe hacerlo en el servidor que designe.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="4e33d-117">Servicios web</span><span class="sxs-lookup"><span data-stu-id="4e33d-117">Web services</span></span>

<span data-ttu-id="4e33d-118">Para editar o especificar una configuración adicional de los servicios web en el grupo de directores, debe modificar o especificar la configuración de los servicios web internos y externos.</span><span class="sxs-lookup"><span data-stu-id="4e33d-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="4e33d-119">En el caso de los **servicios web internos** puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e33d-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4e33d-120">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="4e33d-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="4e33d-121">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4e33d-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="4e33d-122">Si también implementa directores, el FQDN de servicios web externos definido para cualquier director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4e33d-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="4e33d-123">Si decide invalidar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="4e33d-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="4e33d-p105">Si selecciona FQDN de reemplazo, puede especificar un FQDN distinto para la identidad de los servicios web internos en el grupo. De forma predeterminada, la configuración del nombre de grupo actual la define el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="4e33d-p106">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiera su implementación. La configuración predeterminada de puerto 80 para HTTP y puerto 443 para HTTPS es la más común y generalmente no es necesario cambiarla a menos que tenga su organización o el diseño de la infraestructura le marque unos requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="4e33d-128">En el caso de los **servicios web externos**, puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e33d-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="4e33d-p107">Puede definir el FQDN de los servicios web externos. El FQDN que se especifica aquí generalmente quedará definido por los requisitos externos de conexión, como el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="4e33d-p108">Puede especificar los puertos de escucha y publicados para HTTP y HTTPS que requiera su implementación. Inicialmente y de forma predeterminada la configuración es el puerto 8080 para HTTP y el puerto 4443 para HTTPS. Cambie esta configuración para los puertos de escucha en función de los requisitos del proxy inverso y de la red externa. Los puertos publicados se establecen de forma predeterminada en puerto 80 para HTTP y puerto 443 para HTTPS. Estos valores determinan qué puertos escucharán el grupo de directores o el servidor de directores para las solicitudes de entrada. Generalmente no es necesario cambiarlos, a menos que exista un conflicto de requisitos de puerto en el grupo. Es de esperar que haya puertos publicados internos y externos que usen los mismos valores de puerto. Esto no es un conflicto.</span><span class="sxs-lookup"><span data-stu-id="4e33d-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

