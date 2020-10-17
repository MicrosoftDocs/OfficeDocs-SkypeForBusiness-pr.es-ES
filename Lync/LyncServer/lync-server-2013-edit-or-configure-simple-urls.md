---
title: 'Lync Server 2013: editar o configurar direcciones URL sencillas'
description: 'Lync Server 2013: editar o configurar direcciones URL sencillas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551636"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="5ffc5-103">Editar o configurar direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ffc5-103">Edit or configure simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ffc5-104">_**Última modificación del tema:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="5ffc5-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="5ffc5-p101">Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="5ffc5-107">Lync Server 2013 usa direcciones URL sencillas para dirigir llamadas internas y externas a los servicios del servidor front-end o del Director, si se ha implementado una.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-107">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="5ffc5-108">Para obtener más información acerca de las direcciones URL sencillas, consulte [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-108">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="5ffc5-109">Puede seleccionar el formato de las direcciones URL sencillas desde varias opciones.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-109">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="5ffc5-110">Para obtener más información sobre estas opciones, consulte [DNS Requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-110">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="5ffc5-111">De forma predeterminada, las direcciones URL sencillas se configurarán en forma de (por ejemplo, la dirección URL sencilla de acceso telefónico): https://dialin .\<SIP Domain\></span><span class="sxs-lookup"><span data-stu-id="5ffc5-111">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="5ffc5-112">Para configurar direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="5ffc5-112">To configure simple URLs</span></span>

1.  <span data-ttu-id="5ffc5-113">En el generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-113">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="5ffc5-114">En el panel **direcciones URL simples** , seleccione **direcciones URL de acceso telefónico:** (acceso telefónico) o **direcciones URL de reunión:** (reunirse) para editar y, a continuación, haga clic en **Editar dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-114">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="5ffc5-115">Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-115">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="5ffc5-116">El ejemplo que se muestra aquí ha modificado la dirección URL de acceso telefónico a https://pool01.contoso.net/dialin .</span><span class="sxs-lookup"><span data-stu-id="5ffc5-116">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="5ffc5-117">Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-117">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="5ffc5-118">Para definir la dirección URL sencilla de administración opcional</span><span class="sxs-lookup"><span data-stu-id="5ffc5-118">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="5ffc5-119">En el generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-119">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="5ffc5-120">En el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo al panel de control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-120">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5ffc5-121">Recomendamos usar la dirección URL más simple posible para la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-121">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="5ffc5-122">La opción más sencilla es <STRONG> https://admin .</STRONG> &lt; dominio &gt; .</span><span class="sxs-lookup"><span data-stu-id="5ffc5-122">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5ffc5-123">Si cambia una dirección URL sencilla tras la implementación inicial, deberá conocer qué cambios afectan a los certificados y los registros de su sistema de nombres de dominio (DNS) para direcciones de URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-123">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="5ffc5-124">Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-124">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="5ffc5-125">Por ejemplo, si se cambia de https://lync.contoso.com/Meet para https://meet.contoso.com cambia la dirección URL base de lync.contoso.com a meet.contoso.com, es necesario cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-125">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="5ffc5-126">Si ha cambiado la dirección URL sencilla de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings , la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario ningún cambio de certificado o DNS.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-126">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="5ffc5-127">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar el cmdlet <STRONG>enable-CsComputer</STRONG> en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="5ffc5-127">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ffc5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ffc5-128">See Also</span></span>


[<span data-ttu-id="5ffc5-129">Planeación de direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ffc5-129">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

