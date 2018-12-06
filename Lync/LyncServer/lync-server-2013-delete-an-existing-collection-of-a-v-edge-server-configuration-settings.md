---
title: "Eliminar conjunto existente de opciones de configuración del servidor perimetral A/V"
TOCTitle: "Suppr. d’une collection existante de par. de conf. d’un serveur Edge A/V"
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49889210
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un conjunto existente de opciones de configuración del servidor perimetral A/V

 

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).

Al instalar Lync Server, se crea automáticamente una colección global de opciones de configuración de servidor perimetral A/V. Esta colección no se puede eliminar, pero puede se usar el Shell de administración de Lync Server y el cmdlet Remove-CsAVEdgeConfiguration para "restablecerla"; esto quiere decir, sencillamente, que todos los valores de propiedad de la colección global se volverán a su valor predeterminado original. Así, por ejemplo, si ha establecido la propiedad MaxTokenLifetime en 16 horas, se restablecerá a su valor predeterminado, que es de 8 horas.

En cambio, las colecciones de opciones de configuración personalizadas que haya creado (ya sea en el ámbito de sitio o de servicio) se pueden eliminar con el cmdlet Remove-CsAVEdgeConfiguration. Si elimina la configuración de sitio, los servidores perimetrales A/V de dicho sitio pasarán a administrarse mediante la configuración global y, si elimina la configuración de servicio, el servidor se administrará por medio de su configuración de sitio (si la hay) o por la configuración global (en caso de que no haya configuración de sitio disponible).

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration).

## Restablecer la colección global

  - Con el siguiente comando se restablece la colección global de la configuración de servidor perimetral A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

## Quitar una colección del ámbito de sitio

  - Con este comando se quita la configuración de servidor perimetral A/V que se ha usado en el sitio de Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

## Quitar una colección del ámbito de servicio

  - Con este comando se quita la configuración utilizada en el servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Vea también

#### Tareas

[Devolución de información de configuración del servidor perimetral de A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Creación o modificación de conjuntos de opciones de configuración del servidor perimetral A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  

#### Otros recursos

[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)

