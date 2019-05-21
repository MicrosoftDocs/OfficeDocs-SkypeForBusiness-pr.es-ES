---
title: Configurar las opciones del servidor de chat persistentes en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Resumen: Aprenda a configurar opciones del servidor de chat persistentes a nivel global, de sitio o de grupo en Skype empresarial Server 2015.'
ms.openlocfilehash: 6305ba9a961248b24fe1a2fc28d5944efb6adeac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273871"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar las opciones del servidor de chat persistentes en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a configurar las opciones del servidor de chat persistentes en el nivel global, de sitio o de grupo en Skype empresarial Server 2015.
  
Puede especificar varias opciones para el servidor de chat persistente, que se puede aplicar globalmente, a todos los grupos dentro de un sitio o a un grupo específico dentro de un sitio. Las opciones del servidor de chat persistente incluyen las siguientes: 
  
- Historial de chat predeterminado. La cantidad de mensajes de chat disponibles para cada salón de chat tras la primera solicitud. La cantidad global predeterminada es de 30 mensajes de chat. 
    
- Tamaño máximo de archivo. El tamaño máximo de un archivo que se puede cargar o descargar en un salón. El tamaño global predeterminado es 20 MB.
    
- Límite de actualización de participantes. La cantidad máxima de participantes en un determinado salón de chat para los que el chat persistente enviará actualizaciones de lista. La cantidad global predeterminada es 75.
    
- Dirección URL de administración de salas. La dirección URL utilizada por la administración personalizada de un salón de chat. La configuración permite el uso de una solución de administración de salones personalizada. 
   
> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar las opciones globales del servidor de chat persistente

Para configurar las opciones globales del servidor de chat persistentes:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar opciones para un grupo de servidores de chat persistente específico

Para configurar las opciones de un grupo de servidores de chat persistente específico.
  
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
    

