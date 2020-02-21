---
title: 'Lync Server 2013: publicación de la topología actualizada'
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
ms.openlocfilehash: 7b978d7a8d2cf05d4e9fa1b0a224bbef50e3fd7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Publicar la topología actualizada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Después de actualizar la topología en el generador de topologías, debe publicar la topología en el almacén de administración central para poder configurar y usar el servidor de chat persistente. Las copias de solo lectura de los datos se replican a todos los servidores de la topología para que todos los servidores permanezcan sincronizados con la topología y otros cambios de configuración.

<div>

## <a name="to-publish-an-updated-topology"></a>Para publicar una topología actualizada

Antes de publicar la topología, instale las bases de datos para el servidor de chat persistente. Use el generador de topologías para instalar las bases de datos seleccionando **acción** e **instalar base de datos**.

1.  En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo **administradores de dominio** y del grupo **RTCUniversalServerAdmins** y que tiene permisos de control total (es decir, de lectura, escritura y modificación) en el almacén de archivos que se va a usar para el almacén de archivos del servidor de chat persistente (de modo que el generador de topologías pueda configurar las listas de control de acceso discrecional (DACL) necesarias) o una cuenta con derechos de usuario equivalentes.

2.  Inicie el Generador de topologías. Seleccione **Descargar topología de la implementación existente**o **abrir topología desde un archivo local** si lo guardó localmente.

3.  En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.

4.  En la página **Publicar topología**, haga clic en **Siguiente**.

5.  En la página **Asistente de publicación completado**, compruebe que la topología se haya publicado correctamente y, a continuación, haga clic en **Finalizar**.
    
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

