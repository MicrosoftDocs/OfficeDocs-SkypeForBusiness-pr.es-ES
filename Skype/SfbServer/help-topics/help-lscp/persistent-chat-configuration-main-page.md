---
title: Página principal de configuración de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: La implementación del servidor de chat persistente puede alojar muchos salones de chat persistentes simultáneos. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
ms.openlocfilehash: 077ee0fe1058abc54568b47ea55af3c7d9238c7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822543"
---
# <a name="persistent-chat-configuration-main-page"></a>Página principal de configuración de chat persistente
 
La implementación del servidor de chat persistente puede alojar muchos salones de chat persistentes simultáneos. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
  
> [!NOTE]
> Aunque muchas de las características de administración de los salones de chat están disponibles en equipos que ejecutan chat persistente para el usuario, los administradores de chat persistente (en el rol **cspersistentchatadministrator** ) deben usar los cmdlets del panel de control o del shell de administración para crear o administrar categorías.
  
Los administradores de chat persistentes usan el panel de control de Skype empresarial Server o los cmdlets de Windows PowerShell para crear y administrar categorías, y para diseñar el acceso de los usuarios de su organización a los salones de chat.
  
Los administradores de salones de chat persistentes, que tienen la capacidad de administrar una o más salas de chat, pueden usar el cliente para iniciar una aplicación Web de administración de salas para crear y administrar salas (o para que los clientes puedan crear soluciones personalizadas y flujos de trabajo que se invocarán). 
  
Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:
  
- Deshabilitar un salón de chat
    
- Cambiar el nombre de un salón de chat
    
- Cambiar la descripción de un salón de chat
    
- Cambiar el tipo de salón de chat (Auditorio o Normal)
    
- Cambiar la privacidad de un salón (abierto, cerrado o secreto)
    
- Agregar o quitar miembros
    
- Agregar o quitar administradores de salones de chat
    
- Agregar o quitar un complemento
    
- Cambiar la configuración como las invitaciones (según lo permitido por la categoría)
    
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **configuración de chat persistente** : configurar las opciones del servidor de chat persistente globalmente o para un grupo específico
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar las opciones de chat persistentes de forma global

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **configuración de chat persistente** , haga clic en **nuevo** y, a continuación, en **configuración del sitio**.
    
    > [!IMPORTANT]
    > Elija esta opción si quiere que la configuración se aplique a todos los grupos de servidores de chat persistentes implementados en el sitio. Haga clic en **configuración del grupo** si quiere que la configuración se aplique a un grupo de servidores de chat persistente específico.
  
5. En **seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. El nombre de sitio ya existe de forma predeterminada.
    
   - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número. La cantidad predeterminada es 75. Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
   - (Opcional). En **URL de administración de salas**, seleccione la dirección URL de administración de salas. Esta es la dirección URL de una administración de salones personalizada basada en la web. Si no necesita personalizar la administración de salas y simplemente usa la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplicará como la dirección URL de administración del salón tanto interna como externa.
    
     Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente**, haga clic en **Nuevo** y, luego, en **Configuración del grupo de servidores**.
    
5. En **seleccionar un servicio**, seleccione el servicio asociado al grupo de servidores de chat persistente que desea configurar.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva configuración. El nombre del grupo de servidores del sitio ya existe de forma predeterminada.
    
   - En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes. El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda. La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número. La cantidad predeterminada es 75. Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.
    
   - En **URL de administración de sala**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL de una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salas y simplemente usa la configuración predeterminada, deje esta opción en blanco.
    
     Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

Para obtener detalles sobre las funciones y características del servidor de chat persistentes, consulte [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [implementar un servidor de chat persistente en skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [administrar el servidor de chat persistente en Skype empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

