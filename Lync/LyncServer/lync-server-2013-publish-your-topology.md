---
title: 'Lync Server 2013: publicar la topología'
description: 'Lync Server 2013: publique la topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571756"
---
# <a name="publish-your-topology-in-lync-server-2013"></a>Publicar la topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Cada vez que use el generador de topologías para compilar la topología, debe publicar la topología en una base de datos en el almacén de administración central para que los datos puedan usarse para implementar Lync Server 2013. Siga el procedimiento indicado a continuación para publicar la topología.

<div>

## <a name="to-publish-the-topology"></a>Para publicar la topología

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el generador de topologías, en el árbol de la consola, haga clic con el botón secundario en **Lync 2013**y, a continuación, haga clic en **publicar topología**.

3.  En la página **principal** del Asistente, haga clic en **Siguiente**.

4.  En la página **Generador de topologías ha encontrado un almacén de administración de configuración**, haga clic en **Siguiente**.

5.  En la página **Crear otras bases de datos**, haga clic en **Siguiente**.

6.  Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:
    
      - Para visualizar el registro, haga clic en **Ver registro**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.
        
        <div>
        

        > [!IMPORTANT]  
        > Si se trata de una nueva instalación de un servidor perimetral o un grupo de servidores perimetrales, debe exportar la configuración del servidor perimetral desde un servidor front-end existente, un grupo de servidores front-end o un servidor Standard Edition. Para exportar la configuración, consulte <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</A>. Importará el archivo de configuración desde el medio externo o el recurso compartido de red durante la fase de instalación e implementación de los servidores perimetrales mediante el Asistente para la implementación de Lync Server.<BR>Una vez que los servidores perimetrales están operativos y la base de datos de almacenamiento de administración de configuración local se replica con la implementación interna, las actualizaciones posteriores de la configuración de Lync Server 2013 se publicarán y replicarán en los servidores perimetrales.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

