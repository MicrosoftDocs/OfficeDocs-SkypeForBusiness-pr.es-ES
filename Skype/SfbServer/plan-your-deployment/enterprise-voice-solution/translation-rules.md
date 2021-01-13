---
title: Reglas de conversión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Obtenga información sobre las reglas de conversión y la normalización de cadenas de marcado en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802690"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Reglas de conversión en Skype Empresarial Server

Obtenga información sobre las reglas de conversión y la normalización de cadenas de marcado en Skype Empresarial Server Telefonía IP empresarial.

 Enterprise Voice requiere que todas las cadenas de marcado se normalicen al formato E.164 con el objetivo de realizar la búsqueda inversa de números (RNL). Las reglas de conversión se admiten tanto para números llamados como para números de llamada. El sistema del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP) puede requerir que los números se den en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.

Mediante la conversión de la ruta saliente del servidor, se pueden reducir los requisitos de configuración de cada entidad del mismo nivel que el tronco individual para convertir los números de teléfono en un formato de marcado local. Al planear qué puertas de enlace y cuántas puertas de enlace se asociarán a un clúster de servidor de mediación específico, puede resultar útil agrupar troncos del mismo nivel con requisitos de marcado locales similares. De este modo, se puede reducir el número de reglas de conversión requeridas y el tiempo necesario para escribirlas.

> [!IMPORTANT]
> La asociación de una o más reglas de conversión con una configuración de tronco Telefonía IP empresarial debe usarse como alternativa a la configuración de reglas de conversión en el tronco del mismo nivel. No asocie reglas de conversión con una configuración de tronco Telefonía IP empresarial si ha configurado reglas de conversión en el tronco del mismo nivel, porque las dos reglas pueden estar en conflicto.

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para la entidad del mismo nivel que el tronco.

Para obtener más información acerca de cómo implementar reglas de conversión, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación referente a la implementación.

|**Descripción**|**Dígitos iniciales**|**Length**|**Dígitos que se van a quitar**|**Dígitos que se van a agregar**|**Patrón de comparación**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Marcado convencional de larga distancia en EE.UU.  <br/> (quitar el '+')  <br/> |+1  <br/> |Exactamente 12  <br/> |1   <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 se convierte en 14255551010  <br/> |
|Marcado internacional de larga distancia de EE.UU.  <br/> (quitar "+" y agregar 011)  <br/> |+  <br/> |11 como mínimo  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 se convierte en 011441235551010  <br/> |


