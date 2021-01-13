---
title: Editar expansor de configuración perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'La configuración del servidor perimetral o del grupo de servidores perimetrales se modifica mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803300"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="59c22-103">Editar expansor de configuración perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59c22-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="59c22-104">La configuración del servidor perimetral o del grupo de servidores perimetrales se modifica mediante la configuración de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="59c22-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="59c22-105">**General**</span><span class="sxs-lookup"><span data-stu-id="59c22-105">**General**</span></span>
  
- <span data-ttu-id="59c22-106">**FQDN** del grupo de servidores interno: el nombre de dominio completo del grupo interno es la identidad del servidor perimetral o del grupo de servidores perimetrales, tal como se define en el registro de host (A o AAAA) del sistema de nombres de dominio (DNS) (A o AAAA para IPv6).</span><span class="sxs-lookup"><span data-stu-id="59c22-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="59c22-107">Seleccione Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** si desea habilitar el servidor perimetral o el grupo de servidores perimetrales para la federación con otros asociados del protocolo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="59c22-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59c22-108">Solo puede definir un servidor perimetral o un grupo de servidores perimetrales activamente para la federación.</span><span class="sxs-lookup"><span data-stu-id="59c22-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="59c22-109">La configuración que se muestra en la captura de pantalla asociada indica que otro servidor perimetral o grupo de servidores perimetrales ya está configurado para la federación.</span><span class="sxs-lookup"><span data-stu-id="59c22-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="59c22-110">El registro SRV de DNS externo para la federación (_sipfederationtls._tcp. ) apuntará al servidor perimetral o al grupo de servidores perimetrales \<external domain name\> para la federación.</span><span class="sxs-lookup"><span data-stu-id="59c22-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="59c22-111">El puerto de replicación de configuración interna **(HTTPS),** de forma predeterminada en el puerto TCP 4443, es el puerto en el que se replica la copia local (es decir, local a los servidores perimetrales) del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="59c22-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="59c22-112">La copia local del almacén de administración central se encuentra en la base de datos **RTCLOCAL** en SQL Server en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="59c22-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="59c22-113">La replicación es un solo sentido, se inicia desde el servidor de administración central (o bien, el servidor front-end o el grupo de servidores front-end que contiene el rol de servidor de administración central) a los servidores perimetrales y es un puerto de interfaz interna.</span><span class="sxs-lookup"><span data-stu-id="59c22-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="59c22-114">**Selección del próximo salto**</span><span class="sxs-lookup"><span data-stu-id="59c22-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="59c22-115">Seleccione para la lista el grupo **de servidores del próximo salto.**</span><span class="sxs-lookup"><span data-stu-id="59c22-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="59c22-116">Defina un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end para asumir este rol.</span><span class="sxs-lookup"><span data-stu-id="59c22-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="59c22-117">El grupo de servidores del próximo salto es el servidor o grupo de servidores que aceptará mensajes SIP entrantes de la interfaz interna del servidor perimetral o del grupo de servidores perimetrales y enviará SIP saliente a la interfaz interna perimetral.</span><span class="sxs-lookup"><span data-stu-id="59c22-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59c22-118">El director es un rol opcional y, si decide no implementar directores, los servidores front-end (un solo equipo o grupo) asumirán el rol de director.</span><span class="sxs-lookup"><span data-stu-id="59c22-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="59c22-119">**Configuración externa**</span><span class="sxs-lookup"><span data-stu-id="59c22-119">**External settings**</span></span>
  
<span data-ttu-id="59c22-120">Esta sección de las propiedades permite editar las propiedades de la configuración externa del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="59c22-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="59c22-121">Pueden modificarse las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="59c22-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="59c22-122">Active la casilla Habilitar direcciones IP y FQDN independientes para conferencias web y **A/V** si desea asignar direcciones IP distintas y nombres de dominio completos a cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="59c22-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59c22-123">Si decide no activar la casilla, debe usar puertos independientes para cada servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="59c22-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="59c22-124">Cada servicio perimetral compartirá el FQDN definido para el servicio perimetral de acceso y, por lo tanto, usará la misma dirección IP.</span><span class="sxs-lookup"><span data-stu-id="59c22-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="59c22-125">Cada servicio perimetral debe identificarse de forma única mediante una dirección IP distinta y el mismo puerto, o bien la misma dirección IP y valores de puerto únicos.</span><span class="sxs-lookup"><span data-stu-id="59c22-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="59c22-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span><span class="sxs-lookup"><span data-stu-id="59c22-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="59c22-127">Para editar el servicio perimetral de **acceso,** defina el **FQDN** del grupo de servidores para el servicio perimetral de acceso como se define en DNS por registros de host (A y AAAA si se usa IPv6) y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="59c22-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="59c22-128">Para editar el servicio perimetral de conferencia **web,** defina un **FQDN** de grupo para el servicio perimetral de conferencia web como se define en DNS por los registros de host (A y AAAA si se usa IPv6) y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="59c22-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="59c22-129">Para editar el servicio perimetral **A/V,** defina un **FQDN** de grupo para el servicio perimetral A/V como se define en DNS por host (A y AAAA si se usa IPv6) y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="59c22-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59c22-130">Si ha seleccionado la casilla Habilitar fqdN y dirección IP independientes para conferencias web y **A/V,** solo el FQDN del grupo de servidores perimetrales de acceso estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="59c22-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="59c22-131">Asigne puertos distintos para cada uno de los tres servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="59c22-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="59c22-132">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="59c22-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="59c22-133">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="59c22-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="59c22-134">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="59c22-134">**Help** Displays this help screen.</span></span>
  

