---
title: Eliminar un intervalo numérico de respuesta de llamadas en grupo
TOCTitle: Eliminar un intervalo numérico de respuesta de llamadas en grupo
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945629(v=OCS.15)
ms:contentKeyID: 52061686
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un intervalo numérico de respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2013-01-30_

Use el siguiente procedimiento para eliminar un intervalo de números del grupo de atención de llamadas.

## Para eliminar un intervalo de números del grupo de atención de llamadas

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, escriba:
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    Por ejemplo:
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    

    > [!NOTE]
    > Para obtener información detallada sobre otras opciones, consulte <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Vea también

#### Tareas

[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Otros recursos

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

