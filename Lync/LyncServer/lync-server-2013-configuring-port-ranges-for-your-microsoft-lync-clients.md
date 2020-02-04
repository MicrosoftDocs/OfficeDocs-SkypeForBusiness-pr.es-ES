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
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configurar intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

De forma predeterminada, las aplicaciones cliente de Lync pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes. Sin embargo, para usar la calidad de servicio, tendrá que reasignar los diversos tipos de tráfico (audio, vídeo, multimedia, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos. Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios por sí mismos. Los administradores solo pueden hacer cambios en el puerto mediante el cmdlet Set-CsConferencingConfiguration.



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

Si examina detenidamente la salida anterior, verá dos cuestiones de importancia. En primer lugar, la propiedad ClientMediaPortRangeEnabled se establece en false:

    ClientMediaPortRangeEnabled : False

Eso es importante porque, cuando esta propiedad se establece en false, los clientes de Lync usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puertos (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso de un conjunto de puertos especificado (y esto es algo que quiera hacer si piensa implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente. Esto se puede realizar con el siguiente comando de Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencias; sin embargo, esta configuración también se puede aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencias). Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específico, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

También puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda importancia que observará es que la salida de ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único. Por ejemplo, puede configurar los intervalos de puertos como este:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Inicio de Puerto</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>veinte</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019. Esto también se hace principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos que se usan en el servidor. (Por ejemplo, en los equipos cliente, puede configurar el uso compartido de aplicaciones para que lo use, por ejemplo, los puertos 10000 a 10019). Sin embargo, le recomendamos que los intervalos de puertos de cliente sean un subconjunto de intervalos de puertos de servidor.

Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se reservaron 20 puertos para el uso compartido de aplicaciones en los clientes. Esto también se recomienda, pero no es una regla difícil y rápida. En general, puede considerar que cada puerto disponible representa una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos que significa que el equipo en cuestión puede participar, como máximo, de las sesiones de comunicación de 100 en cualquier momento. Dado que es probable que los servidores adquieran parte de muchas más conversaciones que clientes, tiene sentido abrir muchos más puertos en servidores que en los clientes. La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todas al mismo tiempo. Eso debería ser suficiente para la gran mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencias, puede usar el siguiente comando del shell de administración de Lync Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos mismos intervalos de puerto para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar sesión en Lync y, a continuación, iniciar sesión de nuevo antes de que estos cambios se hagan efectivos.

<div>


> [!NOTE]  
> También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

