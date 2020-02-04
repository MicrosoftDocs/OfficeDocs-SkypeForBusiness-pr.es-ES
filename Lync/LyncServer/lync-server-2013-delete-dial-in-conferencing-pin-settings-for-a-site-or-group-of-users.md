---
title: Eliminar la configuración del PIN de conferencias de acceso telefónico local para un sitio o grupo de usuarios
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
ms.openlocfilehash: ae81fd45c2679c8b4d2ab0bf6813fbb405905224
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="e84f7-102">Eliminar la configuración del PIN de conferencias de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e84f7-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84f7-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e84f7-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e84f7-104">Siga estos pasos para eliminar una directiva de PIN de nivel de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="e84f7-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e84f7-105">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="e84f7-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="e84f7-106">Para eliminar una directiva de PIN de un usuario o un sitio</span><span class="sxs-lookup"><span data-stu-id="e84f7-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="e84f7-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e84f7-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e84f7-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e84f7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e84f7-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e84f7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e84f7-110">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="e84f7-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e84f7-111">En la página **Directiva de PIN** , en el campo de búsqueda, escriba todo o parte del nombre de la Directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="e84f7-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e84f7-112">En la lista de directivas, haga clic en la directiva que desea, en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e84f7-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e84f7-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e84f7-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

