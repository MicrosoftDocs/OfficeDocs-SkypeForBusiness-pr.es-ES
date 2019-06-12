---
title: 'Lync Server 2013: configuración de directivas del sitio para archivar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="2eb63-102">Configurar directivas de sitio para archivar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eb63-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eb63-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2eb63-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2eb63-104">Puede habilitar o deshabilitar el archivado de sitios específicos creando y configurando una directiva de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="2eb63-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="2eb63-105">Las directivas de sitio invalidan las directivas globales, pero las directivas de usuario invalidan las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="2eb63-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="2eb63-106">Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están alojados en Exchange 2013 y tienen sus buzones en conservación local.</span><span class="sxs-lookup"><span data-stu-id="2eb63-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="2eb63-107">Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="2eb63-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eb63-108">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local.</span><span class="sxs-lookup"><span data-stu-id="2eb63-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2eb63-109">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2eb63-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2eb63-110">Es necesario que especifique todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado.</span><span class="sxs-lookup"><span data-stu-id="2eb63-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="2eb63-111">Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2eb63-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="2eb63-112">Para crear una directiva de archivado para un sitio</span><span class="sxs-lookup"><span data-stu-id="2eb63-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="2eb63-113">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2eb63-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2eb63-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2eb63-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="2eb63-115">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="2eb63-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="2eb63-116">Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="2eb63-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="2eb63-117">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="2eb63-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="2eb63-118">En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="2eb63-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="2eb63-119">En **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2eb63-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="2eb63-120">En **Nombre**, especifique el nombre para la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="2eb63-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="2eb63-121">En **Descripción**, proporcione información sobre la directiva de sitio (por ejemplo, directiva de sitio para Redmond).</span><span class="sxs-lookup"><span data-stu-id="2eb63-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="2eb63-122">Para controlar el archivado de las comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="2eb63-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="2eb63-123">Para controlar el archivado de las comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="2eb63-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="2eb63-124">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2eb63-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

