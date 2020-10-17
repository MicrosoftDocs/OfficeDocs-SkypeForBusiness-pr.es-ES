---
title: 'Lync Server 2013: configuración de intervalos de puertos para los clientes de Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77366884d83d29c39c1f19fc710030ea8457dd7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535017"
---
# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configuración de intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

De forma predeterminada, las aplicaciones cliente de Lync pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes. Sin embargo, para poder usar la calidad de servicio, tendrá que volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos. Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios por sí mismos. Los cambios de Puerto solo los pueden realizar los administradores mediante el cmdlet Set-CsConferencingConfiguration.



</div>

Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de conferencia después de instalar Lync Server 2013, debe obtener información que incluya estos valores de propiedad:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si observa atentamente el resultado anterior, verá dos aspectos de importancia. En primer lugar, la propiedad los parámetros clientmediaportrangeenabled se establece en false:

    ClientMediaPortRangeEnabled : False

Esto es importante porque, cuando esta propiedad se establece en false, los clientes de Lync usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto específico de puertos (y esto es algo que desea hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente. Esto se puede hacer con el siguiente comando de Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencia; sin embargo, estas opciones también se pueden aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencia). Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específicos, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Como alternativa, puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda importancia que verá es que el resultado del ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para poder implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único. Por ejemplo, puede configurar los intervalos de puertos como se muestra a continuación:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Puerto inicial</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos de 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019. Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos usados en el servidor. (Por ejemplo, en los equipos cliente podría configurar el uso compartido de aplicaciones para usar, por ejemplo, los puertos de 10000 a 10019). Sin embargo, se recomienda que los intervalos de puertos de cliente sean un subconjunto de los intervalos de puertos del servidor.

Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se configuraron 20 puertos para el uso compartido de aplicaciones en los clientes. Esto también se recomienda, pero no es una regla difícil y rápida. En general, puede considerar cada puerto disponible para representar una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de 100 sesiones de comunicación en un determinado momento. Como es probable que los servidores participen en muchas más conversaciones que los clientes, tiene sentido abrir muchos más puertos en los servidores que en los clientes. La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todo al mismo tiempo. Eso debería ser suficiente para la inmensa mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencia, puede usar el siguiente comando del shell de administración de Lync Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos mismos intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar sesión en Lync y, a continuación, volver a iniciar sesión antes de que estos cambios entren en vigor.

<div>


> [!NOTE]  
> También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

