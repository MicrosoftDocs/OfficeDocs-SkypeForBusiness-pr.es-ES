---
title: 'Lync Server 2013: aplicar una directiva de archivado de Lync Server a un usuario'
description: 'Lync Server 2013: aplicar una directiva de archivado de Lync Server a un usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69dcca5601185d65735b963673322a0630af6ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544996"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Aplicar una directiva de archivado de Lync Server a un usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Después de crear una directiva de usuario de Lync Server, debe aplicarla a los usuarios o grupos de usuarios hospedados en Lync Server 2013 para que puedan surtir efecto. Para obtener información detallada sobre cómo crear directivas de usuario para usuarios específicos, vea [crear y configurar directivas de usuario para archivado en Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) en la documentación sobre implementación.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la documentación sobre la implementación o las operaciones.

<div>


> [!NOTE]  
> Para poder configurar y usar el archivado, primero debe implementar el archivado. Para obtener más información, consulte <A href="lync-server-2013-deploying-archiving.md">implementación del archivado en Lync Server 2013</A> en la documentación sobre implementación.<BR>Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Para aplicar una directiva de archivado de Lync Server a un usuario

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La configuración <STRONG> &lt; automática &gt; </STRONG> aplica la configuración de la instalación del servidor predeterminada. Esta configuración se aplica automáticamente por el servidor.

    
    </div>

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

