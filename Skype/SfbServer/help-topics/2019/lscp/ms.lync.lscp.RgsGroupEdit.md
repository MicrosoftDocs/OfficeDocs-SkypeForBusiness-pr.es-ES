---
title: Grupos de respuesta crear un grupo de agentes existente o editar nuevo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
ms.openlocfilehash: bafa1ae490da49c8a4af096129a122315a2a7809
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292622"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Grupos de respuesta: Crear nuevo o editar existente

Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada grupo de agentes requiere un nombre único. Use un nombre descriptivo que identifique la función del grupo. Por ejemplo, soporte técnico.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre el grupo.

- **Política de participación** Especifique la manera en que los agentes van a iniciar sesión en el grupo de respuesta:

  - Seleccione **Informal** para especificar que los agentes en el grupo no necesitan iniciar ni cerrar sesión en el grupo. Los agentes informales se conectan de forma automática cuando inician sesión. El valor predeterminado es **Informal**.

  - Seleccione **formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión. Cuando selecciona esta opción, los agentes hace clic en un elemento de menú en el cliente para abrir un explorador y mostrar una consola de página web para iniciar y cerrar sesión.

- **Tiempo de alerta (segundos)** Especifica la cantidad de segundos que debe sonar un agente antes de ofrecer la llamada al siguiente agente disponible. El valor tiene que ser de al menos 10 segundos e inferior a 180 segundos. El valor predeterminado es 20 segundos.

- **Método de enrutamiento** Seleccione el método para determinar el orden en el que los agentes reciben llamadas:

  - Seleccione **Máxima inactividad** para ofrecer una llamada nueva primero al agente que haya estado más tiempo inactivo (el que más tiempo ha estado **Disponible** o **Inactivo**).

  - Seleccione **En paralelo** para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo. La llamada se envía al primer agente que la acepte.

  - Seleccione **Round robin** para ofrecer una llamada nueva a un agente cada vez.

  - Seleccione **En serie** para ofrecer siempre una llamada nueva a los agentes en el orden en que aparecen en la lista **Agentes**.

  - Seleccione **operador** para ofrecer una nueva llamada a todos los agentes que han iniciado sesión y a la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual. Los operadores y los usuarios de clientes que están configurados como agentes pueden ver todas las llamadas que están esperando y pueden contestar las llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta y el resto de operadores y usuarios dejará de verla.

- **Agentes** Seleccione los usuarios que serán agentes para el grupo de respuesta de una de las siguientes maneras:

  - Seleccione **usar una lista de distribución de correo electrónico existente** para usar una lista de distribución de Exchange. Escriba el correo electrónico de la lista de distribución en **Dirección de la lista de distribución**.

    > [!NOTE]
    > Solo puede seleccionar una lista de distribución por grupo de agentes. Si la lista de distribución incluye listas de distribución anidadas, estas no se incluirán en el grupo de agentes.

    > [!NOTE]
    > El orden en que los agentes se muestran en la lista de distribución afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.

    > [!NOTE]
    > Es posible que los administradores o los usuarios de grupos de respuesta vean pertenencias o listas ocultas ocultas. Para obtener más información, consulte [crear o modificar un grupo de agentes en Skype empresarial](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Seleccione **Definir un grupo de agentes personalizado** para seleccionar los usuarios que quiere asignar como agentes del grupo de respuesta. Haga clic en **Seleccionar** para agregar un agente a la lista y en **Quitar** para eliminar un agente seleccionado de la lista.

    Las flechas arriba y abajo mueven un agente seleccionado hacia arriba y hacia abajo en la lista de agentes. El orden de los agentes afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.

Para obtener más información sobre las funciones y características de grupos de respuesta, consulte [planear la aplicación de grupo de respuesta en Skype empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planificación. Para más información sobre cómo trabajar con grupos de agentes, mire [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) en la documentación de operaciones.


