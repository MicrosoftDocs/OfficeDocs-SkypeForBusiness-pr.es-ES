---
title: Regla de versiones de cliente
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 88316487ccd6f061127f92a762ac2d8c17b6a9c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-rule"></a>Regla de versiones de cliente
 
Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:
  
- Agregar nuevas reglas a una directiva de versión de cliente.
    
- Modificar las reglas que componen una directiva de versión de cliente existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Agente de usuario** Puede seleccionar un tipo de cliente de la lista. En la siguiente tabla se recogen los códigos de agente de usuario.
    
|**Nombre del cliente**|**Agente de usuario**|
|:-----|:-----|
|2013 de Lync, Lync 2010, Office Communicator  <br/> |Componente opcional  <br/> |
|Aplicación Web de Lync, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Plataforma Communicator Phone Edition  <br/> |CPE  <br/> |
|Plataforma de comunicaciones unificadas  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Complemento de Live Meeting  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Cliente de comunicaciones en tiempo real  <br/> |RTC  <br/> |
|Lync 2010 para iPad  <br/> |iPadLync  <br/> |
|Lync 2010 para iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 para Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 para Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 para Android  <br/> |AndroidLync  <br/> |
|Servicio de movilidad  <br/> |McxService  <br/> |
   
- **Número de versión** Puede especificar los números de versión para los siguientes campos, o utilizar comodines para indicar el número de versión del cliente.
    
  - **Versión principal** Especifica el número que corresponde a la principal versión del cliente.
    
  - **Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.
    
  - **Generar** Especifica el número de generación que corresponde a la versión principal y secundaria del cliente.
    
  - **Actualización** Especifica el número que corresponde a la versión actualizada del cliente.
    
- **Operación de comparación** Puede especificar la operación de coincidencia para la versión de cliente especificado en los pasos anteriores. Las siguientes operaciones están disponibles:
    
  - **Igual que**
    
  - **No es**
    
  - **Anterior a**
    
  - **Anterior a o igual que**
    
  - **Posterior a**
    
  - **Posterior a o igual que**
    
- **Acción** Puede especificar la acción a realizar cuando se cumplan los criterios en los pasos anteriores. Están disponibles las siguientes acciones:
    
  - **Permitir** Permite al cliente iniciar sesión.
    
  - **Permitir y actualizar** Permite al cliente iniciar sesión y recibir actualizaciones desde Microsoft Update o de Windows Server Update Services. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.
    
    > [!NOTE]
    > Si se selecciona esta acción, una notificación para que aparezca la próxima vez que los usuarios iniciar sesión en Skype para empresas. La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles. 
  
  - **Permitir con dirección URL** Permite al cliente iniciar sesión y muestra un mensaje acerca de dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.
    
  - **Bloque** Impide que el cliente iniciar sesión.
    
  - **Bloque y actualización** Impide que el cliente de inicio de sesión y permite al cliente recibir actualizaciones desde Microsoft Update o de Windows Server Update Services. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.
    
  - **Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.
    
Para obtener más información acerca de la interoperabilidad entre los clientes y las versiones de cliente, vea [Interoperabilidad de cliente en la vista previa de 2013 Lync](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeamiento. Para obtener más información sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para clientes no admitidas explícitamente o restringido](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de las operaciones.

