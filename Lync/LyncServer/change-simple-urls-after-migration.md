---
title: Cambiar direcciones URL sencillas después de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: df0d6666f4ea824d59a97eb1f63b66016c75d547
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="49a9f-102">Cambiar direcciones URL sencillas después de la migración</span><span class="sxs-lookup"><span data-stu-id="49a9f-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a9f-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="49a9f-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="49a9f-104">Lync Server admite tres direcciones URL sencillas:</span><span class="sxs-lookup"><span data-stu-id="49a9f-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="49a9f-p101">**Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.</span><span class="sxs-lookup"><span data-stu-id="49a9f-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="49a9f-p102">**Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="49a9f-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="49a9f-109">El **Administrador** habilita el acceso rápido al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49a9f-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="49a9f-110">La dirección URL simple de administración es de uso interno para la organización.</span><span class="sxs-lookup"><span data-stu-id="49a9f-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="49a9f-111">Después de migrar a Lync Server 2013, debe tener en cuenta cómo afecta el cambio a los registros DNS y certificados para las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="49a9f-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="49a9f-112">Si el director de Lync Server 2010 heredado permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="49a9f-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="49a9f-113">Si se quita el director de Lync Server 2010 de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49a9f-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="49a9f-114">Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="49a9f-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="49a9f-115">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="49a9f-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="49a9f-116">**Para actualizar las direcciones URL simples de reunión**</span><span class="sxs-lookup"><span data-stu-id="49a9f-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="49a9f-117">En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="49a9f-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="49a9f-118">Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, debajo de direcciones URL de **reunión:** seleccione la dirección URL de reunirse y haga clic en **Editar dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="49a9f-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="49a9f-119">Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="49a9f-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="49a9f-120">**Para actualizar las direcciones URL simples de administración**</span><span class="sxs-lookup"><span data-stu-id="49a9f-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="49a9f-121">En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="49a9f-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="49a9f-122">Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, en el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo al panel de Control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a9f-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="49a9f-123">Recomendamos usar la dirección URL más simple posible para la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="49a9f-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="49a9f-124">La opción más sencilla es <STRONG> https://admin.</STRONG> &lt;dominio&gt;.</span><span class="sxs-lookup"><span data-stu-id="49a9f-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49a9f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="49a9f-125">See Also</span></span>


[<span data-ttu-id="49a9f-126">Planeación de direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a9f-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

