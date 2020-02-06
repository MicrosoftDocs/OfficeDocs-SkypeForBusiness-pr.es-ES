---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: a4d8cb38f30e8c332a9cec0ea90e27c012187d47
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794599"
---
# <a name="client-version-rule"></a>Regla de versiones de cliente

Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:

- Agregar nuevas reglas a una directiva de versión de cliente.

- Modificar las reglas que componen una directiva de versión de cliente existente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Agente de usuario** Puede seleccionar un tipo de cliente de la lista. En la siguiente tabla se recogen los códigos de agente de usuario. Esta lista incluye tipos de clientes heredados, algunos de los cuales ya no se admiten.

|**Nombre de cliente**|**Agente de usuario**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, teléfono de Office Communicator  <br/> |OCPhone  <br/> |
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

- **Número de versión** Puede especificar los números de versión de los siguientes campos, o usar caracteres comodín para indicar el número de versión del cliente.

  - **Versión principal** Especifica el número que corresponde a la versión principal del cliente.

  - **Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.

  - **Crear** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.

  - **Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.

- **Operación de comparación** Puede especificar la operación correspondiente a la versión del cliente que especificó en los pasos anteriores. Las siguientes operaciones están disponibles:

  - **Igual que**

  - **No es**

  - **Anterior a**

  - **Anterior a o igual que**

  - **Posterior a**

  - **Posterior a o igual que**

- **Acción** Puede especificar la acción que se realizará cuando se cumplan los criterios de los pasos anteriores. Están disponibles las siguientes acciones:

  - **Permitir** Permite que el cliente inicie sesión.

  - **Permitir y actualizar** Permite al cliente iniciar y recibir actualizaciones de Windows Server Update Services o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.

    > [!NOTE]
    > Si selecciona esta acción, una notificación aparecerá la próxima vez que los usuarios inicien sesión en Skype empresarial. La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.

  - **Permitir con URL** Permite al cliente iniciar sesión y mostrar un mensaje sobre dónde Descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

  - **Bloquear** Impide que el cliente inicie sesión.

  - **Bloquear y actualizar** Impide que el cliente inicie sesión y permite al cliente recibir actualizaciones de Windows Server Update Services o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.

  - **Bloquear con dirección URL** Impide al cliente iniciar sesión y muestra un mensaje que indica dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

Para obtener más información sobre la interoperabilidad entre los clientes y las versiones de cliente, consulte [interoperabilidad de cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planificación. Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.

