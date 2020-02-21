---
title: Habilitar control remoto de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c32e71ddc7ef0033b6a3380d394e0fe0e559945
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="8c6a1-102">Habilitar control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="8c6a1-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c6a1-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8c6a1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8c6a1-104">El control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) de escritorio con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="8c6a1-105">Si implementó el control remoto de llamadas en su entorno heredado y desea migrar it Lync Server 2013, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="8c6a1-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="8c6a1-106">Instale una puerta de enlace SIP/CSTA y configúrela para que se comunique con su PBX.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="8c6a1-107">Debe realizar este paso al implementar el grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="8c6a1-108">Después de combinar la topología y migrar las directivas y la configuración, configure Lync Server 2013 para enrutar las solicitudes CSTA a la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="8c6a1-109">Se trata de un paso manual que sigue a la migración automatizada.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="8c6a1-110">Para configurar el enrutamiento de solicitudes CSTA, lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8c6a1-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="8c6a1-111">Quite las entradas de host autorizado heredado (conocidas como *entradas de servidor de confianza* en Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="8c6a1-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="8c6a1-112">Si va a migrar los usuarios de la implementación heredada, asegúrese de quitar todas las entradas de host autorizadas existentes que ha creado para la puerta de enlace SIP/CSTA antes de configurar las nuevas entradas de la aplicación de confianza en el grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="8c6a1-113">Para obtener información detallada acerca de cómo quitar entradas de host autorizadas heredadas, consulte [quitar una entrada de host autorizado](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="8c6a1-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="8c6a1-114">Configure una ruta estática para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="8c6a1-115">Puede configurar una ruta estática para los grupos individuales en los que quiera usar el control remoto de llamadas, o bien configurar una ruta estática global para que la usen los grupos que no tengan una individual configurada expresamente.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="8c6a1-116">Para obtener más información sobre cómo configurar la ruta estática, vea [Configure a static Route for Remote Call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="8c6a1-117">Configure una entrada de aplicación de confianza de control remoto de llamadas en cada grupo en el que quiera admitir el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="8c6a1-118">Para obtener más información sobre cómo configurar una entrada de aplicación de confianza, vea [Configure a Trusted Application entry for Remote Call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="8c6a1-119">Si ha implementado una puerta de enlace SIP/CSTA que usa el protocolo de control de transmisión (TCP) para conectarse a Lync Server 2013, defina la dirección IP de la puerta de enlace en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="8c6a1-120">Para obtener más información sobre cómo definir la dirección IP, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="8c6a1-121">Configure los usuarios de Lync 2013 para el control remoto de llamadas habilitando el control remoto de llamadas y asignando un identificador uniforme de recursos (URI) de servidor de línea y un URI de línea.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="8c6a1-122">Al migrar usuarios de la implementación heredada a Lync Server 2013, la configuración del control de llamadas remotas se migra junto con la configuración del otro usuario.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="8c6a1-123">Si personalizó las reglas de normalización de números de teléfono de la Libreta de direcciones en la implementación heredada, cuando finalice la migración automatizada de las directivas y las configuraciones deberá realizar algunas tareas manuales para migrar estas reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="8c6a1-124">Si no personalizó ninguna regla, la Libreta de direcciones se migra con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="8c6a1-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="8c6a1-125">Para obtener información detallada sobre cómo migrar manualmente las reglas de normalización personalizadas, consulte [Migrate Address Book](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="8c6a1-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

