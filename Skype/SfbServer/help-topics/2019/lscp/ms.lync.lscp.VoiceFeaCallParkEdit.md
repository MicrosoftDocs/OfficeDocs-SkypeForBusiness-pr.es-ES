---
title: Parque de llamadas crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o agota el tiempo.
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290173"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamiento de llamadas: Crear nuevo o editar existente

Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o agota el tiempo.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Escriba un nombre descriptivo que identifique el intervalo de números. Tras guardarlo, el nombre no se podrá cambiar.

- **Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números. En el segundo campo, escriba el número final del intervalo de números.

  - El número inicial del intervalo debe ser menor o igual al número final.

  - El valor del número inicial del intervalo debe tener la misma longitud que el número final.

  - El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.

  - Si el intervalo de números comienza con el \* carácter o #, el intervalo debe ser mayor que 100.

  - Valores válidos: deben coincidir con la cadena de\\expresión regular ([* | #] ? [1{0,7}-9] \d) | ([1-9] \d{0,8}). Esto significa que el valor debe ser una cadena que comienza con el \* carácter o # o un número 1 a 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o #, el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no \* es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo: 915551212; 41212; 300).

  - Conviene no tener más de 50.000 números por grupo de servidores. Cada intervalo de números suele estar formado por 100 números o menos, pero puede ser mucho mayor, siempre y cuando tenga menos de 10.000 números. Por ejemplo, en lugar de especificar el número inicial "7000000" y el número final "8000000", piense en especificar el número inicial "7000000" y el número final "7000100".

- **FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas. Todas las llamadas estacionadas en números correspondientes al intervalo acotado por el número inicial y el número final de cada intervalo de números se enrutarán a este servidor o grupo de servidores.

Para obtener más información sobre las funciones y características de reactivación de llamadas, consulte [Plan for Call Park on Skype empresarial](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos numéricos de estacionamiento, consulte [configurar extensiones de números de teléfono para llamadas de aparcamiento](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


