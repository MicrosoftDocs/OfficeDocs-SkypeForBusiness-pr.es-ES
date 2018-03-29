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
description: 'Resumen: Conozca cómo configurar opciones de servidor de charla persistente a nivel global, el sitio o el nivel de grupo en Skype para Business Server 2015.'
ms.openlocfilehash: 6fe06b6a5383178f0a9465624f7a0e739c2a32e6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar las opciones del servidor de chat persistentes en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar opciones de servidor de charla persistente a nivel global, el sitio o el nivel de grupo en Skype para Business Server 2015.
  
Puede especificar varias opciones para el servidor de charla persistente que se pueden aplicar globalmente, a todos los grupos dentro de un sitio o a un grupo específico dentro de un sitio. Las opciones del servidor de chat persistente incluyen las siguientes: 
  
- Historial de chat predeterminado. La cantidad de mensajes de chat disponibles para cada salón de chat tras la primera solicitud. La cantidad global predeterminada es de 30 mensajes de chat. 
    
- Tamaño máximo de archivo. El tamaño máximo de un archivo que se puede cargar o descargar en un salón. El tamaño global predeterminado es 20 MB.
    
- Límite de actualización de participantes. La cantidad máxima de participantes en un determinado salón de chat para los que el chat persistente enviará actualizaciones de lista. La cantidad global predeterminada es 75.
    
- Dirección URL de administración de sala. La dirección URL utilizada por la administración personalizada de un salón de chat. La configuración permite el uso de una solución de administración de salones personalizada. 
    
## <a name="configure-persistent-chat-server-global-options"></a>Configurar las opciones globales del servidor de charla persistente

Para configurar las opciones globales del servidor de charla persistente:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar las opciones de un grupo específico de servidor de charla persistente

Para configurar las opciones de un grupo específico de servidor de charla persistente.
  
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
    
   - En **Dirección URL de administración del salón**, seleccione la dirección URL de administración del salón. Se trata de la dirección URL para una implementación de administración de salones basada en web. Si no es necesario personalizar la administración de la sala y simplemente utiliza la configuración predeterminada, deje esta opción en blanco.
    
    Si desea personalizar su experiencia de creación de sala e incluir el flujo de trabajo de negocio específicas, puede crear una solución de administración de espacio personalizado mediante el persistente Chat Server Software Development Kit (SDK), alojarlo en algún lugar y ponga aquí la dirección URL. Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    

