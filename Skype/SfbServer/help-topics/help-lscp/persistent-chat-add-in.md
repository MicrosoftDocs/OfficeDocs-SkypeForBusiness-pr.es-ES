---
title: Complemento de chat persistente
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
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Puede usar la sección Complemento de la página chat persistente para asociar direcciones URL con los salón de chat persistente. Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de la conversación. Un administrador debe agregar complementos a la lista de complementos registrados, y los administradores/creadores de salas de chat deben asociar los salas con uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente.
ms.openlocfilehash: 306cd54864400362a869db34d79f1fe6241d81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803780"
---
# <a name="persistent-chat-add-in"></a>Complemento de chat persistente

Puede usar la sección **Complemento de** la página **chat** persistente para asociar direcciones URL con los salón de chat persistente. Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de la conversación. Un administrador debe agregar complementos a la lista de complementos registrados, y los administradores/creadores de salas de chat deben asociar los salas con uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente.

Los complementos se usan para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que apunta a una aplicación de Silverlight que intercepta cuando se publica un ticker de bolsa en un salón de chat y muestra el historial de acciones en el panel de extensibilidad. Otros ejemplos incluyen la incrustación de una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir determinado contexto compartido, como "Prioridades" o "Tema del día".

Para crear complementos para los salón de chat persistente, consulte Configurar complementos para los salas de chat persistente en [Skype Empresarial Server 2015.](../../manage/persistent-chat/configure-add-ins.md) Si es un administrador de chat persistente, puede crear complementos mediante el panel de control o los cmdlets Windows PowerShell usuario.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Complemento**:

- [Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.

2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control, consulte [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.

    Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.

4. En la página **Complemento**, haga clic en **Nuevo**.

5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.

6. En **Nuevo complemento**, haga lo siguiente:

   - En **Nombre**, especifique un nombre para el nuevo complemento.

   - En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento. Las direcciones URL están limitadas a los protocolos http y https.

7. Haga clic en **Confirmar**.

## <a name="see-also"></a>Vea también

Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


