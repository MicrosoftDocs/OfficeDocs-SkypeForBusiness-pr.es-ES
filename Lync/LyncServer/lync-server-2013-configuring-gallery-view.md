---
title: 'Lync Server 2013: configuración de la vista de Galería'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configuración de la vista de galería en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En Lync Server 2013, se configura la vista Galería de videoconferencias en Directiva de conferencia. La vista Galería está activada de forma predeterminada. Si no desea permitir la vista Galería, o desea permitir solo a algunos usuarios, debe desactivar la característica en Directiva de conferencia.

Cuando el vídeo de un participante de la Conferencia no está disponible, la experiencia de la vista de galería de los usuarios puede mejorarse si implementa fotos de alta resolución, una nueva característica de Lync Server 2013. Las fotos de alta resolución proporcionan una alternativa a las fotos de contacto de menor tamaño y limitada almacenadas en servicios de dominio de Active Directory. Las fotos de alta resolución se almacenan en el buzón de correo de Exchange 2013 de un usuario y, por lo tanto, requieren la integración de Lync Server 2013 con Exchange 2013. Para obtener más información, vea el artículo del blog de NextHop, "integración de Exchange 2013 y Lync [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Server 2013" en.

<div>


> [!NOTE]  
> El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.



</div>

Puede ver o modificar los parámetros de la vista de galería mediante el panel de control de Lync Server 2013 o mediante uno de los siguientes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurar la vista de galería con la siguiente configuración de directiva de Conferencia:

  - **AllowMultiview**   este parámetro controla si un usuario puede organizar las videoconferencias en la galería de imágenes. Este parámetro se aplica a las reuniones programadas y ad hoc creadas por el usuario.
    
    Acerca
    
      - Este parámetro se establece en true para el usuario A, que está alojado en un grupo de servidores de Lync Server 2013. Las reuniones organizadas por el usuario a permiten a los usuarios unirse y recibir varias transmisiones de vídeo.
    
      - Este parámetro se establece en false para el usuario B, que está alojado en un grupo de servidores de Lync Server 2013. Las reuniones organizadas por el usuario B tienen una sola secuencia de vídeo similar a la de la videoconferencia proporcionada por Lync Server 2010.
    
    Este parámetro determina quién puede organizar reuniones que permitan varias secuencias de vídeo. Los participantes de las reuniones que permitan varias transmisiones de vídeo pueden o no pueden recibir varias secuencias de vídeo, en función de sus permisos individuales (consulte la descripción del parámetro EnableMultiviewJoin).

  - **EnableMultiviewJoin**   este parámetro controla si un participante de una reunión recibe la experiencia de vídeo de la vista de galería en las reuniones que lo permiten. Este parámetro controla la experiencia del usuario en cualquier reunión en la que participe.
    
    Acerca
    
      - Este parámetro se establece en true para el usuario C. el usuario C puede recibir varias transmisiones de vídeo al participar en una reunión organizada o iniciada por el usuario A. el usuario C recibe una única secuencia de vídeo que es similar a la experiencia en videoconferencias proporcionada por Lync Server 2010 cuando participar en una reunión organizada o iniciada por el usuario B.
    
      - Este parámetro se establece en false para el usuario D. el usuario D recibe una única secuencia de vídeo que es similar a la experiencia en videoconferencias proporcionada por Lync Server 2010 cuando participa en una reunión organizada por el usuario A o el usuario B.

El siguiente procedimiento es un ejemplo del uso del shell de administración de Lync Server para habilitar las videoconferencias en la galería.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Para modificar la Directiva de conferencia de la Galería ver videoconferencias

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para editar la Directiva de Conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

