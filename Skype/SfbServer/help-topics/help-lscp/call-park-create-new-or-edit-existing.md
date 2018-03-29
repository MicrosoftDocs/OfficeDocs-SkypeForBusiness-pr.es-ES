---
title: Parque de llamada crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Intervalos numéricos llamada Park definen los números temporales donde se conservan las llamadas aparcadas hasta que alguien recupera ellos o el tiempo de espera.
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamiento de llamadas: Crear nuevo o editar existente
 
Intervalos numéricos llamada Park definen los números temporales donde se conservan las llamadas aparcadas hasta que alguien recupera ellos o el tiempo de espera.
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Nombre** Escriba un nombre descriptivo que identifica el intervalo de números. Tras guardarlo, el nombre no se podrá cambiar.
    
- **Número de intervalo** En el primer campo, escriba el número de comienzo del intervalo de números. En el segundo campo, escriba el número final del intervalo de números.
    
  - El número inicial del intervalo debe ser menor o igual al número final.
    
  - El valor del número inicial del intervalo debe tener la misma longitud que el número final.
    
  - El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.
    
  - Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.
    
  - Valores válidos: debe coincidir con la cadena de expresión regular ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d {0,8}). Esto significa que el valor debe ser una cadena que comienza con el carácter de cualquier \* o # o un número del 1 al 9 (el primer carácter no puede ser cero). Si el primer carácter es \* o #, el carácter siguiente debe ser un número del 1 al 9 (no puede ser cero). Los caracteres siguientes pueden ser cualquier número del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no es \* o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido por un máximo de ocho caracteres, cada uno un número del 0 al 9 (por ejemplo: 915551212; 41212; 300).
    
  - Conviene no tener más de 50.000 números por grupo de servidores. Cada intervalo de números suele estar formado por 100 números o menos, pero puede ser mucho mayor, siempre y cuando tenga menos de 10.000 números. Por ejemplo, en lugar de especificar el número inicial "7000000" y el número final "8000000", piense en especificar el número inicial "7000000" y el número final "7000100".
    
- **FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o identificador del servicio de aplicación que hospeda la aplicación llamada parque de servicio. Todas las llamadas estacionadas en números correspondientes al intervalo acotado por el número inicial y el número final de cada intervalo de números se enrutarán a este servidor o grupo de servidores.
    
Para obtener detalles acerca de llamada Park características y capacidades, consulte [Plan para el parque de llamada en Skype para negocios 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos numéricos llamada Park, vea [Configurar las extensiones de número de teléfono para llamadas de estacionamiento](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).
  

