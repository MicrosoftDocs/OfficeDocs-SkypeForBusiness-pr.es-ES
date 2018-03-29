---
title: Tabla TraceRoute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabla TraceRoute contiene información de enrutamiento de llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>Tabla TraceRoute
 
La tabla TraceRoute contiene información de enrutamiento de llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Fecha y hora en que comenzó la llamada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, externa  <br/> |Identificador único que se utiliza para distinguir entre varias llamadas que han comenzado en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, externa  <br/> |Representa el tipo de línea de vídeo utilizada en la llamada. Los valores permitidos son:  <br/> 0 - audio  <br/> 1 - vídeo  <br/> 2 - vídeo panorámica  <br/> 3 - aplicación o escritorio compartido  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Extremo que realizó la llamada.  <br/> |
|**Salto** <br/> |int  <br/> ||Salto de red /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Externa  <br/> |Identificador único de la dirección IP. Información de dirección IP se almacena en la [tabla de dirección IP](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Tiempo de ida y vuelta. El tiempo de ida y vuelta mide la cantidad de tiempo que tarda un paquete de voz llegar a su destino y, a continuación, enviar una notificación de espera que recibió.  <br/> |
   

