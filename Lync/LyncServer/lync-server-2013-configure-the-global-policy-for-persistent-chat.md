---
title: "Lync Server 2013 : Conf. de la strat. globale pour la conversation permanente"
TOCTitle: Configurar la directiva global para chat persistente
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48275450
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la directiva global para chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Puede usar la directiva global predeterminada por sí misma para habilitar la configuración de Chat persistente para todos los usuarios de su implementación. También puede especificar directivas adicionales para sitios y usuarios para controlar si Chat persistente está habilitado o deshabilitado para usuarios y sitios específicos.

No puede eliminar la directiva global. Si trata de hacerlo, la configuración se restablecerá a los valores predeterminados.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para establecer las opciones de configuración del Servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013</A> en la documentación sobre implementación.



## Para configurar la directiva global para el Chat persistente

1.  En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el Panel de control de Lync Server o abra una ventana del explorador y escriba la dirección URL de administración. Para obtener información sobre los diferentes métodos que se pueden usar para iniciar el Panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación sobre operaciones.
    
    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para saber cómo, consulte <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación sobre implementación.
    


3.  En Panel de control de Lync Server, haga clic en **Chat persistente** y, a continuación, en **Directiva de Chat persistente**.

4.  Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  Haga lo siguiente en **Editar Chat persistente - Global**:
    
      - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
      - En **Descripción**, proporcione información detallada acerca de la función de la directiva de usuario (por ejemplo, directiva global de *centralSiteName*).
    
      - Para controlar el Chat persistente para todos los sitios y usuarios que no estén controlados específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla **Habilitar Chat persistente**.

6.  Haga clic en **Confirmar**.

