---
title: 'Lync Server 2013: configurar las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente'
description: 'Lync Server 2013: Configure las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564996"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configure las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la sección **configuración de chat persistente** de la página **chat persistente** para establecer la configuración de chat persistente globalmente, donde se aplica a todos los grupos de servidores de chat persistente o a un grupo de servidores de chat persistente específico.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar las opciones de chat persistente de forma global

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.

4.  En la página **configuración de chat persistente** , haga clic en **nuevo** y, a continuación, haga clic en **configuración del sitio**.
    
    <div>
    

    > [!IMPORTANT]  
    > Elija esta opción si desea que la configuración se aplique a todos los grupos de servidores de chat persistente implementados en el sitio. Haga clic en <STRONG>configuración del grupo</STRONG> de servidores si desea que la configuración se aplique a un grupo de servidores de chat persistente específico.

    
    </div>

5.  En **seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.

6.  En **Nueva configuración de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del sitio ya existe.
    
      - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
        
        <div>
        

        > [!IMPORTANT]  
        > El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat.

        
        </div>
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de chat en grupo de Office Communications Server 2007 R2 &nbsp; o Lync server 2010, el chat en grupo puede publicar archivos en un salón. El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en un salón más allá del cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
      - (Opcional). En **URL de administración de salón**, seleccione la dirección URL de administración del salón. Esta es la dirección URL para una administración de salones personalizada basada en web. Si no necesita personalizar la administración de salones, y simplemente usa la configuración predeterminada, deje esta opción en blanco. Después de definir la dirección URL, se aplica como la dirección URL de administración de salones tanto internos como externos.
        
        Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada con el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente para que cuando un usuario intente ver o crear un salón, se le dirija a su solución de administración de salones personalizada.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.

4.  En la página **Configuración de chat persistente**, haga clic en **Nueva** y, a continuación, haga clic en **Configuración del grupo de servidores**.

5.  En **seleccionar un servicio**, seleccione el servicio asociado con el grupo de servidores de chat persistente que se va a configurar.

6.  En **Nueva configuración de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del grupo de sitios ya existe.
    
      - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
        
        <div>
        

        > [!IMPORTANT]  
        > El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat.

        
        </div>
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores (el servidor de chat en grupo de Office Communications Server 2007 R2 &nbsp; o Lync server 2010, chat en grupo) pueden publicar archivos en un salón. El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en un salón más allá del cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
      - En **URL de administración de salón**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL para una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salones y simplemente utiliza la configuración predeterminada, deje esta opción en blanco.
        
        Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada con el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

