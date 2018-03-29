---
title: Consultas de base de datos de QoE de ejemplo
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Esta sección contiene ejemplos de consultas de la base de datos de calidad de la experiencia (QoE).
ms.openlocfilehash: 20ca6bc8aea6035ebe27fc5f77d512464cd82dcc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="d1e1e-103">Consultas de base de datos de QoE de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1e1e-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="d1e1e-104">Esta sección contiene ejemplos de consultas de la base de datos de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="d1e1e-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="d1e1e-105">Utilice el ejemplo siguiente para obtener el promedio la inestabilidad y pérdida de paquetes para todas las secuencias de audio.</span><span class="sxs-lookup"><span data-stu-id="d1e1e-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="d1e1e-106">Utilice el siguiente ejemplo para encontrar el número total de conferencias que utilizan la consola de reunión.</span><span class="sxs-lookup"><span data-stu-id="d1e1e-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync

```

<span data-ttu-id="d1e1e-107">Utilice el siguiente ejemplo para obtener ConversstionalMOS, SendingMOS y ListendingMOS por el dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="d1e1e-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc

```


