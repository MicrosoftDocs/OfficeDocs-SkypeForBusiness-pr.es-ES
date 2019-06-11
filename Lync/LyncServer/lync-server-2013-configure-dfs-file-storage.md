---
title: 'Lync Server 2013: Configurar el almacenamiento de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurar el almacenamiento de archivos para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-23_

Lync Server 2013 admite el uso de recursos compartidos de archivos en un sistema de archivos distribuido (DFS). Para obtener más información sobre DFS para Windows Server 2008, consulte la guía paso a paso de DFS para Windows Server 2008 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)en. Para usar un DFS, Lync Server 2013 requiere lo siguiente:

  - Los espacios de nombres se basan en dominios

  - Todos los servidores de espacio de nombres se ejecutan con un mínimo de Windows 2008

El programa de instalación de Lync Server 2013 requiere que los permisos para la carpeta compartida permitan el acceso total al administrador. Lync Server 2013 usará permisos de archivo NTFS para las ACL de las carpetas. Los permisos de recursos compartidos DFS heredados no se usarán para restringir el acceso.

Para obtener más información sobre los requisitos de uso compartido de archivos, consulte [compatibilidad de almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación de soporte técnico.

<div>


> [!NOTE]  
> Es posible que esté buscando información sobre cómo configurar un recurso compartido no DFS. Si es así, consulte <A href="lync-server-2013-hardware-setup.md">configuración de hardware para Lync Server 2013</A>.



</div>

El procedimiento siguiente describe cómo configurar correctamente los permisos de carpetas compartidas mediante el Asistente para espacio de nombres DFS (como se describe en la guía de configuración de DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Para configurar permisos de carpetas compartidas

1.  Haga clic en **Inicio**, elija **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de DFS**.

2.  En el árbol de consola del complemento Administración de DFS, haga clic con el botón secundario en el servidor de espacio de nombres (por ejemplo, filesrv1.contoso.com) y, a continuación, haga clic en **Editar configuración**.

3.  Seleccione **permisos de carpetas**compartidas.

4.  Seleccione **usar permisos personalizados**.

5.  En el grupo administrador, seleccione las siguientes opciones en **permitir**:
    
      - **Control total**
    
      - **Cambio**
    
      - **Consulte**

6.  Haga clic en **aplicar**y, a continuación, en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

