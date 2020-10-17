---
title: Cambiar las direcciones URL simples tras la migración
description: Cambiar direcciones URL sencillas después de la migración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f9974106d28bcfdc64c2255337baf721a937e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545766"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="54392-103">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="54392-103">Change simple URLs after migration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54392-104">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="54392-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="54392-105">Lync Server admite tres direcciones URL sencillas:</span><span class="sxs-lookup"><span data-stu-id="54392-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="54392-p101">**Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.</span><span class="sxs-lookup"><span data-stu-id="54392-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="54392-p102">**Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="54392-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="54392-110">El **Administrador** habilita el acceso rápido al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54392-110">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="54392-111">La dirección URL simple de administración es de uso interno para la organización.</span><span class="sxs-lookup"><span data-stu-id="54392-111">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="54392-112">Después de migrar a Lync Server 2013, debe tener en cuenta cómo afecta el cambio a los registros DNS y certificados para las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="54392-112">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="54392-113">Si el director de Lync Server 2010 heredado permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="54392-113">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="54392-114">Si se quita el director de Lync Server 2010 de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54392-114">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="54392-115">Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="54392-115">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="54392-116">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="54392-116">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="54392-117">**Para actualizar las direcciones URL simples de reunión**</span><span class="sxs-lookup"><span data-stu-id="54392-117">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="54392-118">En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="54392-118">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="54392-119">Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, debajo de direcciones URL de **reunión:** seleccione la dirección URL de reunirse y haga clic en **Editar dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="54392-119">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="54392-120">Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="54392-120">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="54392-121">**Para actualizar las direcciones URL simples de administración**</span><span class="sxs-lookup"><span data-stu-id="54392-121">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="54392-122">En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="54392-122">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="54392-123">Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, en el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo al panel de Control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54392-123">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="54392-124">Recomendamos usar la dirección URL más simple posible para la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="54392-124">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="54392-125">La opción más sencilla es <STRONG> https://admin .</STRONG> &lt; dominio &gt; .</span><span class="sxs-lookup"><span data-stu-id="54392-125">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54392-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54392-126">See Also</span></span>


[<span data-ttu-id="54392-127">Planeación de direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54392-127">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

