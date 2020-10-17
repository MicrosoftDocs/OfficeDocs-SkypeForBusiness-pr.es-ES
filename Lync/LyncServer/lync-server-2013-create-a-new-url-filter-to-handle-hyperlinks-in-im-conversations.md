---
title: Crear un nuevo filtro de dirección URL para administrar hipervínculos en conversaciones de mensajería instantánea
description: Cree un nuevo filtro de dirección URL para controlar los hipervínculos en las conversaciones de mensajería instantánea.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554666"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="5fb75-103">Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="5fb75-103">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb75-104">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="5fb75-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="5fb75-105">Además de modificar el filtro de dirección URL global, puede configurar filtros de URL personalizados para sitios individuales dentro de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fb75-105">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="5fb75-106">Para obtener más información sobre el filtrado de URL, consulte [configuración de transferencia de archivos y filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="5fb75-106">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="5fb75-107">Para crear un filtro nuevo para direcciones URL</span><span class="sxs-lookup"><span data-stu-id="5fb75-107">To create a new URL filter</span></span>

1.  <span data-ttu-id="5fb75-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5fb75-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fb75-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb75-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fb75-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fb75-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fb75-111">En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro para direcciones URL**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-111">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="5fb75-112">En la página **Filtro para direcciones URL**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-112">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="5fb75-113">En el cuadro de diálogo **Seleccionar un sitio**, haga clic en el sitio para el que desea crear un filtro para direcciones URL y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-113">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="5fb75-114">En el cuadro **Filtro para direcciones URL nuevo**, active la casilla **Habilitar filtro para direcciones URL** para habilitar el filtrado para direcciones URL del sitio.</span><span class="sxs-lookup"><span data-stu-id="5fb75-114">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="5fb75-115">Para bloquear cualquier URL activa que contenga un archivo con una extensión que aparezca en **Extensiones de tipo de archivo a bloquear**, en **Editar filtro de archivo**, active la casilla **Bloquear direcciones URL con extensión de archivo**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-115">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="5fb75-116">En la lista desplegable **Prefijo de hipervínculo**, haga clic en la opción que corresponde a cómo desea administrar direcciones URL en conversaciones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="5fb75-116">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="5fb75-117">Con el cuadro **Permitir mensaje**, puede enviar un mensaje de advertencia al usuario cuando se envíen hipervínculos permitidos.</span><span class="sxs-lookup"><span data-stu-id="5fb75-117">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="5fb75-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5fb75-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fb75-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fb75-119">See Also</span></span>


[<span data-ttu-id="5fb75-120">Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fb75-120">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="5fb75-121">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="5fb75-121">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="5fb75-122">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fb75-122">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="5fb75-123">Modificar el filtro de direcciones URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fb75-123">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

