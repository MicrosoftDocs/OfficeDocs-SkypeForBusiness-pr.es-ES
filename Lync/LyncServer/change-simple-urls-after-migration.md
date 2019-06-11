---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0203b33d787310544f4f376872ecf9c99fc7254d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="d0403-102">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="d0403-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0403-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d0403-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d0403-104">Lync Server admite tres direcciones URL simples:</span><span class="sxs-lookup"><span data-stu-id="d0403-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="d0403-105">**Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización.</span><span class="sxs-lookup"><span data-stu-id="d0403-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="d0403-106">Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente.</span><span class="sxs-lookup"><span data-stu-id="d0403-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="d0403-107">El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="d0403-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="d0403-108">La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="d0403-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="d0403-109">El **Administrador** permite acceder rápidamente al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0403-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="d0403-110">La dirección URL simple de administración es interna de su organización.</span><span class="sxs-lookup"><span data-stu-id="d0403-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="d0403-111">Después de migrar a Lync Server 2013, debe tener en cuenta cómo afecta el cambio a los registros DNS y los certificados para las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="d0403-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="d0403-112">Si el director de Lync Server 2010 heredado permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="d0403-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="d0403-113">Si se quita Lync Server 2010 Director de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0403-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="d0403-114">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar enable-CsComputer en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="d0403-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="d0403-115">Cambiar las URL simples después de la migración</span><span class="sxs-lookup"><span data-stu-id="d0403-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="d0403-116">**Para actualizar la dirección URL simple de reunirse**</span><span class="sxs-lookup"><span data-stu-id="d0403-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="d0403-117">En el generador de topología, haga clic con el botón secundario en el nodo superior de **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d0403-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="d0403-118">Seleccione **URL simples** en el panel izquierdo y, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y haga clic en **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="d0403-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="d0403-119">Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="d0403-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="d0403-120">**Para actualizar la dirección URL simple de administración**</span><span class="sxs-lookup"><span data-stu-id="d0403-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="d0403-121">En el generador de topología, haga clic con el botón secundario en el nodo superior de **Lync Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d0403-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="d0403-122">Seleccione **URL simples** en el panel izquierdo y, a continuación, haga clic en **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de Control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0403-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d0403-123">Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración.</span><span class="sxs-lookup"><span data-stu-id="d0403-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="d0403-124">La opción más sencilla es <STRONG> https://admin.</STRONG> &lt;dominio&gt;.</span><span class="sxs-lookup"><span data-stu-id="d0403-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0403-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0403-125">See Also</span></span>


[<span data-ttu-id="d0403-126">Planeación de las direcciones URL simples en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0403-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

