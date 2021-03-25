---
title: Reglas de traducción en Skype Empresarial Server
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
description: Obtenga información sobre las reglas de traducción y la normalización de cadenas de marcado en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d02e4d3b84c03ee40dddbcb9b174adb66dcd6cd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110636"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Reglas de traducción en Skype Empresarial Server

Obtenga información sobre las reglas de traducción y la normalización de cadenas de marcado en Skype Empresarial Server Telefonía IP empresarial.

 Enterprise Voice requiere que todas las cadenas de marcado se normalicen al formato E.164 con el objetivo de realizar la búsqueda inversa de números (RNL). Las reglas de traducción se admiten tanto para números llamados como para números de llamada. El mismo nivel detrunk (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP) pueden requerir que los números se den en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.

Mediante la conversión de la ruta saliente del servidor, se pueden reducir los requisitos de configuración de cada entidad del mismo nivel que el tronco individual para convertir los números de teléfono en un formato de marcado local. Al planear qué puertas de enlace y cuántas puertas de enlace se asociarán a un clúster de servidor de mediación específico, puede resultar útil agrupar los pares de tronco con requisitos de marcado locales similares. De este modo, se puede reducir el número de reglas de conversión requeridas y el tiempo necesario para escribirlas.

> [!IMPORTANT]
> La asociación de una o más reglas de traducción con una configuración Telefonía IP empresarial tronco debe usarse como alternativa a la configuración de reglas de traducción en el mismo nivel del tronco. No asocie reglas de traducción con una configuración Telefonía IP empresarial tronco si ha configurado reglas de traducción en el mismo nivel del tronco, ya que las dos reglas pueden estar en conflicto.

## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para la entidad del mismo nivel que el tronco.

Para obtener más información acerca de cómo implementar reglas de conversión, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) en la documentación referente a la implementación.

|**Descripción**|**Dígitos iniciales**|**Length**|**Dígitos que se van a quitar**|**Dígitos que se van a agregar**|**Patrón de comparación**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Marcado convencional de larga distancia en EE.UU.  <br/> (quitar el '+')  <br/> |+1  <br/> |Exactamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 se convierte en 14255551010  <br/> |
|Marcado internacional de larga distancia de EE.UU.  <br/> (quitar '+' y agregar 011)  <br/> |+  <br/> |11 como mínimo  <br/> |1  <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 se convierte en 011441235551010  <br/> |