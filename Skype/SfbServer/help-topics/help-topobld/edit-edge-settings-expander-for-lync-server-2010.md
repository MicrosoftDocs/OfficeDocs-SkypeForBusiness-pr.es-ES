---
title: Editar expansor de configuración perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Modificar la configuración para el servidor perimetral o grupo de servidores perimetrales mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203133"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="84a84-103">Editar expansor de configuración perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="84a84-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="84a84-104">Modificar la configuración para el servidor perimetral o grupo de servidores perimetrales mediante la configuración de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="84a84-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="84a84-105">**General**</span><span class="sxs-lookup"><span data-stu-id="84a84-105">**General**</span></span>
  
- <span data-ttu-id="84a84-106">**FQDN del grupo de servidores interno**: el nombre de dominio completo del grupo de servidores interno es la identidad del servidor perimetral o grupo de servidores perimetrales como se define en el registro de host (A o AAAA para IPv6) (DNS) del sistema de nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="84a84-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="84a84-107">Seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** si desea habilitar el servidor perimetral o grupo de servidores perimetrales para la federación con otros socios de protocolo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="84a84-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="84a84-108">Sólo se puede definir un servidor perimetral o grupo de servidores perimetrales activamente para la federación.</span><span class="sxs-lookup"><span data-stu-id="84a84-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="84a84-109">La configuración que se muestra en la captura de pantalla asociada indica que otro servidor perimetral o grupo perimetral ya está configurado para la federación.</span><span class="sxs-lookup"><span data-stu-id="84a84-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="84a84-110">El registro SRV de DNS externo para la federación (_sipfederationtls._tcp.\< nombre de dominio externo\>) seleccione el servidor perimetral o grupo de servidores perimetrales para la federación.</span><span class="sxs-lookup"><span data-stu-id="84a84-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="84a84-111">El **Puerto de replicación de configuración interna (HTTPS)**, de forma predeterminada en el puerto TCP 4443, es el puerto que el equipo local (es decir, local a los servidores perimetrales) copia del almacén de Administración Central se replica a través de.</span><span class="sxs-lookup"><span data-stu-id="84a84-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="84a84-112">La copia local del almacén de Administración Central se encuentra en la base de datos **RTCLOCAL** en SQL Server en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="84a84-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="84a84-113">La replicación es unidireccional, iniciada desde el servidor de Administración Central (o el grupo de servidores Front-End o de servidor Front-End que contiene el rol de servidor de Administración Central) a los servidores perimetrales y es un puerto de la interfaz interna.</span><span class="sxs-lookup"><span data-stu-id="84a84-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="84a84-114">**Selección de próximo salto**</span><span class="sxs-lookup"><span data-stu-id="84a84-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="84a84-115">Seleccione el **grupo del próximo salto**para la lista.</span><span class="sxs-lookup"><span data-stu-id="84a84-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="84a84-116">Definir Director, grupo de servidores Director, servidor Front-End o Front-End del grupo de servidores para adoptar esta función.</span><span class="sxs-lookup"><span data-stu-id="84a84-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="84a84-117">El próximo salto es el servidor o grupo de servidores que se aceptará los mensajes SIP entrantes desde el servidor perimetral o interfaz interna del grupo de servidores perimetrales y envío saliente SIP a la interfaz interna perimetral.</span><span class="sxs-lookup"><span data-stu-id="84a84-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84a84-118">El Director es un rol opcional y si decide no implementar directores, servidores de Front-End (un solo equipo o grupo de servidores) asumirá el rol de Director.</span><span class="sxs-lookup"><span data-stu-id="84a84-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="84a84-119">**Configuración de externo**</span><span class="sxs-lookup"><span data-stu-id="84a84-119">**External settings**</span></span>
  
<span data-ttu-id="84a84-120">En esta sección de las propiedades permite editar las propiedades de la configuración externa del servidor perimetral o grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="84a84-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="84a84-121">Pueden modificarse las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="84a84-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="84a84-122">Seleccione el **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** nombres de casilla de verificación si desea asignar distintas direcciones IP y nombre de dominio completo para cada servicio del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="84a84-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84a84-123">Si opta por no active la casilla de verificación, debe utilizar puertos distintos para cada servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="84a84-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="84a84-124">Cada servicio perimetral compartirá el FQDN definido para el servicio de servidor perimetral de acceso y, por lo tanto, usará la misma dirección IP.</span><span class="sxs-lookup"><span data-stu-id="84a84-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="84a84-125">Cada servicio perimetral debe identificarse de forma exclusiva por una dirección IP distinta y mismo puerto, o bien la misma dirección IP y los valores de puerto únicos.</span><span class="sxs-lookup"><span data-stu-id="84a84-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="84a84-126">Seleccione **A / servicio perimetral A/v está habilitado para NAT** si desea configurar el servicio perimetral A/v para usar una dirección privada u otra dirección que va a estar oculta detrás de un dispositivo (NAT) de la traducción de direcciones de red.</span><span class="sxs-lookup"><span data-stu-id="84a84-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="84a84-127">Para editar el **servicio perimetral de acceso**, definir el **FQDN del grupo de servidores** para el servicio de servidor perimetral de acceso tal como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="84a84-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="84a84-128">Para editar el **servicio perimetral de conferencia Web**, definir un **FQDN del grupo de servidores** para el servicio perimetral de conferencia Web como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="84a84-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="84a84-129">Para editar la **A / servicio perimetral A/v**, definir un **FQDN del grupo de servidores** para el servicio perimetral A/v tal como se define en DNS por parte de host (A y AAAA si se utiliza IPv6) registros y un valor de puerto</span><span class="sxs-lookup"><span data-stu-id="84a84-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="84a84-130">Si ha seleccionado la **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** casilla de verificación, el servicio de servidor perimetral de acceso FQDN del grupo estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="84a84-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="84a84-131">Asignar puertos distintos para cada uno de los tres servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="84a84-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="84a84-132">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="84a84-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="84a84-133">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="84a84-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="84a84-134">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="84a84-134">**Help** Displays this help screen.</span></span>
  

