---
title: Eliminación de una directiva de ubicación
TOCTitle: Eliminación de una directiva de ubicación
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49889368
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de una directiva de ubicación

 

_**Última modificación del tema:** 2012-10-10_

En Lync Server 2013, puede usar la directiva de ubicación para aplicar opciones de configuración relacionadas con las funciones de 9-1-1 mejorado (E9-1-1) y la configuración de ubicación para usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la directiva de ubicación para definir qué número constituye una llamada de emergencia (como 911 en EE. UU.), si se debe informar a la seguridad corporativa de forma automática y cómo se debe desviar la llamada.

Puede configurar directivas de ubicación desde el grupo **Configuración de la red** de Panel de control de Lync Server 2013. Desde Panel de control de Lync Server puede ver, crear, modificar o eliminar directivas de ubicación. Utilice los siguientes procedimientos para eliminar una directiva de ubicación. Si desea obtener detalles sobre cómo crear o modificar directivas de ubicación, consulte [Creación o modificación de una directiva de ubicación](lync-server-2013-creating-or-modifying-a-location-policy.md).

## Para eliminar una directiva de ubicación

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación** , seleccione la directiva de ubicación que desea eliminar.
    

    > [!NOTE]
    > Puede eliminar más de una ubicación en la misma operación. Para hacerlo, pulse CTRL y seleccione varias directivas manteniendo pulsada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    
    > [!IMPORTANT]  
    > No puede eliminar la directiva de ubicación Global. Si trata de eliminar la directiva Global recibirá un mensaje de advertencia y las propiedades de dicha directiva se restablecerán a sus valores predeterminados.
    


## Vea también

#### Tareas

[Creación o modificación de una directiva de ubicación](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Visualización de la información de una directiva de ubicación](lync-server-2013-viewing-location-policy-information.md)

