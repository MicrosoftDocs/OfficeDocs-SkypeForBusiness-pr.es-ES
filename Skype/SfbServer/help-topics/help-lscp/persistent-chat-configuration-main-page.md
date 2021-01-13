---
title: Página principal de configuración de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: La implementación del servidor de chat persistente puede hospedar muchos salas de chat persistente simultáneas. Los salones de chat se pueden organizar en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría, y hereda alguna configuración de esa categoría. Esta configuración crea una estructura útil para identificar conversaciones, en función de su propósito empresarial, y facilita la delegación y simplificación de la administración.
ms.openlocfilehash: eb444869c036396ee490b38ea1b0bcd149cf29c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822070"
---
# <a name="persistent-chat-configuration-main-page"></a>Página principal de configuración de chat persistente
 
La implementación del servidor de chat persistente puede hospedar muchos salas de chat persistente simultáneas. Los salones de chat se pueden organizar en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría, y hereda alguna configuración de esa categoría. Esta configuración crea una estructura útil para identificar conversaciones, en función de su propósito empresarial, y facilita la delegación y simplificación de la administración.
  
> [!NOTE]
> Aunque muchas de las características de administración de los salas de chat están disponibles en equipos que ejecutan chat persistente para el usuario, los administradores de chat persistente (en el rol **cspersistentchatadministrator)** deben usar el panel de control o los cmdlets del Shell de administración para crear o administrar categorías.
  
Los administradores de chat persistente usan el Panel de control de Skype Empresarial Server o cmdlets Windows PowerShell para crear y administrar categorías, y para diseñar el acceso a los salón de chat para los usuarios de su organización.
  
Los administradores de salón de chat persistente, que tienen la capacidad de administrar uno o más salas de chat, pueden usar el cliente para iniciar una aplicación web de administración de salas para crear y administrar salas (o los clientes pueden crear soluciones y flujos de trabajo personalizados para invocarlos). 
  
Los administradores de salones pueden hacer cambios en todas las propiedades de salones de chat, excepto en la categoría del salón. No pueden tener restricciones para realizar las siguientes acciones:
  
- Deshabilitar un salón de chat
    
- Cambiar el nombre de un salón de chat
    
- Cambiar la descripción de un salón de chat
    
- Cambiar el tipo de salón de chat (Auditorio o Normal)
    
- Cambiar la privacidad de un salón (abierto/cerrado/secreto)
    
- Agregar o quitar miembros
    
- Agregar o quitar administradores de salones de chat
    
- Agregar o quitar un complemento
    
- Cambiar la configuración, como las invitaciones (según lo permitido por la categoría)
    
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página Configuración de **chat** persistente: configurar las opciones del servidor de chat persistente de forma global o para un grupo específico
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar las opciones de chat persistente globalmente

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente,** haga clic en **Nuevo y,** a continuación, en **Configuración del sitio.**
    
    > [!IMPORTANT]
    > Elija esta opción si desea que la configuración se aplique a todos los grupos de servidores de chat persistente implementados en el sitio. Haga **clic en Configuración** del grupo si desea que la configuración se aplique a un grupo de servidores de chat persistente específico.
  
5. En **Seleccionar un sitio,** seleccione el sitio que se configurará para la configuración del sitio del servidor de chat persistente.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del sitio ya existe.
    
   - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que si aumenta este número, se almacenarán más mensajes en caché. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de lista (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en un salón determinado más allá del cual el servidor de chat persistente deja de enviar actualizaciones de listas a los clientes conectados sobre quién está presente en la sala.
    
   - (Opcional). En **la dirección URL de administración de** sala, seleccione la dirección URL de administración de la sala. Esta es la dirección URL para una administración de salones personalizada basada en web. Si no necesita personalizar la administración de la sala y simplemente usa la configuración predeterminada, deje esta opción en blanco. Después de definir la dirección URL, se aplica como la dirección URL de administración de salones tanto internos como externos.
    
     Si desea personalizar la experiencia de creación de salas e incluir el flujo de trabajo empresarial específico, puede crear una solución de administración de salas personalizada mediante el Kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente para que cuando un usuario intente ver o crear un salón, se le dirija a su solución de administración de salones personalizada.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente**, haga clic en **Nueva** y, a continuación, haga clic en **Configuración del grupo de servidores**.
    
5. En **Seleccionar un servicio,** seleccione el servicio asociado al grupo de servidores de chat persistente que se va a configurar.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del grupo de sitios ya existe.
    
   - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que si aumenta este número, se almacenarán más mensajes en caché. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de lista (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en un salón determinado más allá del cual el servidor de chat persistente deja de enviar actualizaciones de listas a los clientes conectados sobre quién está presente en la sala.
    
   - En **URL de administración de salón**, seleccione la dirección URL de administración del salón. Esta es la dirección URL para una implementación de administración de salones basada en web. Si no necesita personalizar la administración de la sala y simplemente usa la configuración predeterminada, deje esta opción en blanco.
    
     Si desea personalizar la experiencia de creación de salas e incluir el flujo de trabajo empresarial específico, puede crear una solución de administración de salas personalizada mediante el Kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Ver también

Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

