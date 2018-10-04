---
title: Configurar las opciones del servidor de chat persistentes en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Resumen: Obtenga información sobre cómo configurar las opciones del servidor de Chat persistente a nivel global, un sitio o un grupo de servidores en Skype para Business Server 2015.'
ms.openlocfilehash: 5d8bf63332ca991117e0fbd3beddc97855617274
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25376003"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar las opciones del servidor de chat persistentes en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar las opciones del servidor de Chat persistente a nivel global, un sitio o un grupo de servidores en Skype para Business Server 2015.
  
Puede especificar varias opciones para el servidor de Chat persistente que se pueden aplicar globalmente, para todos los grupos dentro de un sitio o a un grupo de servidores específico dentro de un sitio. Las opciones del servidor de chat persistente incluyen las siguientes: 
  
- Historial de chat predeterminado. La cantidad de mensajes de chat disponibles para cada salón de chat tras la primera solicitud. La cantidad global predeterminada es de 30 mensajes de chat. 
    
- Tamaño máximo de archivo. El tamaño máximo de un archivo que se puede cargar o descargar en un salón. El tamaño global predeterminado es 20 MB.
    
- Límite de actualización de participantes. La cantidad máxima de participantes en un determinado salón de chat para los que el chat persistente enviará actualizaciones de lista. La cantidad global predeterminada es 75.
    
- Dirección URL de administración de sala. La dirección URL utilizada por la administración personalizada de un salón de chat. La configuración permite el uso de una solución de administración de salones personalizada. 
   
> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar las opciones globales del servidor de Chat persistente

Para configurar las opciones globales del servidor de Chat persistente:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar las opciones de un grupo de servidores específico de servidor de Chat persistente

Para configurar las opciones para un grupo específico de servidor de Chat persistente.
  
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
    

