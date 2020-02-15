---
title: 'Lync Server 2013: configuración de la invitación a la reunión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="46c68-102">Configuración de la invitación a la reunión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c68-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c68-103">_**Última modificación del tema:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="46c68-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="46c68-104">Puede personalizar las invitaciones a reuniones enviadas por el complemento de reunión en línea para Lync 2013 mediante la inclusión de los siguientes elementos opcionales en el cuerpo de la invitación a la reunión:</span><span class="sxs-lookup"><span data-stu-id="46c68-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="46c68-105">**Logotipo de la organización** Agregue el logotipo de su organización a invitaciones a reuniones mediante la opción de dirección URL del logotipo.</span><span class="sxs-lookup"><span data-stu-id="46c68-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="46c68-106">Si las invitaciones a reuniones se enviarán a personas externas a la organización, la imagen debe estar ubicada en una dirección URL disponible públicamente.</span><span class="sxs-lookup"><span data-stu-id="46c68-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="46c68-107">Los formatos de imagen admitidos son GIF y JPG.</span><span class="sxs-lookup"><span data-stu-id="46c68-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="46c68-108">Aunque Lync Server 2013 almacena la dirección URL sin restricciones de tamaño en la imagen, para obtener los mejores resultados, el tamaño máximo de la imagen debe ser de 30 píxeles de alto por 188 píxeles de ancho.</span><span class="sxs-lookup"><span data-stu-id="46c68-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="46c68-109">**Vínculo personalizado de ayuda o soporte técnico** Agregue una dirección URL para el sitio web de ayuda o soporte técnico de la organización.</span><span class="sxs-lookup"><span data-stu-id="46c68-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="46c68-110">Si se van a enviar invitaciones a reuniones a personas externas a la organización, la dirección URL debe estar disponible públicamente.</span><span class="sxs-lookup"><span data-stu-id="46c68-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="46c68-111">La longitud máxima de la dirección URL es 1 KB.</span><span class="sxs-lookup"><span data-stu-id="46c68-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="46c68-112">**Texto de declinación de responsabilidades legal** Agregue una dirección URL para el texto legal o un aviso de declinación de responsabilidades que se mostrará en todas las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="46c68-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="46c68-113">Si se van a enviar invitaciones a reuniones a personas externas a la organización, la dirección URL debe estar disponible públicamente.</span><span class="sxs-lookup"><span data-stu-id="46c68-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="46c68-114">La longitud máxima de la dirección URL es 1 KB.</span><span class="sxs-lookup"><span data-stu-id="46c68-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="46c68-115">**Texto de pie de página personalizado** Agregar texto que se representará como pie de página personalizado en la invitación.</span><span class="sxs-lookup"><span data-stu-id="46c68-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="46c68-116">La longitud máxima del texto que se puede Agregar es 2 KB.</span><span class="sxs-lookup"><span data-stu-id="46c68-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="46c68-117">Puede configurar estas opciones mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c68-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="46c68-118">**Para personalizar la invitación a la reunión mediante el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="46c68-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="46c68-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46c68-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="46c68-120">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c68-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46c68-121">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46c68-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="46c68-122">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="46c68-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="46c68-123">En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="46c68-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="46c68-p106">Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46c68-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46c68-p107">Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46c68-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="46c68-130">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="46c68-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="46c68-131">En el campo **dirección URL del logotipo** , escriba la dirección URL de la imagen de logotipo de su organización.</span><span class="sxs-lookup"><span data-stu-id="46c68-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="46c68-132">En el campo **dirección URL** de la ayuda, escriba la dirección URL del sitio de ayuda o soporte técnico de su organización.</span><span class="sxs-lookup"><span data-stu-id="46c68-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="46c68-133">En el campo **texto legal** , escriba la dirección URL del texto legal o declinación de responsabilidades que desea incluir en las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="46c68-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="46c68-134">En el campo de **texto personalizado de pie de página** , escriba texto de pie de página, hasta 2 KB.</span><span class="sxs-lookup"><span data-stu-id="46c68-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="46c68-135">**Para personalizar la invitación a la reunión con el shell de administración de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="46c68-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="46c68-136">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="46c68-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="46c68-137">Ejecute el cmdlet **New-CsMeetingConfiguration** o **set-CsMeetingConfiguration** para crear o configurar las opciones de la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="46c68-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="46c68-138">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="46c68-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

