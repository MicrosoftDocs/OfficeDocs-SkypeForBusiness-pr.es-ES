---
title: 'Lync Server 2013: eliminar regiones de red existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Eliminar regiones de red existentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Lync Server para configurar regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. En el panel de control de Lync Server, puede crear, modificar o eliminar una región de red. Use este tema para eliminar regiones de red existentes. Para obtener detalles sobre cómo crear o modificar regiones de red existentes, vea [crear o modificar regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Para eliminar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **región**.

4.  En la página **región** , haga clic en la región que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puedes eliminar más de una región a la vez. Para ello, presione CTRL y seleccione varias regiones mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las regiones, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.
    
    <div>
    

    > [!WARNING]  
    > No se puede quitar una región de red si está asociada a un sitio de red. Si intenta quitar una región asociada a un sitio, recibirá un mensaje de error. Para ver si una región está asociada a algún sitio, seleccione la región y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar regiones de red en Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

