---
title: "Suppr. des paramètres de configuration de la qualité de l’expérience (QoE)"
TOCTitle: "Suppr. des paramètres de configuration de la qualité de l’expérience (QoE)"
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48277294
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de opciones de configuración de la calidad de la experiencia

 

_**Última modificación del tema:** 2013-02-23_

Las métricas de calidad de la experiencia (QoE) controlan la calidad de las llamadas de audio y vídeo realizadas en la organización y aborda aspectos como el número de paquetes de red que se pierden, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de los paquetes). Estas métricas se almacenan en una base de datos aparte de otros datos (como los registros de los detalles de las llamadas), lo cual permite habilitar y deshabilitar la calidad de la experiencia con independencia de otras grabaciones de datos.

Al instalar Microsoft Lync Server 2013, se crea un único conjunto global de opciones de configuración de QoE. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global. Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio mediante la configuración global.

Tenga en cuenta que también puede "eliminar" la configuración global. Sin embargo, las configuraciones globales no se quitan realmente, sino que todas las propiedades de ese conjunto se restablecen a los valores predeterminados. Por ejemplo, de manera predeterminada, la depuración está habilitada en un conjunto de configuraciones de QoE. Supongamos que modifica el conjunto global y que deshabilita la depuración. Si después elimina la configuración global, todas las propiedades se restablecerán a los valores predeterminados y, en este caso, eso significa habilitar de nuevo la depuración.

Puede quitar la configuración de QoE usando Panel de control de Lync Server o mediante el cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration).

## Para eliminar la configuración de QoE usando Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Datos de calidad de experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.

5.  Haga clic en **Aceptar**.

## Para quitar la configuración de QoE usando los cmdlets de Shell de administración de Lync Server

También puede eliminar al configuración de QoE usando Shell de administración de Lync Server y el cmdlet **Remove-CsQoEConfiguration**. Puede ejecutar este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar un conjunto concreto de configuraciones de QoE

  - Este comando quita la configuración de QoE aplicada al sitio Redmond:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

## Para quitar todas las opciones de configuración de QoE aplicadas al ámbito de sitio

  - Este comando quita todas las opciones de configuración de QoE aplicadas al ámbito de sitio:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

## Para quitar todas las opciones de configuración de QoE en las que se ha deshabilitado la supervisión de QoE

  - Este comando quita todas las opciones de configuración de QoE donde se ha deshabilitado la supervisión de QoE:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

Para obtener información detallada, vea [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration).

