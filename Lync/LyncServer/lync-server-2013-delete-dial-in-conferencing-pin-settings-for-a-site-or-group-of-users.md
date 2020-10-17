---
title: Eliminar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios
description: Eliminar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a40168780d5ac5f37ceb33dfaacd25b492d6307a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564256"
---
# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="fb105-103">Eliminar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb105-103">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb105-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fb105-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fb105-105">Siga estos pasos para eliminar una directiva de PIN de nivel de usuario o de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="fb105-105">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fb105-106">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="fb105-106">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="fb105-107">Para eliminar una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="fb105-107">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="fb105-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb105-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fb105-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb105-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb105-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb105-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb105-111">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="fb105-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="fb105-112">En la página **Directiva de PIN** , en el campo de búsqueda, escriba todo o parte del nombre de la Directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="fb105-112">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="fb105-113">En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fb105-113">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="fb105-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb105-114">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

