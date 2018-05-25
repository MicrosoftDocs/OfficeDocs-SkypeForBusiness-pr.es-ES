---
title: Grupos de respuesta creación nuevos o edición grupo de agentes existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
ms.openlocfilehash: 4ae2869e335bc8d7d8b774f7daf7f5915dcba462
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Grupos de respuesta: Crear nuevo o editar existente
 
Los grupos de agentes definen quién puede responder las llamadas a un grupo de respuesta (conocido como agentes) y la configuración que se aplica a todos los agentes del grupo.
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Nombre** Cada grupo de agentes requiere un nombre único. Use un nombre descriptivo que identifica la función del grupo. Por ejemplo, Help Desk.
    
- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre el grupo.
    
- **Directiva de participación** Especifique el modo en que los agentes inician sesión en el grupo de respuesta:
    
  - Seleccione **Informal** para especificar que los agentes en el grupo no necesitan iniciar ni cerrar sesión en el grupo. Los agentes informales se conectan de forma automática cuando inician sesión. El valor predeterminado es **Informal**.
    
  - Seleccione **Formal** para especificar que los agentes en el grupo deben iniciar sesión y cerrar. Cuando se selecciona esta opción, los agentes, haga clic en un elemento de menú en el cliente para abrir un explorador y mostrar una consola de página web para iniciar y cerrar sesión.
    
- **Tiempo de alerta (segundos)** Especifique el número de segundos que hay que llamar a un agente antes de ofrecer la llamada al siguiente agente disponible. El valor tiene que ser de al menos 10 segundos e inferior a 180 segundos. El valor predeterminado es 20 segundos.
    
- **Método de enrutamiento** Seleccione el método para determinar el orden en que los agentes reciben llamadas:
    
  - Seleccione **Máxima inactividad** para ofrecer una llamada nueva primero al agente que haya estado más tiempo inactivo (el que más tiempo ha estado **Disponible** o **Inactivo**).
    
  - Seleccione **En paralelo** para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo. La llamada se envía al primer agente que la acepte.
    
  - Seleccione **Round robin** para ofrecer una llamada nueva a un agente cada vez.
    
  - Seleccione **En serie** para ofrecer siempre una llamada nueva a los agentes en el orden en que aparecen en la lista **Agentes**.
    
  - Seleccione el **operador** para ofrecer una nueva llamada a todos los agentes que han iniciado sesión y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual. Automáticos y los usuarios de cliente que se configuran como agentes pueden ver todas las llamadas que están en espera y pueden responder a las llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta y el resto de operadores y usuarios dejará de verla.
    
- **Agentes** Seleccione los usuarios que van a ser agentes para el grupo de respuesta en una de las siguientes maneras:
    
  - Seleccione **utilizar una lista de distribución de correo electrónico existente** para usar una lista de distribución de Exchange. Escriba el correo electrónico de la lista de distribución en **Dirección de la lista de distribución**.
    
    > [!NOTE]
    > Solo puede seleccionar una lista de distribución por grupo de agentes. Si la lista de distribución incluye listas de distribución anidadas, estas no se incluirán en el grupo de agentes. 
  
    > [!NOTE]
    > El orden en que los agentes se muestran en la lista de distribución afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie. 
  
    > [!NOTE]
    > Miembros ocultos o las listas ocultas pueden quedar visibles para los administradores de grupo de respuesta o los usuarios. Para obtener información detallada, vea [crear o modificar un grupo de agentes en Skype para profesionales de 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md). 
  
  - Seleccione **Definir un grupo de agentes personalizado** para seleccionar los usuarios que quiere asignar como agentes del grupo de respuesta. Haga clic en **Seleccionar** para agregar un agente a la lista y en **Quitar** para eliminar un agente seleccionado de la lista.
    
    Las flechas arriba y abajo mueven un agente seleccionado hacia arriba y hacia abajo en la lista de agentes. El orden de los agentes afecta al orden en que los agentes reciben llamadas para round robin y el enrutamiento en serie.
    
Para obtener información detallada sobre las características de grupo de respuesta y funciones, consulte [Plan para la aplicación de grupo de respuesta en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeación. Para obtener información detallada sobre cómo trabajar con grupos de agentes, consulte [Administración de grupos de agentes](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) en la documentación sobre operaciones.
  

