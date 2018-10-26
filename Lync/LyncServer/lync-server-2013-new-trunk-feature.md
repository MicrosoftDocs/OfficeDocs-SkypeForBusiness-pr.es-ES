---
title: 'Lync Server 2013: Nueva característica de tronco'
TOCTitle: Nueva característica de tronco
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49889400
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nueva característica de tronco en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

En Microsoft Lync Server 2013 pueden definirse varios troncos entre un Servidor de mediación y una puerta de enlace. Microsoft Lync Server 2010 solo permitía un tronco entre un Servidor de mediación y una puerta de enlace RTC. Esta característica ofrece la flexibilidad necesaria para definir troncos adicionales. Un tronco es una asociación lógica entre el FQDN y el puerto de escucha de un Servidor de mediación y el FQDN y el puerto de escucha de una puerta de enlace RTC. Esta nueva capacidad permite definir fácilmente troncos resistentes (en los que los servidores de mediación puedan utilizarse para enrutar llamadas a la misma puerta de enlace RTC), facilitar la interoperabilidad PBX (pueden utilizarse varios troncos con diferentes directivas asociadas entre un IP-PBX y un Servidor de mediación) y crear configuraciones de tronco SIP en las que los Servidores de mediación de diferentes sitios tienen troncos SIP a la portadora referida por el mismo FQDN de portadora.

## Vea también

#### Conceptos

[Nuevas características de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)

