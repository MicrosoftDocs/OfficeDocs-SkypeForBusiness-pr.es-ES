---
title: Regla de versiones de cliente
ms.reviewer: ''
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
ms.openlocfilehash: c70d831d88948bd50f14b9591807e2ce1f36611a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234731"
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

|**Nombre de cliente**|**Agente de usuario**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
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

- **Número de versión** Puede especificar los números de versión para los siguientes campos, o usar caracteres comodín para indicar el número de versión de cliente.

  - **Versión principal** Especifica el número que corresponde a la versión principal de versión del cliente.

  - **Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.

  - **Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.

  - **Actualización** Especifica el número que corresponde a la versión actualizada del cliente.

- **Operación de comparación** Puede especificar la operación coincidente para la versión de cliente que haya especificado en los pasos anteriores. Las siguientes operaciones están disponibles:

  - **Igual que**

  - **No es**

  - **Anterior a**

  - **Anterior a o igual que**

  - **Posterior a**

  - **Posterior a o igual que**

- **Acción** Puede especificar la acción a realizar cuando se cumplen los criterios en los pasos anteriores. Están disponibles las siguientes acciones:

  - **Permitir** Permite que el cliente inicie sesión.

  - **Permitir y actualizar** Permite que el cliente inicie sesión y recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.

    > [!NOTE]
    > Si se selecciona esta acción, una notificación para que aparezca la próxima vez que los usuarios iniciar sesión en Skype para la empresa. La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.

  - **Permitir con dirección URL** Permite que el cliente inicie sesión y muestra un mensaje acerca de dónde descargar otra versión de cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

  - **Bloque** Impide que el cliente de inicio de sesión.

  - **Bloque y actualización** Impide que al cliente de inicio de sesión y permite que el cliente recibir actualizaciones de servicio de actualización de Windows Server o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.

  - **Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

Para más detalles sobre la interoperabilidad entre clientes y versiones de clientes, mire [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.

