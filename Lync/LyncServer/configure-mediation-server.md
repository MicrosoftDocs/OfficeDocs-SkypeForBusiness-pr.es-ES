---
title: Configurar servidor de mediación
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
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="90170-102">Configurar servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="90170-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90170-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="90170-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="90170-104">Este procedimiento detalla los pasos para configurar el grupo de servidores de Lync 2013 para que usen el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="90170-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="90170-105">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="90170-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="90170-106">También es posible delegar los derechos y permisos de administrador adecuados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="90170-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="90170-107">Para obtener más información, consulte permisos de configuración de delegación en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="90170-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="90170-108">Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="90170-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90170-109">Para obtener la información más reciente sobre la búsqueda de puertas de enlace RTC calificadas, IP-PBX y los servicios de Troncalización SIP que funcionan con Lync Server 2013, consulte "programa de <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>interoperabilidad abierto de comunicaciones unificadas de Microsoft" en.</span><span class="sxs-lookup"><span data-stu-id="90170-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="90170-110">Para configurar el servidor de mediación con el generador de topología</span><span class="sxs-lookup"><span data-stu-id="90170-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="90170-111">Abra una topología existente desde el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="90170-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="90170-112">En el panel de la izquierda, vaya a **puertas de enlace RTC**.</span><span class="sxs-lookup"><span data-stu-id="90170-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="90170-113">Haga clic con el botón secundario en **puertas de enlace RTC**y luego haga clic en **nueva puerta de enlace IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="90170-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="90170-114">Complete la página **definir nueva puerta de enlace IP/RTC** con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="90170-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="90170-115">Escriba la dirección IP o el FQDN de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="90170-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="90170-116">El FQDN de la puerta de enlace es obligatorio si la puerta de enlace usa el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="90170-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="90170-117">Acepte el valor predeterminado del **Puerto de escucha para la puerta de enlace IP/PSTN** o introduzca el nuevo puerto de escucha si se modificó.</span><span class="sxs-lookup"><span data-stu-id="90170-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="90170-118">Configurar el **Protocolo de transporte SIP**.</span><span class="sxs-lookup"><span data-stu-id="90170-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="90170-119">En el panel de la izquierda, navegue hasta el **grupo de servidores front-end Enterprise Edition** o el **servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="90170-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="90170-120">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="90170-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="90170-121">En **servidor de mediación**, configure los **puertos de escucha**.</span><span class="sxs-lookup"><span data-stu-id="90170-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="90170-122">A continuación, para asociar la puerta de enlace RTC recién creada, selecciónela y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="90170-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="90170-123">En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="90170-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="90170-124">En el menú **acción** , seleccione **publicar topología** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90170-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="90170-125">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="90170-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90170-126">Es importante que complete el siguiente tema, cambie las <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz para usar el nuevo servidor de mediación de Lync server 2013</A> para asegurarse de que las rutas de voz apuntan al servidor de mediación correcto.</span><span class="sxs-lookup"><span data-stu-id="90170-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

