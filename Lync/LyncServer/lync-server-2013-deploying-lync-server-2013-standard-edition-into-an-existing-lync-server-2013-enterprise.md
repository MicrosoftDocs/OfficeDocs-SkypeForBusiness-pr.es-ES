---
title: 'Lync Server 2013: Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Implementar un servidor Standard Edition en una implementación existente de Enterprise Edition es similar a implementar roles de servidor adicionales. Es posible que se implemente un servidor Standard Edition en otro sitio, lo que permite a los usuarios de ese sitio estar alojados en el servidor Standard Edition en lugar del grupo de aplicaciones front-end en una red de área extensa (WAN). Los procedimientos para instalar el nuevo sitio y los servidores de ese sitio ya están definidos en otras secciones de la documentación de [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Para definir un sitio nuevo**

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **nuevo sitio central**.

3.  En la página **identificar el sitio** , asigne un nombre al sitio y, opcionalmente, escriba una descripción.

4.  Siga los procedimientos para definir el resto de la topología del sitio. Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publique la topología actualizada. Para obtener más información, vea [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configure e instale un servidor Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Si ha implementado un entorno con un servidor Standard Edition, debería haber iniciado el proceso de instalación desde el Asistente para la implementación de Lync Server mediante el vínculo <STRONG>preparar el primer servidor Standard Edition</STRONG> para instalar los archivos de base de datos iniciales en el nuevo Servidor Standard Edition. <STRONG>No</STRONG> siga ese proceso cuando instale un servidor Standard Edition en una implementación existente de Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

