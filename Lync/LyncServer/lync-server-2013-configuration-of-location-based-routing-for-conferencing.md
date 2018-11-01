---
title: 'Lync Server 2013: configuración de enrutamiento basado en ubicación para conferencias'
TOCTitle: Configuración del enrutamiento basado en ubicación para conferencias
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56271362
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del enrutamiento basado en ubicación para conferencias de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La aplicación de conferencias con enrutamiento basado en ubicación toma como base la configuración del enrutamiento basado en ubicación de Lync Server 2013. Estas son las opciones de configuración principales:

  - La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red. Para poder exigir el enrutamiento basado en ubicación, se deben definir en Lync Server un sitio de red y las subredes asociadas.

  - Para exigir el enrutamiento basado en ubicación de las reuniones, los participantes de Lync deben estar habilitados para el enrutamiento basado en ubicación.

  - Para exigir el enrutamiento basado en ubicación de los extremos de RTC que se unen a las reuniones, el tronco SIP que se use para conectar los extremos de RTC debe estar configurado para el enrutamiento basado en ubicación.

Para más información sobre cómo implementar y configurar el enrutamiento basado en ubicación de Lync Server 2013, consulte [Configurar el enrutamiento basado en ubicación](lync-server-2013-configuring-location-based-routing.md).

## Habilitación de la aplicación de conferencias con enrutamiento basado en ubicación

La aplicación de conferencias con enrutamiento basado en ubicación está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, tiene que determinar la prioridad que debe asignar a la aplicación. Para determinar la prioridad, ejecute el siguiente cmdlet en Shell de administración de Lync Server:

Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>

En este cmdlet, \<Pool FQDN\> es el grupo en el que se va a habilitar la aplicación de conferencias con enrutamiento basado en ubicación.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Lync Server y el valor de prioridad de cada una de ellas. A la aplicación de conferencias con enrutamiento basado en ubicación se le debe asignar un valor de prioridad mayor que el de la aplicación “UdcAgent” y menor que el de las aplicaciones “DefaultRouting”, “ExumRouting” y “OutboundRouting”. Le recomendamos que asigne a la aplicación de conferencias con enrutamiento basado en ubicación un valor de prioridad que sea un punto superior al de la aplicación “UdcAgent”.

Por ejemplo, si la aplicación “UdcAgent” tiene un valor de prioridad de “2”, la aplicación “DefaultRouting” tiene un valor de prioridad de “8”, la aplicación “ExumRouting” tiene un valor de prioridad de “9” y la aplicación “OutboundRouting” tiene un valor de prioridad de “10”, deberá asignar a la aplicación de conferencias con enrutamiento basado en ubicación un valor de prioridad de “3”. Al hacerlo, la prioridad de las aplicaciones quedará ordenada así: otras aplicaciones (prioridades: de 0 a 1), “UdcAgent” (prioridad: 2), aplicación de conferencias con enrutamiento basado en ubicación (prioridad: 3), otras aplicaciones (prioridades: de 4 a 8), “DefaultRouting” (prioridad: 9), “ExumRouting” (prioridad: 10) y “OutboundRouting” (prioridad: 11).

Después de encontrar el valor de prioridad adecuado para la aplicación de conferencias con enrutamiento basado en ubicación, escriba el siguiente cmdlet para cada grupo de servidores front-end o servidor Standard Edition que hospede a usuarios habilitados para el enrutamiento basado en ubicación:

New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Por ejemplo:

New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Después de usar este cmdlet, reinicie todos los servidores front-end del grupo o los servidores Standard Edition en los que esté habilitada la aplicación de conferencias con enrutamiento basado en ubicación.

> [!IMPORTANT]  
> El cumplimiento del enrutamiento basado en ubicación por parte de las conferencias o las transferencias consultivas no se exigirá hasta que se reinicien todos los servidores front-end de los grupos o servidores Standard Edition correspondientes. Si configura <strong>–Critical</strong> como <strong>$true</strong> en los cmdlets anteriores, los servicios de Lync se reiniciarán de inmediato. Si no quiere que estos servicios se reinicien inmediatamente, configure <strong>–Critical</strong> como <strong>$false</strong> de momento y, luego, utilice <strong>Set-CsServerApplication</strong> para cambiar <strong>-Critical</strong> a <strong>$true</strong> más adelante, después de reiniciarse los servicios.



Después de habilitar correctamente la aplicación de conferencias de enrutamiento basado en ubicación y de reiniciar todos los servidores de Lync correspondientes, todas las conferencias organizadas por usuarios de Lync y habilitadas para el enrutamiento basado en ubicación se supervisarán para evitar que se omitan los números de pago de RTC

