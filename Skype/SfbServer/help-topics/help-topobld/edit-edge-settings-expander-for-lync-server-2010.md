---
title: Editar borde configuración Expander para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite la configuración para el servidor perimetral o un grupo de servidores de borde mediante la configuración de las propiedades siguientes:'
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d89ed-103">Editar borde configuración Expander para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d89ed-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d89ed-104">Edite la configuración para el servidor perimetral o un grupo de servidores de borde mediante la configuración de las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d89ed-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="d89ed-105">**General**</span><span class="sxs-lookup"><span data-stu-id="d89ed-105">**General**</span></span>
  
- <span data-ttu-id="d89ed-106">**FQDN del grupo interno**: el nombre de dominio completo interno del grupo es la identidad del servidor perimetral o la piscina de borde tal como se define en el registro de host (A o AAAA para IPv6) (DNS) del sistema de nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="d89ed-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="d89ed-107">Si desea habilitar el servidor perimetral o un grupo de servidores de borde para la federación con otros socios de protocolo de inicio de sesión, seleccione **Habilitar la federación para este grupo de borde (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="d89ed-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d89ed-108">Sólo puede definir un servidor perimetral o grupo de servidores de borde activamente para la federación.</span><span class="sxs-lookup"><span data-stu-id="d89ed-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="d89ed-109">La configuración mostrada en la captura de pantalla asociada indica que otro grupo de servidor perimetral o borde ya está configurado para la federación.</span><span class="sxs-lookup"><span data-stu-id="d89ed-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="d89ed-110">El registro SRV de DNS externo para la federación (_sipfederationtls._tcp.\< nombre de dominio externo\>) elija el servidor perimetral o un grupo de servidores de borde para la federación.</span><span class="sxs-lookup"><span data-stu-id="d89ed-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="d89ed-111">El **Puerto interno de replicación de configuración (HTTPS)**, en el puerto TCP 4443, de forma predeterminada es el puerto que el local (es decir, local para los servidores perimetrales) copia del almacén de Administración Central se replica a través de.</span><span class="sxs-lookup"><span data-stu-id="d89ed-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="d89ed-112">La copia local del almacén de Administración Central está en la base de datos **RTCLOCAL** en el SQL Server en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="d89ed-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="d89ed-113">La replicación es unidireccional, iniciadas desde el servidor de Administración Central (o el grupo de servidor Front-End o Front-End que desempeña la función de servidor de Administración Central) para los servidores perimetrales y es un puerto de la interfaz interna.</span><span class="sxs-lookup"><span data-stu-id="d89ed-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
 <span data-ttu-id="d89ed-114">**Selección de salto siguiente**</span><span class="sxs-lookup"><span data-stu-id="d89ed-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="d89ed-115">Seleccione de la lista de su **grupo de salto siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d89ed-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="d89ed-116">Definir Director, grupo de directores, grupo de servidor Front-End o Front-End para asumir esta función.</span><span class="sxs-lookup"><span data-stu-id="d89ed-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="d89ed-117">El siguiente grupo de salto es el servidor o grupo de servidores que se aceptará los mensajes SIP entrantes desde el servidor perimetral o interfaz interna de agrupación de borde y enviar salida SIP a la interfaz interna del borde.</span><span class="sxs-lookup"><span data-stu-id="d89ed-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d89ed-118">El Director es una función opcional y si se decide no implementar directores, los servidores frontales (único equipo o grupo) asumirá la función de Director.</span><span class="sxs-lookup"><span data-stu-id="d89ed-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
 <span data-ttu-id="d89ed-119">**Configuración externa**</span><span class="sxs-lookup"><span data-stu-id="d89ed-119">**External settings**</span></span>
  
<span data-ttu-id="d89ed-120">Esta sección de las propiedades permite editar las propiedades de la configuración del servidor de borde o fondo de borde externa.</span><span class="sxs-lookup"><span data-stu-id="d89ed-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="d89ed-121">Pueden modificarse las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d89ed-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="d89ed-122">Seleccione el **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** nombres de casilla de verificación si desea asignar distintas direcciones IP y nombre de dominio completo para cada servicio del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="d89ed-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d89ed-123">Si decide no activar la casilla de verificación, debe utilizar puertos independientes para cada servicio de borde.</span><span class="sxs-lookup"><span data-stu-id="d89ed-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="d89ed-124">Cada servicio de borde compartirá el FQDN definido para el servicio de servidor perimetral de acceso y, por tanto, se utilizará la misma dirección IP.</span><span class="sxs-lookup"><span data-stu-id="d89ed-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="d89ed-125">Cada servicio de borde debe identificarse de forma exclusiva por una dirección IP distinta y mismo puerto, o bien la misma dirección IP y los valores de puerto único.</span><span class="sxs-lookup"><span data-stu-id="d89ed-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="d89ed-126">Seleccione **A / servicio V perimetral es NAT habilitado** si desea configurar el A / V borde de servicio para utilizar una dirección privada o en otra dirección en la que se oculta detrás de un dispositivo de traducción (NAT) de dirección de red.</span><span class="sxs-lookup"><span data-stu-id="d89ed-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="d89ed-127">Para editar el **servicio acceso perimetral**, definir el **FQDN del grupo de servidores** para el servicio de servidor perimetral de acceso tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="d89ed-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d89ed-128">Para editar el **servicio perimetral de conferencia Web**, definir un **Pool FQDN** para el servicio perimetral de conferencia Web tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="d89ed-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d89ed-129">Para modificar el **A / servicio perimetral V**, definir un **Pool FQDN** en lugar de A / V borde servicio tal como se define en DNS host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="d89ed-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d89ed-130">Si ha seleccionado la **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** casilla de verificación, el servicio de servidor perimetral de acceso Pool FQDN estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="d89ed-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="d89ed-131">Asignar puertos distintos para cada uno de los tres servicios de borde.</span><span class="sxs-lookup"><span data-stu-id="d89ed-131">Assign distinct ports for each of the three Edge services.</span></span>
  
 <span data-ttu-id="d89ed-132">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d89ed-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="d89ed-133">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d89ed-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="d89ed-134">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="d89ed-134">**Help** Displays this help screen.</span></span>
  

