---
title: Estacionamiento de llamadas crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Intervalos de números de estacionamiento de llamadas definición los números temporales donde se conservan las llamadas estacionadas hasta que alguien las recupera o superan el tiempo de espera.
ms.openlocfilehash: 4052354ac50a3881817593485567a8197175b05f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248428"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamiento de llamadas: Crear nuevo o editar existente

Intervalos de números de estacionamiento de llamadas definición los números temporales donde se conservan las llamadas estacionadas hasta que alguien las recupera o superan el tiempo de espera.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifica el intervalo de números. Tras guardarlo, el nombre no se podrá cambiar.

- **Intervalo de número** En el primer campo, escriba el número inicial del intervalo numérico. En el segundo campo, escriba el número final del intervalo de números.

  - El número inicial del intervalo debe ser menor o igual al número final.

  - El valor del número inicial del intervalo debe tener la misma longitud que el número final.

  - El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.

  - Si el intervalo numérico comienza con el carácter \* o #, el intervalo debe ser mayor que 100.

  - Valores válidos: debe coincidir con la cadena de expresión regular ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}). Esto significa que el valor debe ser una cadena que empieza por puede ser el carácter \* o # o un número del 1 al 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o #, el carácter siguiente debe ser un número del 1 al 9 (no puede ser cero). Los caracteres siguientes pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no es \* o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de un máximo de ocho caracteres, cada un número de 0 a 9 (por ejemplo: 915551212; 41212; 300).

  - Conviene no tener más de 50.000 números por grupo de servidores. Cada intervalo de números suele estar formado por 100 números o menos, pero puede ser mucho mayor, siempre y cuando tenga menos de 10.000 números. Por ejemplo, en lugar de especificar el número inicial "7000000" y el número final "8000000", piense en especificar el número inicial "7000000" y el número final "7000100".

- **FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o ID de la aplicación que hospeda la aplicación de estacionamiento de llamadas de servicio. Todas las llamadas estacionadas en números correspondientes al intervalo acotado por el número inicial y el número final de cada intervalo de números se enrutarán a este servidor o grupo de servidores.

Para obtener información detallada sobre las características de estacionamiento de llamadas y funciones, consulte [Plan de estacionamiento de llamadas en Skype para la empresa](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener información detallada sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configurar extensiones de número de teléfono para estacionar llamadas](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


