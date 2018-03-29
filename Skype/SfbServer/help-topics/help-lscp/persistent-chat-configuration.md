---
title: Configuración de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: La implementación del servidor de charla persistente puede alojar muchos salas de Chat persistentes simultáneas. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
ms.openlocfilehash: c4408ebd4417d2cf825620837da018ef30f725c9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-configuration"></a>Configuración de chat persistente
 
La implementación del servidor de charla persistente puede alojar muchos salas de Chat persistentes simultáneas. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
  
> [!NOTE]
> Aunque muchas de las características de gestión de salas de chat están disponibles en equipos que ejecutan charla persistente para el usuario, los administradores de charla persistente (en la función **cspersistentchatadministrator** ) debe utilizar ambos el shell de administración o el panel de control cmdlets para crear o administrar categorías.
  
Persistente de los administradores de charla utilizar Skype para cmdlets de Windows PowerShell o el Panel de Control de servidor de negocio crear y administrar categorías y acceso al diseño de salas de chat para los usuarios de su organización.
  
Los jefes de salón de Chat persistentes, que tienen la capacidad para administrar uno o más salones de charla, pueden utilizar al cliente para iniciar una aplicación Web para crear y administrar las salas de administración sala (o los clientes pueden crear soluciones personalizadas y flujos de trabajo para invocar). Chat persistente
  
Los administradores de charla persistentes también pueden utilizar el panel de control o los cmdlets de Windows PowerShell para crear y administrar las salas de.
  
Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:
  
- Deshabilitar un salón de chat
    
- Cambiar el nombre de un salón de chat
    
- Cambiar la descripción de un salón de chat
    
- Cambiar el tipo de salón de chat (Auditorio o Normal)
    
- Cambiar la privacidad de un salón (abierto, cerrado o secreto)
    
- Agregar o quitar miembros
    
- Agregar o quitar administradores de salones de chat
    
- Agregar o quitar un complemento
    
- Cambiar la configuración como invitaciones (según lo que está permitido por la categoría)
    
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Configuración de Chat persistentes** : configurar opciones de servidor de charla persistente globalmente o para un grupo específico.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Configurar globalmente opciones de Chat persistentes

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **Configuración persistente de Chat** , haga clic en **nuevo** y, a continuación, haga clic en **Configuración del sitio**.
    
    > [!IMPORTANT]
    > Elija esta opción si desea que la configuración se aplique a todos los grupos de servidor de charla persistente implementados en el sitio. Haga clic en **Configuración del grupo** si desea que la configuración se aplique a un grupo específico de servidor de charla persistente.
  
5. En **Seleccione un sitio**, seleccione el sitio que se configurará para la configuración de sitio del servidor de Chat persistentes.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. El nombre de sitio ya existe de forma predeterminada.
    
  - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se procesará para cada salón tras la primera solicitud. De forma predeterminada, la cantidad es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
    > [!IMPORTANT]
    > Servidor de charla persistente almacenará en memoria caché estos mensajes en la memoria, por lo que si se aumenta este número, se almacenará en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
  - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo de cada historial de chat. De forma predeterminada, el tamaño es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse en cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por la configuración de la **Categoría** correspondiente).
    
  - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Servidor de charla persistente envía información de nómina (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, dicha cantidad es 75. Este límite indica el número máximo de participantes en una sala determinada más allá del cual el servidor de charla persistente deje de enviar actualizaciones de nómina a clientes conectados sobre quién está presente en la sala.
    
  - (Opcional). En **URL de administración de la sala**, seleccione la dirección URL de administración de sala. Esta es la dirección URL para una administración de salón personalizada basada en web. Si no es necesario personalizar la administración de la sala y simplemente utiliza la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplica a la dirección URL de administración del salón tanto interna como externa.
    
    Si desea personalizar su experiencia de creación de sala e incluir el flujo de trabajo de negocio específicas, puede crear una solución de administración de espacio personalizado mediante el persistente Chat Server Software Development Kit (SDK), alojarlo en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar opciones de Chat persistentes para un grupo específico de servidor de charla persistente

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor empresarial, o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente**, haga clic en **Nuevo** y, luego, en **Configuración del grupo de servidores**.
    
5. En **Seleccione un servicio**, seleccione el servicio asociado con el grupo de servidor de charla persistente a configurarse.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para la nueva configuración. El nombre del grupo de servidores del sitio ya existe de forma predeterminada.
    
  - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se procesará para cada salón tras la primera solicitud. De forma predeterminada, la cantidad es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
    > [!IMPORTANT]
    > Servidor de charla persistente almacenará en memoria caché estos mensajes en la memoria, por lo que si se aumenta este número, se almacenará en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
  - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo de cada historial de chat. De forma predeterminada, el tamaño es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse en cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por la configuración de la **Categoría** correspondiente).
    
  - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. Servidor de charla persistente envía información de nómina (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, dicha cantidad es 75. Este límite indica el número máximo de participantes en una sala determinada más allá del cual el servidor de charla persistente deje de enviar actualizaciones de nómina a clientes conectados sobre quién está presente en la sala.
    
  - (Opcional) En **URL de administración de sala**, seleccione la dirección URL de administración del salón. Esta es la dirección URL de una implementación de administración de salones basada en web. Si no es necesario personalizar la administración de la sala y simplemente utiliza la configuración predeterminada, deje esta opción en blanco.
    
    Si desea personalizar su experiencia de creación de sala e incluir el flujo de trabajo de negocio específicas, puede crear una solución de administración de espacio personalizado mediante el persistente Chat Server Software Development Kit (SDK), alojarlo en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
### 

Para obtener detalles sobre las características de servidor de charla persistente y capacidades, vea [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Implementar servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

