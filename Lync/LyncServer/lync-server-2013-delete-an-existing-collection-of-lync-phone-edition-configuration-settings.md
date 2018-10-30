---
title: "Eliminar un conjunto existente de opciones de configuración de Lync Phone Edition"
TOCTitle: "Suppr. d’une collection existante de par. de configuration Lync Phone Edition"
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49888909
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un conjunto existente de opciones de configuración de Lync Phone Edition

 

_**Última modificación del tema:** 2013-02-23_

Si ya no desea utilizar una recopilación de configuraciones para los dispositivos que ejecutan Lync Phone Edition, elimínela. Si elimina una recopilación para un sitio, la configuración global se aplicará a los teléfonos de este sitio. No puede eliminar la recopilación global.


> [!NOTE]
> En lugar de eliminar una recopilación, quizás solo necesite cambiar algunas de las configuraciones. Para obtener información detallada sobre cómo realizarlo, consulte <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Creación o modificación de un conjunto de opciones de configuración de Lync Phone Edition</A>.



## Para eliminar una recopilación de configuraciones de parámetros de Lync Phone Edition

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, haga clic en la recopilación que desea eliminar, haga clic en el menú **Editar** y, a continuación, haga clic en **Eliminar**.
    

    > [!NOTE]
    > Si elimina una recopilación global, la configuración simplemente volverá a los valores predeterminados. La recopilación no desaparece.



5.  En el cuadro de confirmación, haga clic en **Aceptar**.

## Para eliminar configuraciones de parámetros de Lync Phone Edition utilizando los cmdlets Shell de administración de Lync Server

Puede eliminar configuraciones de parámetros de Lync Phone Edition utilizando Windows PowerShell y el cmdlet **Remove-CsUCConfiguration**. Puede ejecutar este cmdlet ya sea desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una recopilación determinada de opciones de configuración de Lync Phone Edition

  - Este comando quitar las opciones de configuración de teléfono para comunicaciones unificadas aplicadas al sitio Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## Para quitar todas las opciones de configuración de Lync Phone Edition aplicadas al ámbito del sitio

  - Este comando elimina todas las configuraciones de teléfono para comunicaciones unificadas aplicadas al ámbito del servicio:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## Para quitar todas las opciones de configuración de Lync Phone Edition en las que el bloqueo de teléfono esté deshabilitado

  - Este comando quita cualquier opción de configuración de teléfono para comunicaciones unificadas en la que el bloqueo del teléfono esté deshabilitado:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

Para obtener más información, consulte [Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration).

