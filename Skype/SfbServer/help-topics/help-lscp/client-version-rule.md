---
title: Regla de versiones de cliente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.
ms.openlocfilehash: 4575155cba6608e4a8f4425f7fc2d38042e62ad2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862827"
---
# <a name="client-version-rule"></a>Regla de versiones de cliente

Una directiva de versión de cliente está compuesta de un conjunto de reglas de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente**:

- Agregar nuevas reglas a una directiva de versión de cliente.

- Modificar las reglas que componen una directiva de versión de cliente existente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Agente de usuario** Puede seleccionar un tipo de cliente de la lista. La siguiente tabla define los códigos de agente de usuario.

|**Nombre de cliente**|**Agente de usuario**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Teléfono Edition, Office Communicator Teléfono  <br/> |OCPhone  <br/> |
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

- **Número de versión** Puede especificar los números de versión de los campos siguientes o usar caracteres comodín para indicar el número de versión del cliente.

  - **Versión principal** Especifica el número que corresponde a la versión principal del cliente.

  - **Versión secundaria** Especifica el número que corresponde a la versión secundaria del cliente.

  - **Compilación** Especifica el número de compilación que corresponde a la versión principal y secundaria del cliente.

  - **Actualizar** Especifica el número que corresponde a la versión actualizada del cliente.

- **Operación de comparación** Puede especificar la operación de coincidencia para la versión de cliente especificada en los pasos anteriores. Las siguientes operaciones están disponibles:

  - **Igual que**

  - **No es**

  - **Anterior a**

  - **Anterior a o igual que**

  - **Posterior a**

  - **Posterior a o igual que**

- **Acción** Puede especificar la acción que se debe realizar cuando se cumplan los criterios de los pasos anteriores. Están disponibles las siguientes acciones:

  - **Permitir** Permite que el cliente inicie sesión.

  - **Permitir y actualizar** Permite al cliente iniciar sesión y recibir actualizaciones de Windows Server Update Service o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.

    > [!NOTE]
    > Si selecciona esta acción, aparecerá una notificación la próxima vez que los usuarios inicien sesión en Skype Empresarial. La notificación comunica que hay una actualización disponible, aunque las actualizaciones aún no se hayan publicado en Windows Server Update Service o en Microsoft Update. Para evitar confusiones, se recomienda elegir esta acción solo después de que haya actualizaciones disponibles.

  - **Permitir con dirección URL** Permite al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión de cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

  - **Bloquear** Impide que el cliente inicia sesión.

  - **Bloquear y actualizar** Impide que el cliente inicia sesión y permite al cliente recibir actualizaciones de Windows Servicio de actualización de servidor o Microsoft Update. Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.

  - **Bloquear con dirección URL**   Impide al cliente iniciar sesión y muestra un mensaje sobre dónde descargar otra versión del cliente. Puede especificar la dirección URL en el campo **Dirección URL**.

Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación de planeación. Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.