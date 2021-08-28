---
title: Estacionamiento de llamadas Crear nuevo o Editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se desaten.
ms.openlocfilehash: f541a05fffe7f3696cde151f2d9edc8fcb243d73
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620056"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamiento de llamadas: Crear nuevos o editar los existentes

Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se desaten.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifique el intervalo de números. Una vez que guarde el intervalo numérico, el nombre no se podrá cambiar.

- **Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números. En el segundo campo, escriba el número de finalización del intervalo numérico.

  - El número inicial del intervalo debe ser menor o igual al número final del intervalo.

  - El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.

  - El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.

  - Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.

  - Valores válidos: debe coincidir con la cadena de expresión regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Esto significa que el valor debe ser una cadena que comienza con el carácter o # o un número \* del 1 al 9 (el primer carácter no puede ser cero). Si el primer carácter es o #, el siguiente carácter debe ser un número del 1 al \* 9 (no puede ser cero). Los caracteres posteriores pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", " \* 92000", " 95551212" y \* "915551212"). Si el primer carácter no es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de \* 0 a 9 (por ejemplo: 915551212;41212;300).

  - No debe tener más de 50.000 números por grupo de servidores. Cada intervalo numérico normalmente está formado por 100 números o menos, pero puede ser mucho mayor siempre que tenga menos de 10.000 números. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".

- **FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación estacionamiento de llamadas. Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo numérico se enrutarán a este servidor o grupo de servidores.

Para obtener más información acerca de las funciones y características del estacionamiento de [llamadas,](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)vea Plan for Call Park in Skype Empresarial . Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, [vea Configure Teléfono Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).