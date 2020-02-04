---
title: 'Lync Server 2013: Publicar una topología'
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
ms.openlocfilehash: 6bd80b5b3dfdb71a054c7600a06e892f1396f048
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Publicar una topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Cada vez que use el generador de topología para crear su topología, debe publicarla en una base de datos del almacén de administración central para que los datos puedan usarse para implementar Lync Server 2013. Use el siguiente procedimiento para publicar su topología.

<div>

## <a name="to-publish-the-topology"></a>Para publicar la topología

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topología, en el árbol de consola, haga clic con el botón secundario en **Lync 2013**y, a continuación, haga clic en **publicar topología**.

3.  En la página **principal** del asistente, haga clic en **Siguiente**.

4.  En el **generador de topologías, se encontró una** página de almacén de CMS, haga clic en **siguiente**.

5.  En la página **Crear otras bases de datos**, haga clic en **Siguiente**.

6.  Cuando el estado indica que la creación de la base de datos se realizó correctamente, haga lo siguiente:
    
      - Para visualizar el registro, haga clic en **Ver registro**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.
        
        <div>
        

        > [!IMPORTANT]  
        > Si se trata de una nueva instalación de un servidor perimetral o un grupo perimetral, debe exportar la configuración del servidor perimetral desde un servidor front-end existente, un grupo frontal o un servidor Standard Edition. Para exportar la configuración, vea <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar la topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral</A>. Deberá importar el archivo de configuración de los medios externos o de uso compartido de red durante la fase de configuración e implementación de los servidores perimetrales mediante el Asistente para la implementación de Lync Server.<BR>Una vez que los servidores perimetrales estén operativos y la base de datos del almacén de administración de configuración local se replique con la implementación interna, las actualizaciones posteriores de la configuración de Lync Server 2013 se publicarán y se replicarán en los servidores perimetrales.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

