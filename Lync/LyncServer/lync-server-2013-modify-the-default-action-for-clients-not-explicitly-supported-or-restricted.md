---
title: "Modificar la acción predet. para clientes no admitidos explícitamente o restringidos"
TOCTitle: "Mod. l’action par déf. des clients non explicitement pris en ch. ou restreints"
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48275287
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar la acción predeterminada para clientes que no se admiten explícitamente o que están restringidos

 

_**Última modificación del tema:** 2013-02-23_

Además de especificar la versión de los clientes que desea admitir en el entorno de Lync Server 2013, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en el entorno de Lync Server, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.

## Para modificar la acción predeterminada para clientes que no se admiten explícitamente o que están restringidos

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de versiones de cliente**.

4.  En la página **Configuración de versiones de cliente**, haga doble clic en la configuración **Global** en la lista.

5.  En el cuadro de diálogo **Editar configuración de versiones de cliente**, compruebe que la casilla **Habilitar control de versiones** esté activada y, a continuación, en **Acción predeterminada**, seleccione una de las opciones siguientes:
    
      - **Permitir**   Permite que el cliente inicie la sesión si la versión de cliente no coincide con ningún filtro de la lista **Directivas de versiones de cliente**.
    
      - **Bloquear**   Bloquea los inicios de sesión del cliente si la versión de cliente no coincide con ningún filtro de la lista **Directivas de versiones de cliente**.
    
      - **Bloquear con dirección URL**   Bloquea los inicios de sesión del cliente si la versión de cliente no coincide con ningún filtro de la lista **Directivas de versiones de cliente** e incluye un mensaje de error con una URL en la que se puede descargar un cliente más reciente.
    
      - **Permitir con dirección URL**   Permite que el cliente inicie la sesión si la versión de cliente no coincide con ningún filtro de la lista **Directivas de versiones de cliente** e incluye un mensaje de error con una URL en la que se puede descargar un cliente más reciente.

6.  Si selecciona **Bloquear con dirección URL**, escriba en el cuadro **URL** la dirección URL de descarga del cliente que debe incluirse en el mensaje de error.

7.  Haga clic en **Confirmar**.

## Para deshabilitar el control de versiones de cliente

  - Para deshabilitar el control de versiones para permitir que todos los clientes inicien sesión independientemente de la versión de cliente, desactive la casilla **Habilitar control de versiones** y haga clic en **Confirmar**.

## Cambio de la acción predeterminada con los cmdlets de Lync Server PowerShell

La acción predeterminada que se va a realizar cuando los usuarios intentan iniciar sesión con clientes que no se admiten explícitamente o están restringidos por una directiva de versión del cliente también se pueden administrar con el Interfaz de la línea de comandos Windows PowerShell y el cmdlet **Set-CsClientVersionPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Configuración de la acción predeterminada para bloquear el acceso

  - El siguiente comando establece la acción predeterminada Bloquear para el sitio Redmond. Esto bloqueará el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

## Configuración de la acción predeterminada para permitir el acceso

  - En este ejemplo, la acción predeterminada para el sitio Redmond se establece en Permitir. Esto permitirá el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

Para información, vea el tema de ayuda del cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy).

## Vea también

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

