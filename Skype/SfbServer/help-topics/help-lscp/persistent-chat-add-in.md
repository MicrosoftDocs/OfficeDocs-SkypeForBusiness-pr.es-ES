---
title: Complemento de chat persistente
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
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Puede usar la sección de complemento de la página de chat persistente para asociar las URL a salas de chat persistentes. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.
ms.openlocfilehash: 2122f07bb51167dbaea6eb7d0881443e1ff44575
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822573"
---
# <a name="persistent-chat-add-in"></a>Complemento de chat persistente

Puede usar la sección de **complemento** de la página de **chat persistente** para asociar las URL a salas de chat persistentes. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.

Los complementos sirven para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que señala a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones está publicado en un salón de chat y muestra el historial de cotizaciones en el panel extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".

Para crear complementos para salones de chat persistentes, consulte [configurar complementos para salones de chat persistente en Skype empresarial Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si es un administrador de chat persistente, puede crear complementos con el panel de control o los cmdlets de Windows PowerShell.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Complemento** puede realizar las siguientes tareas:

- [Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más detalles sobre los diferentes métodos que puede usar para abrir el Panel de control, mire [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.

    Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.

4. En la página **Complemento**, haga clic en **Nuevo**.

5. En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro o compartirse entre diferentes grupos.

6. En **Complemento nuevo**, haga lo siguiente:

   - En **Nombre**, especifique un nombre para el nuevo complemento.

   - En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.

7. Haga clic en **Confirmar**.

## <a name="see-also"></a>Vea también

Para obtener detalles sobre las funciones y características del servidor de chat persistentes, consulte [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [implementar un servidor de chat persistente en skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [administrar el servidor de chat persistente en Skype empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md).


