---
title: Página principal de complemento de chat persistente
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Puede usar la sección Complemento de la página Chat persistente para asociar direcciones URL con salas de chat persistente. Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de conversación. Un administrador debe agregar complementos a la lista de complementos registrados y los administradores o creadores de salas de chat deben asociar salas con uno de los complementos registrados antes de que los usuarios puedan ver esta actualización en su cliente.
ms.openlocfilehash: a119eb677aca1cbe938ca0f4e173367e55abfa8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099526"
---
# <a name="persistent-chat-add-in-main-page"></a>Página principal de complemento de chat persistente

Puede usar la sección **Complemento de** la página **Chat** persistente para asociar direcciones URL con salas de chat persistente. Estas direcciones URL aparecen en el cliente en el salón de chat en el panel de extensibilidad de conversación. Un administrador debe agregar complementos a la lista de complementos registrados y los administradores o creadores de salas de chat deben asociar salas con uno de los complementos registrados antes de que los usuarios puedan ver esta actualización en su cliente.

Los complementos se usan para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando se publica un ticker de acciones en un salón de chat y muestra el historial de acciones en el panel de extensibilidad. Otros ejemplos incluyen la incrustación de una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir determinado contexto compartido, como "Prioridades" o "Tema del día".

Para crear complementos para salas de chat persistente, vea [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si es un administrador de chat persistente, puede crear complementos mediante el panel de control o los cmdlets Windows PowerShell usuario.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Complemento**:

- [Configurar complementos para salas de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.

2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el panel de control, vea [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).

3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.

    Para varias implementaciones de grupo de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.

4. En la página **Complemento**, haga clic en **Nuevo**.

5. En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.

6. En **Nuevo complemento**, haga lo siguiente:

   - En **Nombre**, especifique un nombre para el nuevo complemento.

   - En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento. Las direcciones URL están limitadas a los protocolos http y https.

7. Haga clic en **Confirmar**.

## <a name="see-also"></a>Ver también

Para obtener más información sobre las características y capacidades del servidor de chat persistente, vea [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)y [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).