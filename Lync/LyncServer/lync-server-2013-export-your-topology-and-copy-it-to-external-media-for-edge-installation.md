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
ms.openlocfilehash: 5dd461e6a8ce184e5e418feddede258af68d2c25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528377"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Después de publicar la topología, el Asistente para la implementación de Lync Server necesita tener acceso a los datos del almacén de administración central para poder iniciar el proceso de implementación en el servidor. En la red interna, se puede obtener acceso a los datos desde los servidores, pero los servidores perimetrales que no se encuentran en el dominio interno no pueden obtener acceso a los datos. Para que los datos de configuración de la topología estén disponibles para una implementación de servidor perimetral, debe exportar los datos de la topología a un archivo y copiarlos en medios externos (por ejemplo, una unidad USB o un recurso compartido de red disponible desde el servidor perimetral) antes de ejecutar el Asistente para la implementación de Lync Server en el servidor perimetral. Siga el procedimiento indicado a continuación para hacer que sus datos de configuración de topología estén disponibles en el servidor perimetral que está implementando.

<div>


> [!NOTE]
> Después de instalar Lync Server 2013 en un servidor perimetral, se administra el servidor perimetral mediante las herramientas administrativas de la red interna, que replican automáticamente la configuración en los servidores perimetrales de la implementación. La única excepción es la asignación e instalación de certificados, así como la detención y el inicio de servicios que deben realizarse en el servidor perimetral.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Para hacer que los datos de la topología estén disponibles en un servidor perimetral mediante el Shell de administración de Communications Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  En el shell de administración de Lync Server, ejecute el siguiente cmdlet:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copie el archivo externo a medios externos (por ejemplo, una unidad USB o un recurso compartido de red disponible desde el servidor perimetral durante la implementación).

</div>

</div>

<span> </span>

</div>

</div>

</div>

