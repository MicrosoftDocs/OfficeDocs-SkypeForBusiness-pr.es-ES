---
title: "Visualización de información sobre troncos SIP individuales en Lync Server 2013"
TOCTitle: "Aff. des inf. sur les jonctions SIP individuelles dans Lync Server 2013"
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49889531
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información sobre troncos SIP individuales en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Los enlaces troncales SIP se usan para conectar la red telefónica de voz sobre IP de Microsoft Lync Server 2013 con la red telefónica conmutada (RTC). En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.

Sin embargo, en Lync Server 2013, ahora es posible asignar varios enlaces troncales a una única puerta de enlace RTC. Esto significa que las puertas de enlace y los enlaces troncales ya no son únicos ni idénticos. En su lugar, los administradores deben usar el nuevo cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para ver información sobre un enlace troncal SIP individual.

El cmdlet Get-CsTrunk se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Ver información sobre todos los enlaces troncales SIP

  - El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:
    
        Get-CsTrunk

## Ver información sobre un enlace troncal SIP específico

  - Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## Ver información sobre todos los enlaces troncales SIP asignados a un grupo

  - En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

