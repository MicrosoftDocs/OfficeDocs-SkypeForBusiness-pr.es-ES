---
title: Tabla TraceRoute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294631"
---
# <a name="traceroute-table"></a>Tabla TraceRoute
 
La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Fecha y hora en que comenzó la llamada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Identificador único que se usa para distinguir entre varias llamadas que podrían haber comenzado en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, extranjero  <br/> |Representa el tipo de línea de vídeo que se usa en la llamada. Los valores permitidos son:  <br/> 0: audio  <br/> 1-video  <br/> 2-video panorámico  <br/> 3-uso compartido de aplicaciones y escritorio  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Extremo que hizo la llamada.  <br/> |
|**Únicos** <br/> |int  <br/> ||Salto de red/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Extranjero  <br/> |Identificador único de la dirección IP. La información de la dirección IP se almacena en la [tabla dirección](ipaddress.md)IP.  <br/> |
|**RTT** <br/> |int  <br/> ||Tiempo de ida y vuelta. El tiempo de ida y vuelta mide la cantidad de tiempo que se tarda en llegar un paquete de voz a su destino y, a continuación, se envía una notificación de que se ha recibido.  <br/> |
   

