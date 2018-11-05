---
title: "Config. servidor de chat persistentes globales o para servidores de chat persistentes"
TOCTitle: Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48274646
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

En Panel de control de Lync Server 2013, puede usar la sección **Chat persistente Configuración** de la página **Chat persistente** para establecer la configuración de Chat persistente a nivel cuando se aplique a todos los Grupos de servidores de chat persistente o para un determinado Grupo de servidores de chat persistente.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.



## Para configurar las opciones de Chat persistente a nivel global

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio**, seleccione el Panel de control de Lync Server o abra la ventana del explorador y, después, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > También puede utilizar cmdlets Windows PowerShell. Para más información, vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación de implementación.
    


3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y luego haga clic en **Chat persistente Configuración**.

4.  En la página **Configuración de Chat persistente**, haga clic en **Nuevo** y luego haga clic en **Configuración de sitio**.
    
    > [!IMPORTANT]  
    > Seleccione esta opción si desea que la configuración se aplique a todos los Grupos de servidores de chat persistente implementados en el sitio. Haga clic en <strong>Configuración de grupos de servidores</strong> si desea que la configuración se aplique a un determinado Grupo de servidores de chat persistente.
    


5.  En **Seleccionar un sitio**, seleccione el sitio que se configurará para la configuración de sitio del Servidor de chat persistente.

6.  En **Nueva configuración de Chat persistente**, siga este procedimiento:
    
      - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. De manera predeterminada, el nombre de sitio ya existe.
    
      - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se van a procesar para cada salón tras la primera solicitud. De manera predeterminada, el número es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
        
        > [!IMPORTANT]  
        > Servidor de chat persistente almacenará en la memoria caché estos mensajes, de modo tal que si incrementa este número, se almacenarán más mensajes en la memoria caché. Siempre tiene acceso al contenido del historial mediante la búsqueda. El número predeterminado solo determina el número máximo de mensajes que ve inicialmente cuando se conecta a una sala de chat.
        
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. De forma predeterminada, el número es 20 MB (20.000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier sala de chat del sistema (para las que las cargas de archivos estén habilitadas por su correspondiente parámetro **Categoría**).
        
        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor debido a que las aplicaciones personalizadas o los clientes previos de Chat en grupo que usan Office Communications Server 2007 R2Servidor de chat en grupo o Lync Server 2010, chat en grupo pueden publicar archivos en una sala. El cliente de Lync 2013 no tiene capacidad de carga/descarga de archivos, de modo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat de Servidor de chat persistente.
        
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) para todos los participantes hasta que el número de usuarios conectados alcanza su número. De manera predeterminada, el número es 75. Este límite indica el número máximo de participantes en una sala determinado más allá del cual Servidor de chat persistente deja de enviar actualizaciones de lista a clientes conectados acerca de quién está presente en el salón.
    
      - (Opcional). En **Dirección URL de administración de salones**, seleccione la dirección URL de administración de sala. Esta es la dirección URL para una administración de salones personalizada basada en la web. Si no necesita personalizar la administración de salones y simplemente utiliza la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplica a la dirección URL de administración del salón tanto interno como externo.
        
        Si desea personalizar la experiencia de creación de salones e incluir el flujo de trabajo de su empresa específico, puede generar una solución de administración de salones personalizada utilizando el Kit de desarrollo de software (SDK) de Servidor de chat persistente, hospédela en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.

7.  Haga clic en **Confirmar**.

## Para configurar las opciones de Chat persistente para un determinado Grupo de servidores de chat persistente

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio**, seleccione el Panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la URL de administración. Para obtener información sobre los distintos métodos que puede usar para iniciar el Panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > También puede utilizar cmdlets Windows PowerShell. Para más información, vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación de implementación.
    


3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y luego haga clic en **Chat persistente Configuración**.

4.  En la página **Configuración de Chat persistente**, haga clic en **Nuevo** y, a continuación, haga clic en **Configuración de grupo de servidores**.

5.  En **Seleccionar un servicio**, seleccione el servicio asociado con el Grupo de servidores de chat persistente que se va a configurar.

6.  En **Nueva configuración de Chat persistente**, siga este procedimiento:
    
      - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. De manera predeterminada, el nombre del grupo de servidores del sitio ya existe.
    
      - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se van a procesar para cada salón tras la primera solicitud. De manera predeterminada, el número es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
        
        > [!IMPORTANT]  
        > Servidor de chat persistente almacenará en la memoria caché estos mensajes, de modo tal que si incrementa este número, se almacenarán más mensajes en la memoria caché. Siempre tiene acceso al contenido del historial mediante la búsqueda. El número predeterminado solo determina el número máximo de mensajes que ve inicialmente cuando se conecta a una sala de chat.
        
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. De forma predeterminada, el número es 20 MB (20.000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier sala de chat del sistema (para las que las cargas de archivos estén habilitadas por su correspondiente parámetro **Categoría**).
        
        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor debido a que las aplicaciones personalizadas o los clientes previos de Chat en grupo ( Office Communications Server 2007 R2Servidor de chat en grupo o Lync Server 2010, chat en grupo) pueden publicar archivos en una sala. El cliente de Lync 2013 no tiene capacidad de carga/descarga de archivos, de modo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat de Servidor de chat persistente.
        
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) para todos los participantes hasta que el número de usuarios conectados alcanza su número. De manera predeterminada, el número es 75. Este límite indica el número máximo de participantes en una sala determinado más allá del cual Servidor de chat persistente deja de enviar actualizaciones de lista a clientes conectados acerca de quién está presente en el salón.
    
      - En **URL de administración de salón**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL para una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salones y simplemente utiliza la configuración predeterminada, deje esta opción en blanco.
        
        Si desea personalizar la experiencia de creación de salones e incluir el flujo de trabajo de su empresa específico, puede generar una solución de administración de salones personalizada utilizando el Kit de desarrollo de software (SDK) de Servidor de chat persistente, hospédela en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.

7.  Haga clic en **Confirmar**.

