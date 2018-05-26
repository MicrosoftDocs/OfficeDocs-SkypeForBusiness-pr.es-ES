---
title: Página principal de configuración de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: La implementación de servidor de Chat persistente puede hospedar muchos salones de Chat persistente simultáneas. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
ms.openlocfilehash: 633bcc1e2aaa7bb7ae4c657e196a3b7838184783
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="persistent-chat-configuration-main-page"></a>Página principal de configuración de chat persistente
 
La implementación de servidor de Chat persistente puede hospedar muchos salones de Chat persistente simultáneas. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
  
> [!NOTE]
> Si bien muchas de las características de administración de salones de chat están disponibles en los equipos que ejecutan Chat en grupo para el usuario, los administradores de charla persistente (en el rol **cspersistentchatadministrator** ) debe usar los cmdlets del shell de administración o el panel de control Para crear o administrar categorías.
  
Los administradores de charla persistente usar Skype para cmdlets de Windows PowerShell o de Panel de Control de servidor empresarial crear y administrar categorías y para acceso de diseño para salones de chat para los usuarios de su organización.
  
Los jefes de salón de Chat persistente, que tienen la capacidad de administrar uno o más salones de chat, pueden usar al cliente para iniciar una aplicación Web para crear y administrar las salas de administración de la sala (o los clientes pueden crear soluciones personalizadas y flujos de trabajo que se invoca). 
  
Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:
  
- Deshabilitar un salón de chat
    
- Cambiar el nombre de un salón de chat
    
- Cambiar la descripción de un salón de chat
    
- Cambiar el tipo de salón de chat (Auditorio o Normal)
    
- Cambiar la privacidad de un salón (abierto, cerrado o secreto)
    
- Agregar o quitar miembros
    
- Agregar o quitar administradores de salones de chat
    
- Agregar o quitar un complemento
    
- Cambiar configuraciones como invitaciones (de acuerdo con lo que está permitido por la categoría)
    
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página de **Configuración de Chat persistente** : configurar las opciones de servidor de Chat persistente globalmente o para un grupo de servidores específico
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar las opciones de Chat persistente a nivel global

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **Configuración de Chat persistente** , haga clic en **nuevo** y, a continuación, haga clic en **Configuración del sitio**.
    
    > [!IMPORTANT]
    > Elija esta opción si desea que la configuración que se aplicará a todos los grupos de servidores de Chat persistente implementados en el sitio. Si desea que la configuración que se aplicará a un grupo de servidores específico de servidor de Chat persistente, haga clic en **Configuración del grupo de servidores** .
  
5. En **Seleccionar un sitio**, seleccione el sitio que se configurará para la configuración del sitio de servidor de Chat persistente.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. El nombre de sitio ya existe de forma predeterminada.
    
  - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se procesará para cada salón tras la primera solicitud. De forma predeterminada, la cantidad es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
    > [!IMPORTANT]
    > Servidor de Chat persistente almacenará en memoria caché estos mensajes en la memoria, por lo que si se aumenta este número, más mensajes se almacenarán en caché. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
  - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo de cada historial de chat. De forma predeterminada, el tamaño es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse en cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por la configuración de la **Categoría** correspondiente).
    
  - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Persistent Chat Server envía información de la lista de participantes (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcance este número. De forma predeterminada, dicha cantidad es 75. Este límite indica el número máximo de participantes en una sala determinada más allá del cual Persistent Chat Server deja de enviar actualizaciones de la lista de participantes a los clientes conectados sobre quién está presente en la sala.
    
  - (Opcional). En **dirección URL de administración de sala**, seleccione la dirección URL de administración de sala. Esta es la dirección URL para una administración de salón personalizada basada en web. Si no es necesario personalizar la administración de sala y simplemente utilizar la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplica a la dirección URL de administración del salón tanto interna como externa.
    
    Si desea personalizar su experiencia de creación de sala e incluir el flujo de trabajo de negocio específicos, puede crear una solución de administración de salón personalizado mediante el uso de la persistente Chat Server Software Development Kit (SDK), que lo hospede en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar las opciones de Chat persistente para un grupo específico de servidor de Chat persistente

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial, o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente**, haga clic en **Nuevo** y, luego, en **Configuración del grupo de servidores**.
    
5. En **Seleccionar un servicio**, seleccione el servicio asociado con el grupo de servidores de Chat persistente que desea configurar.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para la nueva configuración. El nombre del grupo de servidores del sitio ya existe de forma predeterminada.
    
  - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se procesará para cada salón tras la primera solicitud. De forma predeterminada, la cantidad es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
    > [!IMPORTANT]
    > Servidor de Chat persistente almacenará en memoria caché estos mensajes en la memoria, por lo que si se aumenta este número, más mensajes se almacenarán en caché. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
  - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo de cada historial de chat. De forma predeterminada, el tamaño es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse en cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por la configuración de la **Categoría** correspondiente).
    
  - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Persistent Chat Server envía información de la lista de participantes (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcance este número. De forma predeterminada, dicha cantidad es 75. Este límite indica el número máximo de participantes en una sala determinada más allá del cual Persistent Chat Server deja de enviar actualizaciones de la lista de participantes a los clientes conectados sobre quién está presente en la sala.
    
  - En **Dirección URL de administración del salón**, seleccione la dirección URL de administración del salón. Se trata de la dirección URL para una implementación de administración de salones basada en web. Si no es necesario personalizar la administración de sala y simplemente utilizar la configuración predeterminada, deje esta opción en blanco.
    
    Si desea personalizar su experiencia de creación de sala e incluir el flujo de trabajo de negocio específicos, puede crear una solución de administración de salón personalizado mediante el uso de la persistente Chat Server Software Development Kit (SDK), que lo hospede en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
### 

Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, vea [Planear Persistent Chat Server in Skype para Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server en Skype para Business Server 2015](../../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../../manage/persistent-chat/persistent-chat.md).
  

