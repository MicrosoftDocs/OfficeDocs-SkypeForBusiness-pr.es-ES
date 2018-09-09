---
title: Reglas de conversión de Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Obtenga información sobre las reglas de conversión y de marcado de normalización de cadenas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e32cdd3f3dd21ac4aa87dcdd7eecddf8be9153e6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886299"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Reglas de conversión de Skype para Business Server

Obtenga información sobre las reglas de conversión y de marcado de normalización de cadenas en Skype para Business Server Enterprise Voice.

 Enterprise Voice requiere que todas las cadenas de marcado puede normalizar al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL). Reglas de conversión se admiten para los números de llamada y los números de llamada. Punto de Thetrunk (es decir, la puerta de enlace asociada, central de conmutación (PBX) o tronco SIP) puede requerir que los números de estar en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de redirigirlo al tronco del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y cambiarlo por 0144.

Con la conversión de la ruta saliente del servidor, puedes reducir los requisitos de configuración de cada tronco del mismo nivel individual para convertir los números de teléfono en un formato de marcado local. Al planear qué puertas de enlace y cuántas puertas de enlace, para asociar a un clúster de servidor de mediación específico, puede resultar útil para elementos del mismo nivel tronco grupo con local similar requisitos de marcado. Así, se puede reducir la cantidad de reglas de conversión necesarias y el tiempo necesario para escribirlas.

> [!IMPORTANT]
> Asociación de una o varias reglas de traducción con una configuración de tronco de Enterprise Voice debe usarse como alternativa a la configuración de reglas de conversión en el mismo nivel de tronco. No asocie reglas de conversión con una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en el mismo nivel de tronco, debido a que las dos reglas entran en conflicto.

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para el tronco del mismo nivel.

Para obtener información detallada acerca de cómo implementar reglas de conversión, consulte [Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.

|**Descripción**|**Dígitos iniciales**|**Longitud**|**Dígitos que se van a quitar**|**Dígitos que se van a agregar**|**Patrón de comparación**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Marcado convencional de larga distancia de EE. UU.  <br/> (quite el '+')  <br/> |+ 1  <br/> |Exactamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 se convierte en 14255551010  <br/> |
|Marcado internacional de larga distancia de EE. UU.  <br/> (quite el '+' y agregue 011)  <br/> |+  <br/> |11 como mínimo  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 se convierte en 011441235551010  <br/> |


