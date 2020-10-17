---
title: 'Lync Server 2013: configuración de directivas de sitio para archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e5ac47b0bd8c7668fa929fbc5f712ad8d396af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521797"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Configuración de directivas de sitio para archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Puede habilitar o deshabilitar el archivado de sitios específicos al crear y configurar una directiva de archivado para cada uno de esos sitios. Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio. Las directivas de archivado solo se aplican si no se usa la integración de Microsoft Exchange o si se usa la integración de Microsoft Exchange, pero hay algunos usuarios que no están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place retención.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.

<div>


> [!NOTE]  
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>Para crear una directiva de archivado para un sitio

1.  Desde una cuenta de usuario que se asigne a la función CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
    Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.

4.  Haga clic en  **Nuevo ** y en  **Directiva de sitio **.

5.  En  **Seleccionar un sitio **, haga clic en el sitio al que se va a aplicar la directiva.

6.  En  **Directiva de archivado nueva **, haga lo siguiente:
    
      - En  **Nombre **, especifique el nombre para la directiva de sitio.
    
      - En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).
    
      - Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla  **Archivar comunicaciones internas **.
    
      - Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla  **Archivar comunicaciones externas **.

7.  Haga clic en  **Confirmar **.

</div>

</div>

<span> </span>

</div>

</div>

</div>

