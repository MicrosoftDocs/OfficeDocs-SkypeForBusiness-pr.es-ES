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

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurar el almacenamiento de archivos DFS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-23_

Lync Server 2013 admite el uso de recursos compartidos de archivos en un sistema de archivos distribuido (DFS). Para obtener más información sobre DFS para Windows Server 2008, vea la guía paso a paso de DFS para Windows Server 2008 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)en. Para usar un DFS, Lync Server 2013 requiere lo siguiente:

  - Los espacios de nombres se basan en dominios

  - Todos los servidores de espacios de nombres ejecutan Windows 2008 o posterior

El programa de instalación de Lync Server 2013 requiere que los permisos de la carpeta compartida permitan el acceso total al administrador. Lync Server 2013, a continuación, usará los permisos de archivo NTFS para las carpetas ACL. Los permisos de recurso compartido DFS heredados no se usarán para restringir el acceso.

Para obtener más información sobre los requisitos de recursos compartidos de archivos, consulte [compatibilidad con el almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.

<div>


> [!NOTE]  
> Es posible que le interese información sobre la configuración de un recurso compartido no DFS. Si es así, consulte <A href="lync-server-2013-hardware-setup.md">configuración de hardware para Lync Server 2013</A>.



</div>

En el siguiente procedimiento se describe cómo configurar correctamente los permisos de carpeta compartida usando el Asistente de espacios de nombres DFS (como se describe en la guía de configuración de DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Procedimiento para configurar los permisos de carpeta compartida

1.  Haga clic en **Inicio**, señale **Todos los programas**, **Herramientas administrativas** y, a continuación, haga clic en **Administración de DFS**.

2.  En el árbol de consola del complemento Administración de DFS, haga clic con el botón secundario en el servidor de espacios de nombres (por ejemplo, filesrv1.contoso.com) y haga clic en **Editar configuración**.

3.  Seleccione **Permisos de carpeta compartida**.

4.  Seleccione **Usar permisos personalizados**.

5.  Para el grupo Administrador, seleccione lo siguiente en **Permitir**:
    
      - **Control completo**
    
      - **Cambio**
    
      - **Lectura**

6.  Haga clic en **Aplicar** y en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

