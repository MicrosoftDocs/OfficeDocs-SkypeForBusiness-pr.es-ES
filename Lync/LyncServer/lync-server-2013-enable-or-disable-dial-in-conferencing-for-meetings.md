---
title: 'Lync Server 2013: habilitar o deshabilitar las conferencias de acceso telefónico local para las reuniones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d23187c76a0e8711340f68e75a422a20ea7588
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532107"
---
# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="a3132-102">Habilitar o deshabilitar las conferencias de acceso telefónico local para reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3132-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3132-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a3132-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a3132-104">El siguiente procedimiento describe cómo permitir que los usuarios se unan a una reunión con acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a3132-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="a3132-105">Para habilitar o deshabilitar las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a3132-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="a3132-106">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a3132-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3132-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3132-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3132-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3132-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3132-109">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="a3132-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="a3132-110">En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia con acceso telefónico, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a3132-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a3132-p102">Para permitir que los usuarios se unan a la reunión con acceso telefónico, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones mediante la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="a3132-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="a3132-113">Haga clic en \*\*Confirmar \*\*.</span><span class="sxs-lookup"><span data-stu-id="a3132-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

