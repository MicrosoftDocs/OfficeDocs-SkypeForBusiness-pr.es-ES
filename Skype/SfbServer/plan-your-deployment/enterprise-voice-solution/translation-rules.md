---
title: Reglas de conversión en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Obtenga información sobre las reglas de conversión y marcar la normalización de cadenas en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: ff3718e89d152a2b6c7d1c78ccaaa055d00ffcdb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="translation-rules-in-skype-for-business-server-2015"></a>Reglas de conversión en Skype Empresarial Server 2015
 
Obtenga información sobre las reglas de conversión y marcar la normalización de cadenas en Skype para Telefonía IP empresarial de Business Server.
  
 Telefonía IP empresarial requiere que todas las cadenas de marcado se normaliza en formato E.164 con el fin de realizar la búsqueda de número inversa (RNL). Las reglas de conversión son compatibles con los números y los números de llamada. Thetrunk igual (es decir, la puerta de enlace asociada, centralita privada (PBX) o troncal SIP) puede exigir que los números en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de redirigirlo al tronco del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y cambiarlo por 0144.
  
Con la conversión de la ruta saliente del servidor, puedes reducir los requisitos de configuración de cada tronco del mismo nivel individual para convertir los números de teléfono en un formato de marcado local. Cuando planee las puertas de enlace y cuántas puertas de enlace, para asociar a un clúster de servidor de mediación específico, puede ser útil para compañeros de grupo troncal con local similar requisitos de marcado. Así, se puede reducir la cantidad de reglas de conversión necesarias y el tiempo necesario para escribirlas.
  
> [!IMPORTANT]
> Asociar una o más reglas de traducción con una configuración de troncales de Telefonía IP empresarial debe utilizarse como alternativa a la configuración de las reglas de conversión en el mismo nivel de tronco. No asociar las reglas de conversión con la configuración de troncales de Telefonía IP empresarial si ha configurado reglas de traducción en el mismo nivel de tronco, porque las dos reglas entran en conflicto. 
  
## <a name="example-translation-rules"></a>Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para el tronco del mismo nivel.
  
Para obtener más información acerca de cómo implementar las reglas de conversión, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.
  
|**Descripción**|**Dígitos iniciales**|**Longitud**|**Dígitos a quitar**|**Dígitos para agregar**|**Patrón de coincidencia**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Marcado convencional de larga distancia de EE. UU.  <br/> (eliminar el '+')  <br/> |+ 1  <br/> |Exactamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10}) $  <br/> |$1  <br/> |+14255551010 se convierte en 14255551010  <br/> |
|Marcado internacional de larga distancia de EE. UU.  <br/> (eliminar '+' y agregue 011)  <br/> |+  <br/> |11 como mínimo  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 se convierte en 011441235551010  <br/> |
   

