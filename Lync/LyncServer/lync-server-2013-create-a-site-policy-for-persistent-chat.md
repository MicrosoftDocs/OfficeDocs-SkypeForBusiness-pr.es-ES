---
title: "Lync Server 2013 : Créa. d’une strat. de site pour la conversation permanente"
TOCTitle: Crear una directiva de sitio para chat persistente
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48274494
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de sitio para chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Para cada sitio que ha implementado, puede crear un directiva de Chat persistente específica de sitio.

La configuración de la directiva de sitio invalida la directiva global, aunque solo para el sitio específico cubierto por la directiva de sitio.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para establecer las opciones de configuración del Servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013</A> en la documentación sobre implementación.



## Para crear una directiva de Chat persistente para un sitio

1.  En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio**, seleccione el Panel de control de Lync Server o abra la ventana del explorador y, después, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y luego en Directiva **Chat persistente**.
    
    > [!IMPORTANT]  
    > También puede utilizar cmdlets Windows PowerShell. Para más información, vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación de implementación.
    


4.  Haga clic en **Nuevo** y en **Directiva de sitio**.

5.  En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.

6.  En **Nueva directiva de Chat persistente**, siga estos pasos:
    
      - En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).
    
      - En **Descripción**, proporcione detalles acerca de lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).
    
      - Para controlar Chat persistente para todos los sitios no específicamente controlados a través de una directiva de sitio, active o desactive la casilla **Habilitar Chat persistente**.

7.  Haga clic en **Confirmar**.

