---
title: 'Lync Server 2013: Editar o configurar direcciones URL sencillas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="dcac5-102">Editar o configurar direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcac5-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcac5-103">_**Última modificación del tema:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="dcac5-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="dcac5-104">Este procedimiento no requiere la pertenencia a un grupo de dominio de administrador o de privilegios local.</span><span class="sxs-lookup"><span data-stu-id="dcac5-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="dcac5-105">Debe iniciar sesión en un equipo como usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="dcac5-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="dcac5-106">Lync Server 2013 usa direcciones URL simples para dirigir llamadas internas y externas a servicios en el servidor front-end o en el director, si se ha implementado una.</span><span class="sxs-lookup"><span data-stu-id="dcac5-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="dcac5-107">Para obtener más información acerca de las direcciones URL simples, consulte [planificación de direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="dcac5-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="dcac5-108">Puede seleccionar el formato de las direcciones URL simples de varias opciones.</span><span class="sxs-lookup"><span data-stu-id="dcac5-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="dcac5-109">Para obtener más información sobre estas opciones, consulte [requisitos de DNS para obtener direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="dcac5-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="dcac5-110">De forma predeterminada, las direcciones URL simples se configurarán con el formato (por ejemplo, la dirección URL de acceso https://dialin.\<SIP telefónico simple): dominio\></span><span class="sxs-lookup"><span data-stu-id="dcac5-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="dcac5-111">Para configurar direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="dcac5-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="dcac5-112">En el generador de topología, haga clic con el botón secundario en el nodo de **Lync Server** y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dcac5-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dcac5-113">En el panel **Direcciones URL sencillas**, seleccione **Direcciones URL de acceso telefónico:** (marcado) o **Direcciones URL de reunión:** (reunión) para editarlas. Luego, haga clic en **Editar dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="dcac5-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="dcac5-114">Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="dcac5-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="dcac5-115">El ejemplo que se muestra aquí ha modificado la dirección URL de https://pool01.contoso.net/dialinacceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="dcac5-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="dcac5-116">Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="dcac5-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="dcac5-117">Para definir la dirección URL sencilla de administración opcional</span><span class="sxs-lookup"><span data-stu-id="dcac5-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="dcac5-118">En el generador de topología, haga clic con el botón secundario en el nodo de **Lync Server** y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dcac5-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dcac5-119">En el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dcac5-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="dcac5-120">Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración.</span><span class="sxs-lookup"><span data-stu-id="dcac5-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="dcac5-121">La opción más sencilla es <STRONG> https://admin.</STRONG> &lt;dominio&gt;.</span><span class="sxs-lookup"><span data-stu-id="dcac5-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dcac5-122">Si modifica una dirección URL sencilla después de la implementación inicial, necesita saber qué cambios influyen en los certificados y registros del Sistema de nombres de dominio (DNS) relativos a las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="dcac5-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="dcac5-123">Si el cambio afecta a la base de una dirección URL simple, debe cambiar también los certificados y los registros DNS.</span><span class="sxs-lookup"><span data-stu-id="dcac5-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="dcac5-124">Por ejemplo, si cambia https://lync.contoso.com/Meet de https://meet.contoso.com para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, tendrá que cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dcac5-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="dcac5-125">Si cambió la dirección URL simple de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario realizar cambios en el certificado o DNS.</span><span class="sxs-lookup"><span data-stu-id="dcac5-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="dcac5-126">Sin embargo, siempre que cambie un nombre de dirección URL simple, debe ejecutar el cmdlet <STRONG>enable-CsComputer</STRONG> en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="dcac5-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcac5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcac5-127">See Also</span></span>


[<span data-ttu-id="dcac5-128">Planeación de las direcciones URL simples en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcac5-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

