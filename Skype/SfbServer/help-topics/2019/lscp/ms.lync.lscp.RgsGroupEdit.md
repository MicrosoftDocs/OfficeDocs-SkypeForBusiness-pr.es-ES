---
title: Grupos de respuesta Crear nuevo o editar grupo de agentes existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118969"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Grupos de respuesta: Crear nuevos o editar los grupos de agentes existentes

Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada grupo de agentes requiere un nombre único. Use un nombre descriptivo que identifique la función del grupo. Por ejemplo, Servicio de asistencia.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre el grupo.

- **Directiva de participación** Especifique la forma en que los agentes deben iniciar sesión en el grupo de respuesta:

  - Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión. Los agentes informales inician sesión automáticamente cuando inician sesión. El valor predeterminado es **Informal**.

  - Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión. Al seleccionar esta opción, los agentes hacen clic en un elemento de menú del cliente para abrir un explorador y mostrar una consola de página web para iniciar y salir.

- **Hora de alerta (segundos)** Especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible. El valor debe ser de al menos 10 segundos e inferior a 180 segundos. El valor predeterminado es 20 segundos.

- **Método de enrutamiento** Seleccione el método para determinar el orden en que los agentes reciben llamadas:

  - Seleccione **Máxima inactividad** para ofrecer una llamada nueva primero al agente que ha estado más tiempo inactivo (el que más tiempo ha estado **Disponible** o **Inactivo**).

  - Seleccione **Enrutamiento paralelo** para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo. La llamada se envía al primer agente que la acepte.

  - Seleccione **Round robin** para ofrecer una llamada nueva a un agente cada vez.

  - Seleccione **Enrutamiento en serie** para ofrecer siempre una llamada nueva a los agentes en el orden en que aparecen en la lista **Agentes**.

  - Seleccione **Operador** para ofrecer una nueva llamada a todos los agentes que han iniciado sesión y a la aplicación grupo de respuesta al mismo tiempo, independientemente de su presencia actual. Los operadores y usuarios cliente configurados como agentes pueden ver todas las llamadas que están en espera y pueden responder llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta y los demás operadores y usuarios ya no ven la llamada.

- **Agentes** Seleccione los usuarios que deben ser agentes para el grupo de respuesta de una de las siguientes maneras:

  - Seleccione **Usar una lista de distribución de correo electrónico existente** para usar una lista de distribución de Exchange. Escriba la dirección de correo electrónico de la lista de distribución en **Dirección de la lista de distribución**.

    > [!NOTE]
    > Solo puede seleccionar una lista de distribución por grupo de agentes. Si la lista de distribución incluye listas de distribución anidadas, estas no se incluirán en el grupo de agentes.

    > [!NOTE]
    > El orden en que los agentes se muestran en la lista de distribución afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.

    > [!NOTE]
    > Las pertenencias ocultas o listas ocultas pueden ser visibles para los administradores o usuarios del grupo de respuesta. Para obtener más información, [vea Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Seleccione **Definir un grupo de agentes personalizado** para seleccionar los usuarios que desee asignar como agentes para el grupo de respuesta. Haga clic en **Seleccionar** para agregar un agente a la lista. Haga clic en **Quitar** para eliminar un agente seleccionado de la lista.

    Las flechas arriba y abajo mueven un agente seleccionado hacia arriba y hacia abajo en la lista de agentes. El orden de los agentes afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.

Para obtener más información sobre las características y capacidades del grupo de respuesta, vea [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con grupos de agentes, vea [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) en la documentación de operaciones.