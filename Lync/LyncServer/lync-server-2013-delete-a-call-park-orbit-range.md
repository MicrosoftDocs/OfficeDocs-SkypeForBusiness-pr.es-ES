---
title: Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013
TOCTitle: Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48275904
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-20_

Use uno de los siguientes procedimientos para eliminar un Estacionamiento de llamadas intervalo de órbitas.

## Para usar Panel de control de Lync Server para eliminar un intervalo de órbitas Estacionamiento de llamadas

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4.  En la página **Estacionamiento de llamadas**, en el campo de búsqueda, escriba la totalidad o parte del nombre de intervalo de órbitas que desea eliminar.

5.  En la lista de órbitas resultante, haga clic en la órbita, en **Editar** y, a continuación, en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Para usar Cmdlets para eliminar un intervalo de órbitas Estacionamiento de llamadas

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos escriba:
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    Por ejemplo:
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    

    > [!NOTE]
    > Para obtener más información acerca de las opciones, vea <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Vea también

#### Tareas

[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Otros recursos

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

