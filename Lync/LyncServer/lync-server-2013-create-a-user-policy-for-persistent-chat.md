---
title: "Lync Server 2013 : Créa. d’une strat. ut. pour la conversation permanente"
TOCTitle: Crear una directiva de usuario para chat persistente
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48276292
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de usuario para chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

En el Panel de control de Lync Server, es posible definir directivas que se pueden asignar a usuarios en **Usuarios** .

La directiva de usuario anula la directiva global y las directivas de sitio, pero solo para los usuarios específicos a los que se asignó dicha directiva.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para establecer las opciones de configuración del Servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013</A> en la documentación sobre implementación.



## Para crear una directiva de usuario para Chat persistente

1.  En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el Panel de control de Lync Server o abra la ventana del explorador y, después, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación sobre implementación.
    


3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en Directiva **Chat persistente**.

4.  Haga clic en **Nuevo** y luego en **Directiva de usuario** .

5.  En **Nueva directiva de Chat persistente**, siga estos pasos:
    
      - En **Nombre** , especifique un nombre para la nueva directiva de usuario.
    
      - En **Descripción** , proporcione detalles sobre la función de la directiva de usuario (por ejemplo, directiva de Chat persistente para usuario específico).
    
      - Para controlar el Chat persistente de todos los usuarios que no se controlan específicamente a través de una directiva de usuario, active o desactive la casilla **Habilitar Chat persistente**.

6.  Haga clic en **Confirmar** .

