---
title: 'Lync Server 2013: implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente'
description: 'Lync Server 2013: implementar Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b233d4e782e716904fca0a2a146b2459e906aa57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571726"
---
# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Implementación de Lync Server 2013 Standard Edition en una empresa existente de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La implementación de un servidor Standard Edition en una implementación de Enterprise Edition existente es similar a la implementación de roles de servidor adicionales. Es posible que se implemente un servidor Standard Edition en otro sitio, lo que permite a los usuarios de ese sitio hospedarse en el servidor Standard Edition en lugar del grupo de servidores front-end en una red de área extensa (WAN). Los procedimientos para instalar el nuevo sitio y los servidores de ese sitio ya están definidos en otras secciones de la documentación sobre la [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Para definir un sitio nuevo**

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **nuevo sitio central**.

3.  En la página **Identificar el sitio**, escriba un nombre para el sitio y, opcionalmente, una descripción.

4.  Siga los procedimientos de definición del resto de la topología del sitio. Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publicar la topología actualizada. Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configurar e instalar un servidor Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Si ha implementado un entorno con un servidor Standard Edition, habría iniciado el proceso de instalación desde el Asistente para la implementación de Lync Server mediante el vínculo <STRONG>preparar el primer servidor Standard Edition</STRONG> para instalar los archivos de base de datos iniciales en el nuevo servidor Standard Edition. <STRONG>No</STRONG> siga ese proceso cuando instale un servidor Standard Edition en una implementación existente de Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

