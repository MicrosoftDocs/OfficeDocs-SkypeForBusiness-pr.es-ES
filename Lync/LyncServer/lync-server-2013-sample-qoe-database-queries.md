---
title: 'Lync Server 2013: Consultas de base de datos de QoE de ejemplo'
TOCTitle: Consultas de base de datos de QoE de ejemplo
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398100(v=OCS.15)
ms:contentKeyID: 48274292
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consultas de base de datos de QoE de ejemplo en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-17_

Esta sección contiene ejemplos de consultas de la base de datos QoE (Calidad de la experiencia).

Utilice el siguiente ejemplo para obtener la tasa media de pérdida de paquetes y vibración de todas las secuencias de audio.

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

Utilice el siguiente ejemplo para conocer el número total de conferencias que utilizaron la consola Meeting.

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

Utilice el siguiente ejemplo para obtener los valores de ConversationalMOS, SendingMOS y ListendingMOS por dispositivo de captura.

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

