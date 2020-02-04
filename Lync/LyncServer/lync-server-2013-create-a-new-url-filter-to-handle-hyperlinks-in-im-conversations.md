---
title: Crear un filtro de dirección URL para procesar hipervínculos en conversaciones de mensajería instantánea
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
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="b0300-102">Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="b0300-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0300-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b0300-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b0300-104">Además de modificar el filtro de dirección URL global, puede configurar filtros de URL personalizados para sitios individuales dentro de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0300-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="b0300-105">Para obtener más información sobre el filtrado de URL, consulte [configuración de la transferencia de archivos y filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="b0300-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="b0300-106">Para crear un filtro de dirección URL nuevo</span><span class="sxs-lookup"><span data-stu-id="b0300-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="b0300-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b0300-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0300-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0300-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b0300-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0300-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b0300-110">En la barra de navegación izquierda, haga clic en **mensajería instantánea y presencia**y, a continuación, haga clic en **filtro de URL**.</span><span class="sxs-lookup"><span data-stu-id="b0300-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="b0300-111">En la página **filtro de URL** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b0300-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="b0300-112">En **seleccionar un sitio**, haga clic en el sitio para el que desea crear el filtro de dirección URL y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0300-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="b0300-113">En el cuadro de diálogo **nuevo filtro de URL** , seleccione la casilla de verificación **Habilitar filtro** de URL para habilitar el filtrado de URL para el sitio.</span><span class="sxs-lookup"><span data-stu-id="b0300-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="b0300-114">Para bloquear cualquier dirección URL activa que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloquean** en **Editar filtro de archivo**, active la casilla **bloquear direcciones URL con extensión de archivo** .</span><span class="sxs-lookup"><span data-stu-id="b0300-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="b0300-115">En el cuadro de lista desplegable **prefijo del hipervínculo** , haga clic en la opción que corresponde a cómo desea controlar las direcciones URL en las conversaciones de mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="b0300-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="b0300-116">El cuadro **permitir mensaje** permite que se envíe un mensaje de advertencia al usuario al enviar hipervínculos que pueden enviarse.</span><span class="sxs-lookup"><span data-stu-id="b0300-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="b0300-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b0300-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0300-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0300-118">See Also</span></span>


[<span data-ttu-id="b0300-119">Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0300-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="b0300-120">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="b0300-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="b0300-121">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0300-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="b0300-122">Modificar el filtro de dirección URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0300-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

