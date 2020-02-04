---
title: Editar expansor de configuración perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Para editar la configuración del servidor perimetral o del grupo Edge, configure las siguientes propiedades:'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697385"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1b313-103">Editar expansor de configuración perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b313-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="1b313-104">Para editar la configuración del servidor perimetral o del grupo Edge, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1b313-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="1b313-105">**General**</span><span class="sxs-lookup"><span data-stu-id="1b313-105">**General**</span></span>
  
- <span data-ttu-id="1b313-106">**FQDN del grupo interno**: el nombre de dominio completo del grupo interno es la identidad del servidor perimetral o del grupo de servidores perimetrales según se define en el registro del sistema de nombres de dominio (DNS) (a o AAAA para IPv6).</span><span class="sxs-lookup"><span data-stu-id="1b313-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="1b313-107">Seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)** si desea habilitar el servidor perimetral o el grupo perimetral para la Federación con otros socios del Protocolo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1b313-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b313-108">Solo puede definir un servidor perimetral o un grupo perimetral de forma activa para la Federación.</span><span class="sxs-lookup"><span data-stu-id="1b313-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="1b313-109">La configuración que se muestra en la captura de pantalla asociada indica que ya está configurado otro servidor perimetral o un grupo perimetral para la Federación.</span><span class="sxs-lookup"><span data-stu-id="1b313-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="1b313-110">El registro SRV de DNS externo para la Federación (_sipfederationtls.\< _tcp. nombre\>de dominio externo) apuntará al servidor perimetral o al grupo perimetral para la Federación.</span><span class="sxs-lookup"><span data-stu-id="1b313-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="1b313-111">El **Puerto de replicación de configuración interna (https)**, de forma predeterminada en el puerto TCP 4443, es el puerto por el que se replica la copia local (es decir, local de los servidores perimetrales) del almacén central de administración.</span><span class="sxs-lookup"><span data-stu-id="1b313-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="1b313-112">La copia local del almacén de administración central está en la base de datos **RTCLOCAL** en SQL Server en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="1b313-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="1b313-113">La replicación es unidireccional, iniciada desde el servidor de administración central (o, el servidor front-end o el grupo de servidores front-end que tiene el rol de servidor de administración central) en los servidores perimetrales y es un puerto de interfaz interna.</span><span class="sxs-lookup"><span data-stu-id="1b313-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="1b313-114">**Selección del próximo salto**</span><span class="sxs-lookup"><span data-stu-id="1b313-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="1b313-115">Seleccione la lista de su **grupo de próximos saltos**.</span><span class="sxs-lookup"><span data-stu-id="1b313-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="1b313-116">Defina un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end para asumir este rol.</span><span class="sxs-lookup"><span data-stu-id="1b313-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="1b313-117">El siguiente grupo de saltos es el servidor o grupo de servidores que aceptará mensajes SIP entrantes de la interfaz interna del servidor perimetral o de la agrupación perimetral y enviar SIP saliente a la interfaz interna de Edge.</span><span class="sxs-lookup"><span data-stu-id="1b313-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b313-118">El director es un rol opcional y si decide no implementar directores, los servidores front-end (un equipo o un grupo) asumirán el rol de director.</span><span class="sxs-lookup"><span data-stu-id="1b313-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="1b313-119">**Configuración externa**</span><span class="sxs-lookup"><span data-stu-id="1b313-119">**External settings**</span></span>
  
<span data-ttu-id="1b313-120">Esta sección de las propiedades le permite editar las propiedades de la configuración externa del servidor perimetral o del grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="1b313-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="1b313-121">Pueden modificarse las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1b313-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="1b313-122">Seleccione las casillas de verificación **Habilitar FQDN e dirección IP para las conferencias web y a/V** si desea asignar direcciones IP y nombres de dominio completos para cada servicio de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1b313-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b313-123">Si decide no activar la casilla, debe usar puertos independientes para cada servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="1b313-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="1b313-124">Cada servicio perimetral compartirá el FQDN definido para el servicio perimetral de acceso y, por lo tanto, usará la misma dirección IP.</span><span class="sxs-lookup"><span data-stu-id="1b313-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="1b313-125">Cada servicio perimetral debe estar identificado de forma exclusiva por una dirección IP distinta y el mismo puerto, o por la misma dirección IP y valores de Puerto únicos.</span><span class="sxs-lookup"><span data-stu-id="1b313-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="1b313-126">Seleccione el **servicio de borde a/v es NAT habilitado** si desea configurar el servicio perimetral a/v para que use una dirección privada u otra dirección que se ocultará detrás de un dispositivo de traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="1b313-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="1b313-127">Para editar el **servicio perimetral de acceso**, define el **FQDN del grupo** de servidores para el servicio perimetral de acceso según se define en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto</span><span class="sxs-lookup"><span data-stu-id="1b313-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="1b313-128">Para editar el **servicio perimetral de conferencias web**, define un **FQDN de grupo** para el servicio perimetral de conferencias web definido en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto</span><span class="sxs-lookup"><span data-stu-id="1b313-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="1b313-129">Para editar el **servicio perimetral a/v**, define un **FQDN de grupo** para el servicio perimetral a/v definido en DNS por host (a y AAAA si se usa IPv6) y un valor de Puerto</span><span class="sxs-lookup"><span data-stu-id="1b313-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b313-130">Si ha seleccionado las casillas de verificación **habilitar diferentes FQDN e IP para conferencias web y a/V** , solo el FQDN del grupo de servicio perimetral de acceso estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="1b313-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="1b313-131">Asigne puertos distintos para cada uno de los tres servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="1b313-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="1b313-132">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1b313-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="1b313-133">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1b313-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="1b313-134">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="1b313-134">**Help** Displays this help screen.</span></span>
  

