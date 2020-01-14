---
title: 'Lync Server 2013: Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fedd0d1adb4149c3dc2ea41c5321259f571524f
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la sección **configuración de chat** persistente de la página **chat persistente** para configurar las opciones de chat de forma global, donde se aplica a todos los grupos de servidores de chat persistentes o a un grupo de servidores de chat persistente específico.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar las opciones de chat persistentes de forma global

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.

4.  En la página **configuración de chat persistente** , haga clic en **nuevo** y, a continuación, en **configuración del sitio**.
    
    <div>
    

    > [!IMPORTANT]  
    > Elija esta opción si quiere que la configuración se aplique a todos los grupos de servidores de chat persistentes implementados en el sitio. Haga clic en <STRONG>configuración del grupo</STRONG> si quiere que la configuración se aplique a un grupo de servidores de chat persistente específico.

    
    </div>

5.  En **seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.

6.  En **Nueva configuración de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. El nombre de sitio ya existe de forma predeterminada.
    
      - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
        
        <div>
        

        > [!IMPORTANT]  
        > El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat.

        
        </div>
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor&nbsp;de chat grupal de Office Communications Server 2007 R2 o Lync Server 2010, la conversación grupal puede publicar archivos en un salón. El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número. La cantidad predeterminada es 75. Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
      - (Opcional). En **URL de administración de sala**, seleccione la dirección URL de administración de salón. Esta es la dirección URL de una administración de salones personalizada basada en la web. Si no necesita personalizar la administración de salones y, simplemente, usa la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplicará como la dirección URL de administración del salón tanto interna como externa.
        
        Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server, o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.

4.  En la página **Configuración de chat persistente**, haga clic en **Nuevo** y, luego, en **Configuración del grupo de servidores**.

5.  En **seleccionar un servicio**, seleccione el servicio asociado al grupo de servidores de chat persistente que desea configurar.

6.  En **Nueva configuración de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva configuración. El nombre del grupo de servidores del sitio ya existe de forma predeterminada.
    
      - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
        
        <div>
        

        > [!IMPORTANT]  
        > El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat.

        
        </div>
    
      - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores (servidor de chat&nbsp;en grupo de Office Communications Server 2007 R2 o Lync Server 2010, chat grupal) pueden publicar archivos en una sala. El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
      - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número. La cantidad predeterminada es 75. Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
      - En **URL de administración de sala**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL de una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salones y, simplemente, usa la configuración predeterminada, deje esta opción en blanco.
        
        Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

