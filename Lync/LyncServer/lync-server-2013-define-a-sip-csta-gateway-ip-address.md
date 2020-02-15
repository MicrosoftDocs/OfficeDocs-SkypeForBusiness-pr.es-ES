---
title: 'Lync Server 2013: definir una dirección IP de puerta de enlace SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="15476-102">Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15476-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15476-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="15476-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="15476-104">Si Lync Server se conectará a la puerta de enlace SIP/CSTA que implementó para el control remoto de llamadas mediante una conexión de protocolo de control de transmisión (TCP), debe definir la dirección IP de la puerta de enlace en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="15476-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="15476-105">Este paso no es necesario para puertas de enlace compatibles con conexiones de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="15476-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="15476-106">Para cualquier puerta de enlace que admita conexiones TLS, puede omitir este procedimiento y continuar con la implementación del control remoto de llamadas siguiendo los pasos descritos en [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="15476-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="15476-107">Para definir la dirección IP de la puerta de enlace SIP/CSTA con el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="15476-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="15476-108">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="15476-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="15476-109">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15476-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="15476-110">Elija la opción para descargar una topología existente.</span><span class="sxs-lookup"><span data-stu-id="15476-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="15476-111">Expanda el nodo **Servidores de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="15476-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="15476-112">Haga clic con el botón secundario en el grupo de aplicaciones de confianza que ha creado, como se describe en [configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="15476-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="15476-113">Desactive la casilla **Habilitar replicación de datos de configuración en este grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="15476-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="15476-p102">Haga clic en **Limitar el uso del servicio a las direcciones IP seleccionadas**. La configuración predeterminada es **Usar todas las direcciones IP configuradas**.</span><span class="sxs-lookup"><span data-stu-id="15476-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="15476-116">En el cuadro de texto **Dirección IP principal**, escriba la dirección IP de la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="15476-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="15476-117">Para actualizar la topología en el almacén de administración central, en el árbol de la consola, haga clic en **Lync Server** y, desde el panel **Acciones**, haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="15476-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15476-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="15476-118">See Also</span></span>


[<span data-ttu-id="15476-119">Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15476-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="15476-120">Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15476-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

