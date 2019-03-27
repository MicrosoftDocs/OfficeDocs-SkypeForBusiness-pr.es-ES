---
title: Complemento de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Puede usar la sección de la página de Chat persistente para asociar las direcciones URL a salones de Chat persistente. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.
ms.openlocfilehash: 8cac9a89bcccc66459d0663f9211d22c173f94a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878824"
---
# <a name="persistent-chat-add-in"></a>Complemento de chat persistente

Puede usar **la sección de la página de **Chat persistente** ** para asociar las direcciones URL a salones de Chat persistente. Estas direcciones URL aparecen en el cliente, en el salón de chat, en el panel de extensibilidad de la conversación. Un administrador necesita agregar complementos a la lista de complementos registrados, y los administradores/creadores del salón de chat necesitan asociar los salones a uno de los complementos registrados para que los clientes puedan ver esta actualización en su cliente.

Los complementos sirven para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".

Para crear complementos para salones de Chat persistente, vea [configurar complementos para salones de Chat persistente en Skype para Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si es un administrador de Chat persistente, puede crear complementos mediante el panel de control o los cmdlets de Windows PowerShell.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Complemento** puede realizar las siguientes tareas:

- [Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para más detalles sobre los diferentes métodos que puede usar para abrir el Panel de control, mire [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.

    Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.

4. En la página **Complemento**, haga clic en **Nuevo**.

5. En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente que necesita para crear el complemento. Los complementos no se pueden mover de un grupo a otro o compartirse entre diferentes grupos.

6. En **Complemento nuevo**, haga lo siguiente:

   - En **Nombre**, especifique un nombre para el nuevo complemento.

   - En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.

7. Haga clic en **Confirmar**.

## <a name="see-also"></a>Consulte también

Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, vea [Planear Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Administrar Persistent Chat Server en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


