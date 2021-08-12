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
ms.openlocfilehash: f08b3cf1e007d9ba2258db1d4db86e9af160a8c9286bc75e27ab9c0ea8ece441
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322932"
---
# <a name="traceroute-table"></a>Tabla TraceRoute
 
La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Fecha y hora en que empezó la llamada.  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal, Externa  <br/> |Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, Externa  <br/> |Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:  <br/> 0- Audio  <br/> 1 - Vídeo  <br/> 2: vídeo panorámico  <br/> 3: uso compartido de aplicaciones y escritorio  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |Extremo que ha realizado la llamada.  <br/> |
|**Salto** <br/> |Entero  <br/> ||Salto de red.  <br/> |
|**IPAddressKey** <br/> |Entero  <br/> |Externo  <br/> |Identificador único de la dirección IP. La información de dirección IP se almacena en la [tabla IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |Entero  <br/> ||Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.  <br/> |
   

