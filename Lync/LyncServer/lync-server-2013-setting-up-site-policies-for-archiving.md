---
title: 'Lync Server 2013: configuración de directivas de sitio para archivado'
description: 'Lync Server 2013: configuración de directivas de sitio para archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558396"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="e8762-103">Configuración de directivas de sitio para archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8762-103">Setting up site policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8762-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e8762-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e8762-105">Puede habilitar o deshabilitar el archivado de sitios específicos al crear y configurar una directiva de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="e8762-105">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="e8762-106">Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="e8762-106">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="e8762-107">Las directivas de archivado solo se aplican si no se usa la integración de Microsoft Exchange o si se usa la integración de Microsoft Exchange, pero hay algunos usuarios que no están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="e8762-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="e8762-108">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="e8762-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8762-109">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión.</span><span class="sxs-lookup"><span data-stu-id="e8762-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e8762-110">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="e8762-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e8762-111">Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="e8762-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="e8762-112">Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="e8762-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="e8762-113">Para crear una directiva de archivado para un sitio</span><span class="sxs-lookup"><span data-stu-id="e8762-113">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="e8762-114">Desde una cuenta de usuario que se asigne a la función CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e8762-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8762-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8762-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="e8762-116">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="e8762-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="e8762-117">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="e8762-117">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="e8762-118">Haga clic en  \*\*Nuevo \*\* y en  \*\*Directiva de sitio \*\*.</span><span class="sxs-lookup"><span data-stu-id="e8762-118">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="e8762-119">En  \*\*Seleccionar un sitio \*\*, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="e8762-119">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="e8762-120">En  \*\*Directiva de archivado nueva \*\*, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8762-120">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="e8762-121">En  \*\*Nombre \*\*, especifique el nombre para la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="e8762-121">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="e8762-122">En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).</span><span class="sxs-lookup"><span data-stu-id="e8762-122">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="e8762-123">Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla  \*\*Archivar comunicaciones internas \*\*.</span><span class="sxs-lookup"><span data-stu-id="e8762-123">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="e8762-124">Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla  \*\*Archivar comunicaciones externas \*\*.</span><span class="sxs-lookup"><span data-stu-id="e8762-124">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="e8762-125">Haga clic en  \*\*Confirmar \*\*.</span><span class="sxs-lookup"><span data-stu-id="e8762-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

