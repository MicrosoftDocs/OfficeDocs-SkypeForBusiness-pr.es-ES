---
title: "Lync Server 2013: Publicar cambios pendientes en config. del enrutamiento de voz"
TOCTitle: Publicar los cambios pendientes en la configuración del enrutamiento de voz
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48277284
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-07_

Después de realizar algún cambio en cualquiera de las opciones de configuración de las páginas del grupo **Enrutamiento de voz**, siga este procedimiento para revisar, publicar o cancelar los cambios pendientes.

> [!IMPORTANT]  
> Compruebe que solo modifica las opciones de configuración de Enrutamiento de voz un usuario cada vez.<br />
Todos los cambios pendientes deben publicarse al mismo tiempo, ejecutando el comando <strong>Confirmar todo</strong>. No se pueden publicar los cambios pendientes de forma selectiva. Antes de publicar los cambios pendientes, ejecute el comando <strong>Revisar cambios sin confirmar</strong> y cancele los cambios de configuración que no desee publicar.<br />
> Si sale de las páginas del grupo <strong>Enrutamiento de voz</strong> antes de confirmar los cambios pendientes, se perderán todos los cambios pendientes. Sin embargo, puede exportar la configuración actual (incluidos los cambios pendientes) a un archivo de configuración de voz y, a continuación, importar y publicar la configuración actualizada. Para obtener información detallada, vea <a href="lync-server-2013-export-a-voice-route-configuration-file.md">Exportar un archivo de configuración de enrutamiento de voz en Lync Server 2013</a>.


## Para revisar, publicar o cancelar cambios de configuración de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  Realice los cambios de configuración que desee en las opciones de cada página del grupo **Enrutamiento de voz**.

5.  Para revisar los cambios pendientes sin publicarlos, seleccione **Revisar cambios sin confirmar** en el menú **Confirmar**.

6.  Si desea cancelar alguno de los cambios pendientes, realice una de las siguientes acciones:
    
      - Seleccione **Cancelar todos los cambios sin confirmar** en el menú **Confirmar**.
    
      - Navegue hasta la pestaña de la página de **Enrutamiento de voz** que tiene los cambios pendientes que desea cancelar, seleccione el elemento con cambios pendientes, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar cambios seleccionados**.

7.  Después de revisar todos los cambios pendientes y cancelar los que no desee publicar, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

8.  En el cuadro de diálogo **Configuración de voz no confirmada**, que muestra una lista de todos los cambios pendientes, haga clic en **Aceptar**.
    
    Cuando Panel de control de Lync Server haya confirmado los cambios, aparecerá el mensaje **Configuración de enrutamiento de voz publicada correctamente**.

