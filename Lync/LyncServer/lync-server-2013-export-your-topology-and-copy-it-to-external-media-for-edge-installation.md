---
title: Exportar la topología y copiarla en un medio externo para la instalación perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Después de publicar su topología, el Asistente para la implementación de Lync Server necesita acceso a los datos del almacén central de administración para iniciar el proceso de implementación en el servidor. En la red interna, los datos están disponibles directamente desde los servidores, pero los servidores perimetrales que no se encuentran en el dominio interno no tienen acceso a los datos. Para que los datos de configuración de topología estén disponibles para una implementación de servidor perimetral, debe exportar los datos de la topología a un archivo y copiarlos en medios externos (por ejemplo, una unidad USB o un recurso compartido de red que esté disponible desde el servidor perimetral) antes de ejecutar el servidor de DEP de Lync Server Asistente para loyment en el servidor perimetral. Use el siguiente procedimiento para que los datos de configuración de su topología estén disponibles en el servidor perimetral que va a implementar.

<div>


> [!NOTE]
> Después de instalar Lync Server 2013 en un servidor perimetral, administra el servidor perimetral con las herramientas administrativas de la red interna, que automáticamente replican la configuración en los servidores perimetrales de la implementación. La única excepción es asignar e instalar certificados e detener e iniciar servicios, ambos deben realizarse en el servidor perimetral.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Para hacer que los datos de su topología estén disponibles en un servidor perimetral mediante el shell de administración de Lync Server

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En el shell de administración de Lync Server, ejecute el siguiente cmdlet:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copie el archivo exportado a un medio externo (por ejemplo, una unidad USB o un recurso compartido de red que esté disponible desde el servidor perimetral durante la implementación).

</div>

</div>

<span> </span>

</div>

</div>

</div>

