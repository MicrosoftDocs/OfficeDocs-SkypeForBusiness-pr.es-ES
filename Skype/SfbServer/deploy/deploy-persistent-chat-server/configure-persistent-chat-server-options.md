---
title: Configurar las opciones del servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Summary: Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype Empresarial Server 2015.'
ms.openlocfilehash: 99dab0b4a5e7bb542dee00803e5c401c63544ada
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835848"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar las opciones del servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar las opciones del servidor de chat persistente en el nivel global, de sitio o de grupo en Skype Empresarial Server 2015.
  
Puede especificar varias opciones para el servidor de chat persistente que se pueden aplicar globalmente, a todos los grupos de servidores de un sitio o a un grupo específico dentro de un sitio. Entre las opciones del servidor de chat persistente se incluyen las siguientes: 
  
- Historial de chat predeterminado. El número de mensajes de chat que están disponibles para cada salón de chat tras la primera solicitud. El valor predeterminado global es 30 mensajes de chat. 
    
- Tamaño máximo de archivo. El tamaño máximo de un archivo que se puede cargar o descargar desde una sala. El valor predeterminado global es 20 MB.
    
- Límite de actualización de participantes. El número máximo de participantes en un salón de chat determinado al que el Chat persistente enviará actualizaciones de lista. El valor predeterminado global es 75.
    
- Dirección URL de administración de sala. La dirección URL usada para la administración de salas de chat personalizadas. La configuración permite el uso de una solución de administración de sala personalizada. 
   
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar opciones globales del servidor de chat persistente

Para configurar las opciones globales del servidor de chat persistente:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú** Inicio, seleccione Skype Empresarial Server Panel de control o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.
    
4. En la **página Configuración de chat persistente,** haga clic en Nuevo **y, a continuación,** haga clic en **Configuración del sitio**.
    
    > [!IMPORTANT]
    > Elija esta opción si desea que la configuración se aplique a todos los grupos de servidores de chat persistente implementados en el sitio. Haga **clic en** Configuración del grupo si desea que la configuración se aplique a un grupo de servidores de chat persistente específico.
  
5. En **Seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del sitio ya existe.
    
   - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente almacenará en caché estos mensajes en la memoria, por lo que si aumenta este número, se almacenarán más mensajes en caché. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de lista (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en una sala determinada más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados acerca de quién está presente en la sala.
    
   - (Opcional). En **Dirección URL de administración de sala,** seleccione la dirección URL de administración de sala. Esta es la dirección URL para una administración de salones personalizada basada en web. Si no necesita personalizar la administración de sala y simplemente usa la configuración predeterminada, deje esta opción en blanco. Después de definir la dirección URL, se aplica como la dirección URL de administración de salones tanto internos como externos.
    
     Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo empresarial específico, puede crear una solución de administración de salas personalizada mediante el Kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente para que cuando un usuario intente ver o crear un salón, se le dirija a su solución de administración de salones personalizada.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar opciones para un grupo de servidores de chat persistente específico

Para configurar opciones para un grupo de servidores de chat persistente específico.
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú** Inicio, seleccione Skype Empresarial Server Panel de control o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.
    
4. En la página **Configuración de chat persistente**, haga clic en **Nueva** y, a continuación, haga clic en **Configuración del grupo de servidores**.
    
5. En **Seleccionar un servicio,** seleccione el servicio asociado al grupo de servidores de chat persistente que se va a configurar.
    
6. En **Nueva configuración de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del grupo de sitios ya existe.
    
   - En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.
    
     > [!IMPORTANT]
     > El servidor de chat persistente almacenará en caché estos mensajes en la memoria, por lo que si aumenta este número, se almacenarán más mensajes en caché. SIempre puede obtener acceso al contenido histórico mediante búsqueda. El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat. 
  
   - En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).
    
   - En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes. El servidor de chat persistente envía información de lista (que está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número. De forma predeterminada, el número es 75. Este límite indica el número máximo de participantes en una sala determinada más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados acerca de quién está presente en la sala.
    
   - En **URL de administración de salón**, seleccione la dirección URL de administración del salón. Esta es la dirección URL para una implementación de administración de salones basada en web. Si no necesita personalizar la administración de sala y simplemente usa la configuración predeterminada, deje esta opción en blanco.
    
     Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo empresarial específico, puede crear una solución de administración de salas personalizada mediante el Kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí. Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.
    
7. Haga clic en **Confirmar**.
    

