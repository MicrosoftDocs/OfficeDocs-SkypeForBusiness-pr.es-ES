---
title: Creación y configuración de directivas de usuario para archivado en Lync Server
description: Creación y configuración de directivas de usuario para archivado en Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dad260910f01e10c71dbbde67af98ea9a207e33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563096"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c00ca-103">Creación y configuración de directivas de usuario para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c00ca-103">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c00ca-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c00ca-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c00ca-105">Para habilitar o deshabilitar el archivado para usuarios específicos hospedados en Lync Server, primero debe crear una directiva de usuario y, a continuación, aplicar la Directiva a uno o más usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c00ca-105">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="c00ca-106">Para obtener más información sobre cómo aplicar directivas de usuario a usuarios y grupos de usuarios específicos, consulte [aplicar una directiva de archivado de Lync Server a un usuario en Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c00ca-106">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c00ca-107">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c00ca-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c00ca-108">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión.</span><span class="sxs-lookup"><span data-stu-id="c00ca-108">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c00ca-109">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c00ca-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c00ca-110">Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.</span><span class="sxs-lookup"><span data-stu-id="c00ca-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="c00ca-111">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c00ca-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="c00ca-112">Para configurar una directiva de archivado para los usuarios hospedados en Lync Server</span><span class="sxs-lookup"><span data-stu-id="c00ca-112">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="c00ca-113">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c00ca-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c00ca-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c00ca-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c00ca-115">Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c00ca-115">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c00ca-116">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c00ca-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="c00ca-117">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c00ca-117">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="c00ca-118">En **Nueva directiva de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c00ca-118">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="c00ca-119">En **Nombre**, escriba el nombre de la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="c00ca-119">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="c00ca-120">En **Descripción**, proporcione información sobre cuál es la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).</span><span class="sxs-lookup"><span data-stu-id="c00ca-120">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="c00ca-121">Para controlar el archivado de las comunicaciones internas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="c00ca-121">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="c00ca-122">Para controlar el archivado de las comunicaciones externas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="c00ca-122">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="c00ca-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c00ca-123">Click **Commit**.</span></span>

<span data-ttu-id="c00ca-124">Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.</span><span class="sxs-lookup"><span data-stu-id="c00ca-124">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="c00ca-125">Para obtener más información sobre cómo aplicar una directiva de usuario a usuarios específicos, consulte [aplicar una directiva de archivado de Lync Server a un usuario en Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c00ca-125">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

