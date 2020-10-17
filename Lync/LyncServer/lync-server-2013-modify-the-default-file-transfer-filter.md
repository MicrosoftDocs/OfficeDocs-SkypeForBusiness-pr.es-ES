---
title: 'Lync Server 2013: modificar el filtro de transferencia de archivos predeterminado'
description: 'Lync Server 2013: modificar el filtro de transferencia de archivos predeterminado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566936"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="cd43c-103">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd43c-103">Modify the default file transfer filter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd43c-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cd43c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cd43c-105">Lync Server 2013 proporciona un filtro de transferencia de archivos global que bloquea determinados tipos de archivos durante las siguientes actividades relacionadas con archivos dentro de la implementación de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="cd43c-105">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="cd43c-106">Solicitudes de transferencia de archivos durante las conversaciones de mensajería instantánea (mi)</span><span class="sxs-lookup"><span data-stu-id="cd43c-106">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="cd43c-107">Cargas y descargas de archivos al usar la característica de documentos en el cliente de Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="cd43c-107">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="cd43c-108">Reproducción multimedia durante las conferencias</span><span class="sxs-lookup"><span data-stu-id="cd43c-108">Multimedia playback during conferences</span></span>

<span data-ttu-id="cd43c-109">En función de los tipos de archivos que quiera bloquear o permitir, puede usar el panel de control de Lync Server para modificar el filtro global.</span><span class="sxs-lookup"><span data-stu-id="cd43c-109">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="cd43c-110">Para obtener más información sobre el filtrado de transferencia de archivos, consulte [configuración de transferencia de archivos y filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="cd43c-110">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="cd43c-111">Para modificar el filtro de transferencia de archivos predeterminado</span><span class="sxs-lookup"><span data-stu-id="cd43c-111">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="cd43c-112">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="cd43c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd43c-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd43c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd43c-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cd43c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd43c-115">En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro de archivo**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-115">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="cd43c-116">En la página **filtro de archivos** , haga doble clic en el filtro **global** .</span><span class="sxs-lookup"><span data-stu-id="cd43c-116">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="cd43c-117">En **Editar filtro de archivo**, active la casilla de verificación **Habilitar filtro de archivos** .</span><span class="sxs-lookup"><span data-stu-id="cd43c-117">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="cd43c-118">En el cuadro de lista desplegable **transferencia de archivos** , haga clic en **bloquear todos** o en **bloquear tipos de archivo específicos**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-118">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="cd43c-119">Si hizo clic en **bloquear todos**, vaya al paso 9.</span><span class="sxs-lookup"><span data-stu-id="cd43c-119">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="cd43c-120">Si hizo clic en **Bloquear tipos de archivos específicos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd43c-120">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="cd43c-121">Haga clic en **Seleccionar** para modificar la lista predeterminada de las extensiones de tipo de archivo que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="cd43c-121">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="cd43c-122">En **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desea bloquear o permitir agregando o quitando sus extensiones de las categorías de **extensiones de tipo de archivo**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-122">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="cd43c-123">Si no ve la extensión para un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-123">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="cd43c-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-124">Click **OK**.</span></span>

9.  <span data-ttu-id="cd43c-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cd43c-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd43c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd43c-126">See Also</span></span>


[<span data-ttu-id="cd43c-127">Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd43c-127">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="cd43c-128">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="cd43c-128">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="cd43c-129">Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="cd43c-129">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="cd43c-130">Modificar el filtro de direcciones URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd43c-130">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

