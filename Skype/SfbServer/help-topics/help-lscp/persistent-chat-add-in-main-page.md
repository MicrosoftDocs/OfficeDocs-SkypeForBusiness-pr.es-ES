---
title: Página principal de complemento de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Puede utilizar la sección de la página de Chat persistentes para asociar direcciones URL a salones de Chat persistentes. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.
ms.openlocfilehash: 701a128095cd2d9e001109fb6623659d189b2fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-add-in-main-page"></a>Página principal de complemento de chat persistente
 
Puede utilizar **la sección de la página de **Chat persistentes** ** para asociar direcciones URL a salones de Chat persistentes. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.
  
Los complementos sirven para ampliar la experiencia en el salón. Un complemento típico podría incluir una dirección URL que señala a una aplicación de Silverlight que intercepta cuando un indicador de cotizaciones bursátiles se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".
  
Para crear complementos para salas de Chat persistentes, consulte [configurar complementos para salas de Chat persistentes en Skype para Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si es un administrador de charla persistente, puede crear complementos mediante el panel de control o los cmdlets de Windows PowerShell.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Complemento** puede realizar las siguientes tareas:
  
- [Configurar complementos para salas de Chat persistentes en Skype para Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin. Para obtener información detallada sobre los distintos métodos que puede utilizar para iniciar el panel de control, consulte [Abrir herramientas administrativas de Lync Server](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.
    
    Para varias implementaciones de grupo de servidor de charla persistente, seleccione el grupo adecuado de la lista desplegable.
    
4. En la página **Complemento**, haga clic en **Nuevo**.
    
5. En **Seleccione un servicio**, seleccione el servicio correspondiente al grupo de servidores de charla persistente que necesita para crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.
    
6. Haga lo siguiente en **Complemento nuevo**:
    
  - En **Nombre**, especifique un nombre para el nuevo complemento.
    
  - En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.
    
7. Haga clic en **Confirmar**.
    
### 

Para obtener detalles sobre las características de servidor de charla persistente y capacidades, vea [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Implementar servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

