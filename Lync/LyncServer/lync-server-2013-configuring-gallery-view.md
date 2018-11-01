---
title: Configuración de la vista de galería
TOCTitle: Configuración de la vista de galería
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48275193
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la vista de galería

 

_**Última modificación del tema:** 2016-12-08_

En Lync Server 2013, configure la conferencia de vídeo de Vista Galería en la directiva de conferencias. La Vista Galería se activa de forma predeterminada. Si no desea permitir la Vista Galería o desea permitirla solo para algunos usuarios, deberá desactivar la función en la directiva de conferencias.

Cuando el vídeo de un participante en la conferencia no está disponible, la experiencia de Vista Galería de los usuarios puede mejorarse si implementa fotos en alta resolución, una nueva característica de Lync Server 2013. Las fotos de alta resolución ofrecen una alternativa a las fotos de contactos pequeñas con una resolución limitada almacenadas en Servicios de dominio de Active Directory. Las fotos de alta resolución se almacenan en el buzón de Exchange 2013 del usuario y, por tanto, necesitan que integre Lync Server 2013 con Exchange 2013. Para más información, vea el artículo de blog NextHop, "Integración de Exchange 2013 y Lync Server 2013" en [http://go.microsoft.com/fwlink/?linkid=260987\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=260987%26clcid=0xc0a).


> [!NOTE]
> El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.



Puede ver o modificar los parámetros de la Vista Galería con Panel de control de Lync Server 2013 o usando uno de los cmdlets siguientes:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configure Vista Galería con los siguientes parámetros de directiva de conferencia:

  - **AllowMultiview**    Este parámetro controla si un usuario puede organizar las conferencias de vídeo de la Vista Galería. Este parámetro se aplica a reuniones programadas y ad-hoc creadas por el usuario.
    
    Ejemplos:
    
      - Este parámetro se establece en True para usuario A, que se aloja en un grupo de Lync Server 2013. Las reuniones organizadas por el usuario A permiten a los usuarios unirse y recibir múltiples secuencias de vídeo.
    
      - Este parámetro se establece en False para el usuario B, que se aloja en un grupo Lync Server 2013. Las reuniones organizadas por el usuario B tienen una secuencia de vídeo única que es similar a la experiencia de conferencia de vídeo proporcionada por Lync Server 2010.
    
    Este parámetro determina quién puede organizar reuniones que permiten múltiples secuencias de vídeo. Los participantes en las reuniones que permiten múltiples secuencias de vídeo pueden o no puede recibir múltiples secuencias de vídeo, basándose en sus permisos individuales (vea la descripción del parámetro EnableMultiviewJoin).

  - **EnableMultiviewJoin**   Este parámetro controla si un participante en una reunión recibe la experiencia de vídeo de Vista Galería en reuniones que lo permitan. Este parámetro controla la experiencia del usuario en cualquier reunión en la que él o ella participe.
    
    Ejemplos:
    
      - Este parámetro se establece en True para el usuario C. El usuario C puede recibir múltiples secuencias de vídeo cuando participa en una reunión organizada o iniciada por el usuario A. El usuario C recibe una secuencia de vídeo única que es similar a la experiencia de conferencia de vídeo proporcionada por Lync Server 2010 al participar en una reunión organizada o iniciada por el usuario B.
    
      - Este parámetro se establece en False para el usuario D. El usuario D una única secuencia de vídeo que es similar a la experiencia de conferencia de vídeo proporcionada por Lync Server 2010 al participar en cualquier reunión organizada o iniciada por el usuario A o el usuario B.

El procedimiento siguiente es un ejemplo del uso de Shell de administración de Lync Server para habilitar la conferencia de vídeo de Vista Galería.

## Para modificar la directiva de conferencias para conferencias de de vídeo de Vista Galería

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true

