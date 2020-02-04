---
title: 'Lync Server 2013: Probar el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82b8b7e494a66cf38fd27e37f322c79e95f801c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="0fe79-102">Probar el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fe79-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fe79-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0fe79-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0fe79-104">En este momento, tiene un grupo de directores o directores configurado, pero las entradas SRV del sistema de nombres de dominio (DNS) aún apuntan a los clientes para iniciar sesión usando un grupo de servidores o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0fe79-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="0fe79-105">Antes de cambiar el registro DNS para que los clientes de Lync 2013 inicien sesión automáticamente con el director, pruebe un cliente de forma manual al Director.</span><span class="sxs-lookup"><span data-stu-id="0fe79-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="0fe79-106">Para probar la implementación</span><span class="sxs-lookup"><span data-stu-id="0fe79-106">To test the deployment</span></span>

1.  <span data-ttu-id="0fe79-107">Inicie sesión en el equipo en el que tiene instalado el panel de control de Lync Server con una cuenta de dominio que forme parte del grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="0fe79-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="0fe79-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0fe79-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0fe79-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0fe79-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0fe79-110">En el panel de navegación, haga clic en **topología**y, en la columna **Estado** , confirme que hay un servidor verde con una flecha (es decir, ![icono de servidor con flecha verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icono de servidor con flecha verde")) para su director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="0fe79-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="0fe79-111">Conecte dos equipos cliente que tengan el cliente de Lync Server 2013 instalado e inicie sesión con una cuenta de usuario diferente habilitada para Lync Server 2013 en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="0fe79-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="0fe79-112">En uno de los equipos cliente, haga clic en el menú **Opciones** , seleccione el grupo configuración **personal** , haga clic en **avanzadas**, haga clic en **configuración manual**y, a continuación, establezca el **nombre del servidor interno o la dirección IP** en el nombre de dominio completo (FQDN) del nuevo director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="0fe79-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="0fe79-113">Inicie sesión en ambos clientes y compruebe que el cliente que inicia sesión con el director puede iniciar sesión correctamente, ver el estado de presencia del otro usuario y que pueden intercambiar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="0fe79-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

