---
title: 'Lync Server 2013: configurar el almacenamiento de archivos DFS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a9c0bbce2ced36e9df99d7239c2f562b20edbd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="c1ae3-102">Configurar el almacenamiento de archivos DFS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1ae3-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1ae3-103">_**Última modificación del tema:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="c1ae3-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="c1ae3-104">Lync Server 2013 admite el uso de recursos compartidos de archivos en un sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="c1ae3-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="c1ae3-105">Para obtener más información sobre DFS para Windows Server 2008, vea la guía paso a paso de DFS para Windows Server 2008 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)en. Para usar un DFS, Lync Server 2013 requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1ae3-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="c1ae3-106">Los espacios de nombres se basan en dominios</span><span class="sxs-lookup"><span data-stu-id="c1ae3-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="c1ae3-107">Todos los servidores de espacios de nombres ejecutan Windows 2008 o posterior</span><span class="sxs-lookup"><span data-stu-id="c1ae3-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="c1ae3-108">El programa de instalación de Lync Server 2013 requiere que los permisos de la carpeta compartida permitan el acceso total al administrador.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="c1ae3-109">Lync Server 2013, a continuación, usará los permisos de archivo NTFS para las carpetas ACL.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="c1ae3-110">Los permisos de recurso compartido DFS heredados no se usarán para restringir el acceso.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="c1ae3-111">Para obtener más información sobre los requisitos de recursos compartidos de archivos, consulte [compatibilidad con el almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1ae3-112">Es posible que le interese información sobre la configuración de un recurso compartido no DFS.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="c1ae3-113">Si es así, consulte <A href="lync-server-2013-hardware-setup.md">configuración de hardware para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c1ae3-114">En el siguiente procedimiento se describe cómo configurar correctamente los permisos de carpeta compartida usando el Asistente de espacios de nombres DFS (como se describe en la guía de configuración de DFS).</span><span class="sxs-lookup"><span data-stu-id="c1ae3-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="c1ae3-115">Procedimiento para configurar los permisos de carpeta compartida</span><span class="sxs-lookup"><span data-stu-id="c1ae3-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="c1ae3-116">Haga clic en **Inicio**, señale **Todos los programas**, **Herramientas administrativas** y, a continuación, haga clic en **Administración de DFS**.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="c1ae3-117">En el árbol de consola del complemento Administración de DFS, haga clic con el botón secundario en el servidor de espacios de nombres (por ejemplo, filesrv1.contoso.com) y haga clic en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="c1ae3-118">Seleccione **Permisos de carpeta compartida**.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="c1ae3-119">Seleccione **Usar permisos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="c1ae3-120">Para el grupo Administrador, seleccione lo siguiente en **Permitir**:</span><span class="sxs-lookup"><span data-stu-id="c1ae3-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="c1ae3-121">**Control completo**</span><span class="sxs-lookup"><span data-stu-id="c1ae3-121">**Full Control**</span></span>
    
      - <span data-ttu-id="c1ae3-122">**Cambio**</span><span class="sxs-lookup"><span data-stu-id="c1ae3-122">**Change**</span></span>
    
      - <span data-ttu-id="c1ae3-123">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="c1ae3-123">**Read**</span></span>

6.  <span data-ttu-id="c1ae3-124">Haga clic en **Aplicar** y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1ae3-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

