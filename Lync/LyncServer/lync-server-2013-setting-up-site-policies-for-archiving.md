---
title: 'Lync Server 2013: configuración de directivas del sitio para archivar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Configurar directivas de sitio para archivar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Puede habilitar o deshabilitar el archivado de sitios específicos creando y configurando una directiva de archivado para cada uno de esos sitios. Las directivas de sitio invalidan las directivas globales, pero las directivas de usuario invalidan las directivas de sitio. Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están alojados en Exchange 2013 y tienen sus buzones en conservación local.

Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .

<div>


> [!NOTE]  
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Es necesario que especifique todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>Para crear una directiva de archivado para un sitio

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013.

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
    Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .

4.  Haga clic en **Nuevo** y en **Directiva de sitio**.

5.  En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva.

6.  En **Directiva de archivado nueva**, haga lo siguiente:
    
      - En **Nombre**, especifique el nombre para la directiva de sitio.
    
      - En **Descripción**, proporcione información sobre la directiva de sitio (por ejemplo, directiva de sitio para Redmond).
    
      - Para controlar el archivado de las comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de las comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas**.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

