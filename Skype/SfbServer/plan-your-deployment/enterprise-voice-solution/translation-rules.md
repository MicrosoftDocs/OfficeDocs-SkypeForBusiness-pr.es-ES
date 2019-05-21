---
title: Reglas de traducción en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Obtenga más información sobre las reglas de traducción y la normalización de marcado de cadenas en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297368"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Reglas de traducción en Skype empresarial Server

Obtenga más información sobre las reglas de traducción y la normalización de marcado de cadenas en Skype empresarial Server Enterprise Voice.

 La telefonía IP empresarial requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL). Se admiten las reglas de traducción para los números llamados números y números de llamadas. El tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco del SIP) puede requerir que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de redirigirlo al tronco del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y cambiarlo por 0144.

Con la conversión de la ruta saliente del servidor, puedes reducir los requisitos de configuración de cada tronco del mismo nivel individual para convertir los números de teléfono en un formato de marcado local. Cuando se planean las puertas de enlace y el número de puertas de enlace para asociarlas con un clúster de servidor de mediación específico, puede resultar útil agrupar los pares de troncales con requisitos de marcado local similares. Así, se puede reducir la cantidad de reglas de conversión necesarias y el tiempo necesario para escribirlas.

> [!IMPORTANT]
> La Asociación de una o más reglas de traducción con una configuración de telefonía IP empresarial debe utilizarse como alternativa a la configuración de reglas de traducción en el sistema troncal. No asociar reglas de traducción con una configuración de troncal empresarial de voz si ha configurado reglas de traducción en el sistema troncal del mismo nivel, porque las dos reglas podrían entrar en conflicto.

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para el tronco del mismo nivel.

Para obtener más información sobre cómo implementar reglas de conversión, mira [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación referente a la implementación.

|**Descripción**|**Dígitos iniciales**|**Longitud**|**Dígitos que se van a quitar**|**Dígitos que se van a agregar**|**Patrón de comparación**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Marcado convencional de larga distancia de EE. UU.  <br/> (separa ' + ')  <br/> |+1  <br/> |Exactamente 12  <br/> |1  <br/> |,0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+14255551010 se convierte en 14255551010  <br/> |
|Marcado internacional de larga distancia de EE. UU.  <br/> (destaque ' + ' y agregar 011)  <br/> |+  <br/> |11 como mínimo  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011$1  <br/> |+441235551010 se convierte en 011441235551010  <br/> |


