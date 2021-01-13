---
title: Tabla TraceRoute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831330"
---
# <a name="traceroute-table"></a>Tabla TraceRoute
 
La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Fecha y hora en que empezó la llamada.  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal, Externa  <br/> |Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, Externa  <br/> |Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:  <br/> 0- Audio  <br/> 1 - Vídeo  <br/> 2- Vídeo panorámico  <br/> 3- Uso compartido de aplicaciones y escritorio  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |Extremo que ha realizado la llamada.  <br/> |
|**Salto** <br/> |entero  <br/> ||Salto de red.  <br/> |
|**IPAddressKey** <br/> |entero  <br/> |Externo  <br/> |Identificador único de la dirección IP. La información de la dirección IP se almacena en la [tabla IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |entero  <br/> ||Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.  <br/> |
   

