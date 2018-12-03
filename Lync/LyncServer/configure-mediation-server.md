---
title: Configurar el servidor de mediación
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="a67c4-102">Configurar el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a67c4-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a67c4-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a67c4-103"></span></span>

<span data-ttu-id="a67c4-104">_**Última modificación del tema:** 09-2012-28_</span><span class="sxs-lookup"><span data-stu-id="a67c4-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a67c4-105">Este procedimiento detallan los pasos para configurar el grupo de Lync Server 2013 para usar el servidor de mediación de Lync Server 2013, en lugar del antiguo servidor Office Communications Server 2007 R2 mediación.</span><span class="sxs-lookup"><span data-stu-id="a67c4-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="a67c4-106">Para publicar correctamente, habilitar o deshabilitar una topología al agregar o quitar una función de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="a67c4-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a67c4-107">También es posible delegar los permisos para agregar funciones de servidor y derechos de administrador adecuados.</span><span class="sxs-lookup"><span data-stu-id="a67c4-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="a67c4-108">Para obtener información detallada, vea delegar permisos de instalación en el servidor Standard Edition o Enterprise Edition documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="a67c4-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a67c4-109">Otros cambios de configuración, es necesaria sólo pertenencia en el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a67c4-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a67c4-110">Para obtener la información más reciente sobre la búsqueda de puertas de enlace RTC cualificadas, sistemas IP-PBX y servicios de enlace troncal SIP que funcionan con Lync Server 2013, consulte "Microsoft Unified Communications Open Interoperability Program" en <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span><span class="sxs-lookup"><span data-stu-id="a67c4-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="a67c4-111">Para configurar el generador de topología de uso de servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a67c4-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="a67c4-112">Abrir una topología existente desde el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="a67c4-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="a67c4-113">En el panel izquierdo, vaya a **puertas de enlace RTC**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="a67c4-114">Secundario **puertas de enlace RTC**y, a continuación, haga clic en **Nueva puerta de enlace IP/RTC**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="a67c4-115">Complete la página **Definir nueva puerta de enlace IP/RTC** con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a67c4-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="a67c4-116">Escriba el FQDN o la dirección IP de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="a67c4-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="a67c4-117">El FQDN de la puerta de enlace es necesario si la puerta de enlace usa el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="a67c4-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="a67c4-118">Acepte el valor predeterminado del **puerto de escucha para puerta de enlace IP/RTC** o escriba el puerto de escucha de nuevo si se ha modificado.</span><span class="sxs-lookup"><span data-stu-id="a67c4-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="a67c4-119">Establecer el **Protocolo de transporte de Sip**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="a67c4-120">En el panel izquierdo, desplácese hasta el **grupo de servidores Front-End de Enterprise Edition** o el **Servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="a67c4-121">Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="a67c4-122">En **El servidor de mediación**, establezca los **puertos de escucha**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="a67c4-123">A continuación, asocie la puerta de enlace RTC recién creada seleccionándola y haciendo clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="a67c4-124">En **El generador de topología**, seleccione el nodo de nivel superior **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="a67c4-125">En el menú **acción** , seleccione **Publicar topología** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a67c4-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="a67c4-126">Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente.</span><span class="sxs-lookup"><span data-stu-id="a67c4-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a67c4-127">Es importante que complete el siguiente tema, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz de cambio para usar el nuevo servidor de mediación de Lync Server 2013</A> para asegurarse de que las rutas de voz señalen al servidor de mediación correcto.</span><span class="sxs-lookup"><span data-stu-id="a67c4-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="a67c4-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a67c4-128"></span></span></div>

