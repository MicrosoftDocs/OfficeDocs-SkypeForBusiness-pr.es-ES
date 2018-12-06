---
title: Eliminar un intervalo numérico sin asignar en Lync Server 2013
TOCTitle: Eliminar un intervalo numérico sin asignar en Lync Server 2013
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48276286
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un intervalo numérico sin asignar en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Siga uno de los procedimientos que se indican a continuación para eliminar un intervalo de números sin asignar para anuncios.

## Para usar Panel de control de Lync Server de cara a eliminar un intervalo de números sin asignar

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.

4.  En la página **Número sin asignar**, en el campo de búsqueda, escriba la totalidad o parte del nombre del intervalo del número sin asignar que desee eliminar.

5.  En la lista resultante de rangos de números, haga clic en el nombre, en **Editar** y, a continuación, en **Eliminar**.

6.  Haga clic en **Confirmar todo**.

## Para usar cmdlets de cara a eliminar un intervalo de números sin asignar

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, escriba lo siguiente:
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Por ejemplo:
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    

    > [!NOTE]
    > Para obtener información detallada sobre otras opciones, consulte <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Vea también

#### Tareas

[Crear o modificar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### Otros recursos

[Remove-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

