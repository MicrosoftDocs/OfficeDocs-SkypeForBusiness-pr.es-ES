---
title: 'Lync Server 2013: modificar el filtro de transferencia de archivos predeterminado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="e0f86-102">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f86-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f86-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e0f86-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e0f86-104">Lync Server 2013 proporciona un filtro de transferencia de archivos global que bloquea determinados tipos de archivos durante las siguientes actividades relacionadas con archivos dentro de la implementación de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e0f86-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="e0f86-105">Solicitudes de transferencia de archivos durante conversaciones de mensajería instantánea (mi)</span><span class="sxs-lookup"><span data-stu-id="e0f86-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="e0f86-106">Cargas y descargas de archivos al usar la característica de documentos en el cliente de Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="e0f86-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="e0f86-107">Reproducción multimedia durante las conferencias</span><span class="sxs-lookup"><span data-stu-id="e0f86-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="e0f86-108">En función de los tipos de archivos que desea bloquear o permitir, puede usar el panel de control de Lync Server para modificar el filtro global.</span><span class="sxs-lookup"><span data-stu-id="e0f86-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="e0f86-109">Para más información sobre el filtrado de transferencia de archivos, vea [configuración de la transferencia de archivos y filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="e0f86-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="e0f86-110">Para modificar el filtro de transferencia de archivos predeterminado</span><span class="sxs-lookup"><span data-stu-id="e0f86-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="e0f86-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e0f86-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e0f86-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f86-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e0f86-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e0f86-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0f86-114">En la barra de navegación izquierda, haga clic en **mensajería instantánea y presencia** y, a continuación, haga clic en **filtro de archivos**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="e0f86-115">En la página **filtro de archivos** , haga doble clic en el filtro **global** .</span><span class="sxs-lookup"><span data-stu-id="e0f86-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="e0f86-116">En **filtro de archivo de edición**, active la casilla de verificación **Habilitar filtro de archivos** .</span><span class="sxs-lookup"><span data-stu-id="e0f86-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="e0f86-117">En el cuadro de lista desplegable **transferencia de archivos** , haga clic en **bloquear todos** o **bloquear tipos de archivo específicos**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="e0f86-118">Si hizo clic en **bloquear todo**, vaya al paso 9.</span><span class="sxs-lookup"><span data-stu-id="e0f86-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="e0f86-119">Si hizo clic en **bloquear tipos de archivo específicos**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="e0f86-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="e0f86-120">Haga clic en **seleccionar** para modificar la lista predeterminada de extensiones de tipo de archivo que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="e0f86-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="e0f86-121">En **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desea bloquear o permitir agregando o quitando sus extensiones de las categorías de **extensiones de tipo de archivo**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="e0f86-122">Si no ve la extensión de un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="e0f86-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-123">Click **OK**.</span></span>

9.  <span data-ttu-id="e0f86-124">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e0f86-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0f86-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f86-125">See Also</span></span>


[<span data-ttu-id="e0f86-126">Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f86-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="e0f86-127">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="e0f86-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="e0f86-128">Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e0f86-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="e0f86-129">Modificar el filtro de dirección URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f86-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

