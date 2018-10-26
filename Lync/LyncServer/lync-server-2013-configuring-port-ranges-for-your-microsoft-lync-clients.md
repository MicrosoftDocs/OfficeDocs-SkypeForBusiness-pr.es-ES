---
title: Configuración de los intervalos de puertos para clientes de Microsoft Lync
TOCTitle: Configuración de los intervalos de puertos para clientes de Microsoft Lync
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48274753
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los intervalos de puertos para clientes de Microsoft Lync

 

_**Última modificación del tema:** 2015-03-09_

De forma predeterminada, las aplicaciones cliente de Lync pueden usar cualquier puerto entre los puertos 1024 y 65535 en sesiones de comunicación. Esto se debe a que los intervalos de puertos específicos no están habilitados automáticamente para los clientes. Para usar la Calidad de servicio, deberá reasignar los tipos de tráfico (audio, vídeo, multimedia, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos única. Para ello, utilice el cmdlet Set-CsConferencingConfiguration.

Puede determinar qué intervalos de puertos se están utilizando actualmente para las sesiones de comunicación ejecutando el comando siguiente desde el Shell de administración de Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Si no ha realizado ningún cambio en la configuración de conferencia desde la instalación de Lync Server 2013, el sistema debería devolver información que incluya los valores de propiedad siguientes:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si presta atención a los resultados anteriores, verá que hay dos elementos de gran importancia. En primer lugar, la propiedad ClientMediaPortRangeEnabled está establecida como False:

    ClientMediaPortRangeEnabled : False

Esto es importante porque cuando esta propiedad se establece como False, los clientes de Lync utilizan siempre cualquier puerto disponible entre los puertos 1024 y 65535 en sesiones de comunicación. Esto tiene lugar independientemente de cuál sea la configuración del resto de puertos (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto de puertos específico (cosa que puede hacer si tiene planeado implementar el servicio de calidad de servicio), deberá habilitar en primer lugar los intervalos de puertos multimedia de clientes. Para ello, utilice el comando de Windows PowerShell siguiente:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos multimedia para la recopilación global de opciones de configuración de conferencia; sin embargo, esta configuración también puede aplicarse al ámbito del sitio o del servicio (solo para el servicio de Servidor de conferencia). Para habilitar los intervalos de puertos multimedia de clientes para un servidor o sitio específicos, especifique la identidad de dicho servidor o sitio al llamar al cmdlet Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

De forma alternativa, puede usar este comando para habilitar intervalos de puertos para todas las opciones de configuración de conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

El segundo elemento importante es que los resultados de muestra indican que, de forma predeterminada, los intervalos de puertos multimedia configurados para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar el servicio QoS, cada uno de estos intervalos de puertos debe ser único. Por ejemplo, puede configurar los intervalos de puertos del modo siguiente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico cliente</th>
<th>Inicio de puerto</th>
<th>Intervalo de puerto</th>
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


En la tabla anterior, los intervalos de puertos de clientes representan un subconjunto de intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones estaba configurado para utilizar los puertos del 40803 al 49151. En los equipos cliente, el uso compartido de aplicaciones está configurado para utilizar los puertos del 42000 al 42019. Esto facilita la administración de QoS: los puertos de los clientes no tienen que representar ningún subconjunto de los puertos utilizados en el servidor. (Por ejemplo, en los equipos cliente puede configurar el uso compartido de aplicaciones para que utilice los puertos del 10000 al 10019.) Sin embargo, se recomienda crear un subconjunto de los intervalos de puertos del servidor para los intervalos de puertos de los clientes.

Además, se habrá dado cuenta de que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se han reservado 20 puertos para el uso compartido de aplicaciones en los clientes. Esta es la práctica recomendada, aunque no puede considerarse como la norma más rápida y eficaz. En general, puede utilizar cada uno de los puertos disponibles para representar una única sesión de comunicación: si tiene 100 puertos disponibles en un intervalo de puertos, quiere decir que el equipo en cuestión podría participar en 100 sesiones de comunicación como máximo en un momento determinado. Puesto que, probablemente, los servidores participarán en muchas más conversaciones que los clientes, tiene sentido abrir más puertos en los servidores que en los clientes. Si se reservan 20 puertos para el uso compartido de aplicaciones en un cliente, quiere decir que el usuario podría participar en 20 sesiones de uso compartido de aplicaciones con el dispositivo especificado y de forma simultánea, lo cual es suficiente para la mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la recopilación global de opciones de configuración de conferencia, utilice el comando de Shell de administración de Lync Server siguiente:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, utilice este comando para asignar estos intervalos de puertos a todas las opciones de configuración de conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deberán cerrar la sesión de Lync y volver a iniciarla antes de que surtan efecto estos cambios.


> [!NOTE]
> También puede habilitar los intervalos de puertos multimedia y, a continuación, asignar dichos intervalos de puertos mediante un comando simple. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>


