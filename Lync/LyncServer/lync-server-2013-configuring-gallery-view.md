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
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configuración de la vista de galería en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En Lync Server 2013, se configura la Conferencia de vídeo de vista de galería en la Directiva de conferencia. La Vista Galería se activa de forma predeterminada. Si no desea permitir la Vista Galería o desea permitirla solo para algunos usuarios, deberá desactivar la función en la directiva de conferencias.

Cuando el vídeo de un participante de la Conferencia no está disponible, la experiencia de visualización de la galería de los usuarios se puede mejorar si implementa fotos de alta resolución, una nueva característica en Lync Server 2013. Las fotos de alta resolución proporcionan una alternativa a las fotos de contacto de resolución limitada más pequeñas y de menor tamaño almacenadas en los servicios de dominio de Active Directory. Las fotos de alta resolución se almacenan en el buzón de correo de Exchange 2013 del usuario y, por lo tanto, requieren la integración de Lync Server 2013 con Exchange 2013. Para obtener información detallada, consulte el artículo del blog NextHop, "integración de Exchange 2013 y Lync Server [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)2013", en.

<div>


> [!NOTE]  
> El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.



</div>

Puede ver o modificar los parámetros de la vista de galería mediante el panel de control de Lync Server 2013 o mediante uno de los siguientes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configure Vista Galería con los siguientes parámetros de directiva de conferencia:

  - **AllowMultiview**   este parámetro controla si un usuario puede organizar las videoconferencias de vista de galería. Este parámetro se aplica a reuniones programadas y ad-hoc creadas por el usuario.
    
    Ejemplos:
    
      - Este parámetro se establece en true para el usuario A, que está hospedado en un grupo de servidores de Lync Server 2013. Las reuniones organizadas por el usuario A permiten a los usuarios unirse y recibir múltiples secuencias de vídeo.
    
      - Este parámetro se establece en false para el usuario B, que está hospedado en un grupo de servidores de Lync Server 2013. Las reuniones organizadas por el usuario B tienen una única secuencia de vídeo similar a la experiencia de conferencia de vídeo que proporciona Lync Server 2010.
    
    Este parámetro determina quién puede organizar reuniones que permiten múltiples secuencias de vídeo. Los participantes en las reuniones que permiten múltiples secuencias de vídeo pueden o no puede recibir múltiples secuencias de vídeo, basándose en sus permisos individuales (vea la descripción del parámetro EnableMultiviewJoin).

  - **EnableMultiviewJoin**   este parámetro controla si un participante de una reunión recibe la experiencia de vídeo de la vista de galería en las reuniones que la permiten. Este parámetro controla la experiencia del usuario en cualquier reunión en la que él o ella participe.
    
    Ejemplos:
    
      - Este parámetro se establece en true para el usuario C. el usuario c puede recibir varias secuencias de vídeo cuando participa en una reunión organizada o iniciada por el usuario A. el usuario C recibe una única secuencia de vídeo que es similar a la experiencia de la Conferencia de vídeo que proporciona Lync Server 2010 cuando participar en una reunión organizada o iniciada por el usuario B.
    
      - Este parámetro se establece en false para el usuario D. el usuario D recibe una única secuencia de vídeo similar a la experiencia de videoconferencia que proporciona Lync Server 2010 cuando participa en cualquier reunión organizada por el usuario A o el usuario B.

El siguiente procedimiento es un ejemplo del uso del shell de administración de Lync Server para habilitar la Conferencia de vídeo de vista de galería.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Para modificar la directiva de conferencias para conferencias de de vídeo de Vista Galería

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

