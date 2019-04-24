---
title: Tabla TraceRoute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: En la tabla TraceRoute contiene información de enrutamiento de llamadas. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212077"
---
# <a name="traceroute-table"></a>Tabla TraceRoute
 
En la tabla TraceRoute contiene información de enrutamiento de llamadas. En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Fecha y hora en que comenzó la llamada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, externa  <br/> |Identificador exclusivo utilizado para distinguir entre varias llamadas que pueden haber empezado en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, externa  <br/> |Representa el tipo de línea de vídeo utilizada en la llamada. Los valores permitidos son:  <br/> 0 - audio  <br/> 1 - vídeo  <br/> 2 - vídeo panorámico  <br/> 3 - aplicación o escritorio compartido  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Extremo que realizó la llamada.  <br/> |
|**Salto** <br/> |int  <br/> ||Salto de red /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Externa  <br/> |Identificador único de la dirección IP. Información de la dirección IP se almacena en la [tabla IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Tiempo de ida y vuelta. El tiempo de ida y vuelta mide la cantidad de tiempo que tarda un paquete de voz llegar a su destino y, a continuación, Enviar atrás notificación que recibió.  <br/> |
   

