---
title: Configurar el servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389c6e5c017594bf386109541a379bd5ae2f7e01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="e7ef1-102">Configurar el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="e7ef1-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7ef1-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e7ef1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e7ef1-104">En este procedimiento se detallan los pasos para configurar el grupo de servidores de Lync Server 2013 para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="e7ef1-105">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="e7ef1-106">También es posible delegar los derechos y permisos de administrador adecuados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="e7ef1-107">Para obtener información detallada, consulte Delegate Setup Permissions en la documentación referente a la implementación de servidores Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="e7ef1-108">Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7ef1-109">Para obtener la información más reciente sobre cómo buscar puertas de enlace RTC cualificadas, IP-PBX y servicios de enlace troncal SIP que funcionen con Lync Server 2013, consulte "Microsoft Unified Communications <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Open Interoperability Program" en.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="e7ef1-110">Para configurar el servidor de mediación mediante el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="e7ef1-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="e7ef1-111">Abre una topología existente del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="e7ef1-112">En el panel de la izquierda, navegue a **Puertas de enlace RTC**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="e7ef1-113">Haga clic con el botón secundario en \*\*Puertas de enlace RTC \*\* y, a continuación, haga clic en \*\*Nueva puerta de enlace IP/RTC \*\*.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="e7ef1-114">Complete la página \*\*Definir nueva puerta de enlace IP/RTC \*\* con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e7ef1-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="e7ef1-p102">Indique el FQDN de puerta de enlace o la dirección IP. El FQDN de la puerta de enlace es obligatorio si la puerta de enlace utiliza el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="e7ef1-117">Acepte el valor predeterminado de la opción **Puerto de escucha para la puerta de enlace IP/RTC** o, si se ha modificado, especifique el nuevo puerto de escucha.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="e7ef1-118">Establezca el **	Protocolo de transporte SIP**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="e7ef1-119">En el panel de la izquierda, navegue al **grupo de servidores front-end Enterprise Edition** o al **servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="e7ef1-120">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="e7ef1-121">En **Servidor de mediación**, defina los **Puertos de escucha**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="e7ef1-122">A continuación, asocie la puerta de enlace RTC recién creada seleccionándola y haciendo clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="e7ef1-123">En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="e7ef1-124">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="e7ef1-125">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7ef1-126">Es importante que complete el siguiente tema, cambie las <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</A> para asegurarse de que las rutas de voz señalen al servidor de mediación correcto.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

