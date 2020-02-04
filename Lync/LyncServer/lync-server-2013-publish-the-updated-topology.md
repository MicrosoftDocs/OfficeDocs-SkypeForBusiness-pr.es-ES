---
title: 'Lync Server 2013: Publicar la topología actualizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Publicar la topología actualizada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Después de actualizar su topología en el generador de topología, debe publicarla en el almacén de administración central para poder configurar y usar el servidor de chat persistente. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.

<div>

## <a name="to-publish-an-updated-topology"></a>Para publicar una topología actualizada

Antes de publicar su topología, instale las bases de datos para el servidor de chat persistente. Use el generador de topología para instalar bases de datos seleccionando **acción** e **instalar base de datos**.

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo **administradores de dominio** y el grupo **RTCUniversalServerAdmins** . y que tiene permisos de control total (es decir, leer, escribir y modificar) en el almacén de archivos para usarlos en el almacén de archivos del servidor de chat persistente (para que el generador de topología pueda configurar las listas de control de acceso discrecional (DACL) obligatorias) o una cuenta con derechos de usuario equivalentes.

2.  Iniciar el generador de topología. Seleccione **Descargar topología de una implementación existente**o **abra topología desde un archivo local** si la ha guardado de forma local.

3.  En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Después de publicar la topología, debe configurar la compatibilidad con el servidor de chat persistente antes de que se pueda archivar contenido.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

