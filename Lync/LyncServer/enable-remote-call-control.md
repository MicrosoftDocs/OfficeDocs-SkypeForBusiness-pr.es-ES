---
title: Habilitar control remoto de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="50bf4-102">Habilitar control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="50bf4-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50bf4-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="50bf4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="50bf4-104">El control remoto de llamadas permite a los usuarios controlar sus teléfonos de escritorio privado de escritorio (PBX) con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50bf4-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="50bf4-105">Si ha implementado el control remoto de llamadas en su entorno heredado y desea migrar it Lync Server 2013, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="50bf4-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="50bf4-106">Instala una puerta de enlace SIP/CSTA y configúrela para comunicarse con tu PBX.</span><span class="sxs-lookup"><span data-stu-id="50bf4-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="50bf4-107">Debe realizar este paso al implementar el grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50bf4-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="50bf4-108">Después de combinar su topología y migrar las directivas y la configuración, configure Lync Server 2013 para que enruten las solicitudes de CSTA a la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="50bf4-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="50bf4-109">Este paso es un paso manual que sigue la migración automática.</span><span class="sxs-lookup"><span data-stu-id="50bf4-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="50bf4-110">Para configurar el enrutamiento de las solicitudes de CSTA, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50bf4-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="50bf4-111">Elimine las entradas de host autorizadas heredadas (conocidas como *entradas de servidor de confianza* en Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="50bf4-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="50bf4-112">Si va a migrar usuarios de la implementación heredada, asegúrese de quitar todas las entradas de host autorizadas existentes que haya creado para la puerta de enlace SIP/CSTA antes de configurar las nuevas entradas de aplicaciones de confianza en el grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50bf4-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="50bf4-113">Para obtener más información sobre cómo quitar entradas de host heredadas, consulte [quitar una entrada de host autorizado](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="50bf4-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="50bf4-114">Configurar una ruta estática para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="50bf4-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="50bf4-115">Puede configurar una ruta estática para agrupaciones individuales que desee que admitan el control remoto de llamadas o puede configurar una ruta estática global para que cada grupo de servidores que no esté configurado con una ruta estática en el nivel de grupo use la ruta estática global.</span><span class="sxs-lookup"><span data-stu-id="50bf4-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="50bf4-116">Para obtener más información sobre cómo configurar la ruta estática, vea [configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="50bf4-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="50bf4-117">Configure una entrada de aplicación de confianza para el control remoto de llamadas en cada grupo para el que desee admitir el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="50bf4-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="50bf4-118">Para obtener más información sobre cómo configurar una entrada de aplicación de confianza, vea [configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="50bf4-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="50bf4-119">Si ha implementado una puerta de enlace SIP/CSTA que usa el protocolo de control de transmisión (TCP) para conectarse a Lync Server 2013, defina la dirección IP de la puerta de enlace en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="50bf4-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="50bf4-120">Para obtener más información sobre cómo definir la dirección IP, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="50bf4-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="50bf4-121">Configure los usuarios de Lync 2013 para el control remoto de llamadas habilitando el control remoto de llamadas y asignando un identificador uniforme de recursos (URI) de line Server y un URI de línea.</span><span class="sxs-lookup"><span data-stu-id="50bf4-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="50bf4-122">Al migrar usuarios de la implementación heredada a Lync Server 2013, se migra la configuración de control de llamada remota junto con la configuración del otro usuario.</span><span class="sxs-lookup"><span data-stu-id="50bf4-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="50bf4-123">Si ha personalizado las reglas de normalización de números de teléfono de la libreta de direcciones en la implementación heredada, tendrá que realizar algunas tareas manuales una vez completada la migración automática de las directivas y la configuración para migrar las reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="50bf4-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="50bf4-124">Si no ha personalizado las reglas de normalización, la libreta de direcciones se migrará junto con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="50bf4-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="50bf4-125">Para obtener detalles sobre la migración manual de reglas de normalización, consulte migrar la [Libreta de direcciones](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="50bf4-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

