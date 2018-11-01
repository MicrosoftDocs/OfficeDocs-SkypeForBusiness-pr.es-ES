---
title: "Introducción a las opciones de configuración del servicio de registro centralizado"
TOCTitle: "Présentation des param. de config. du service de journalisation centralisée"
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49889049
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción a las opciones de configuración del servicio de registro centralizado

 

_**Última modificación del tema:** 2015-03-09_

El Servicio de registro centralizado está configurado para definir lo que el servicio de inicio de sesión debe recopilar, de qué modo lo debe hacer, de qué lugares y cuál es la configuración de registro. Define estas configuraciones de modo global (es decir, para la implementación total) o para un sitio (es decir, un sitio específico de su implementación). Cualquier registro que defina utilizará las configuraciones apropiadas para la identidad que utiliza para iniciar, detener, vaciar y buscar registros.

## Mostrar la configuración actual de Servicio de registro centralizado

Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

Escriba lo siguiente en un símbolo del sistema:

    Get-CsClsConfiguration

> [!TIP]  
> Puede acotar o expandir el ámbito de los parámetros de configuración que se devuelven definiendo <code>-Identity</code> y un ámbito, como “Site:Redmond” para devolver solamente CsClsConfiguration para el sitio Redmond. Si quiere información detallada sobre una parte determinada de la configuración, puede transferir el resultado a otro Windows PowerShell. Por ejemplo, para obtener información detallada sobre los escenarios definidos en la configuración para el sitio “Redmond”, escriba: <code>Get-CsClsConfiguration -Identity &quot;site:Redmond&quot; | Select-Object -ExpandPropery Scenarios</code>



![Salida de ejemplo de Get-CsClsConfiguration.](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Salida de ejemplo de Get-CsClsConfiguration.")

El resultado del cmdlet muestra la configuración actual del Servicio de registro centralizado.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opciones de configuración</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Scenarios</strong></p></td>
<td><p>Listado de todos los escenarios que se definen para esta configuración.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>Términos de búsqueda definidos para la configuración. Office 365, no implementaciones locales.</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>Grupos de seguridad definidos que controlan quiénes (es decir, miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. Sitio, en este contexto, es el sitio según se lo define en Generador de topologías.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>Las regiones definidas se utilizan para reunir SecurityGroups en una región, por ejemplo EMEA.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>Ruta definida de la ubicación en la que se escriben los archivos de registro en los equipos. CLSAgent escribe los archivos de registro y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un nuevo archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>Ubicación en la que se buscará archivos con formato de mensaje de seguimiento. Los archivos con formato de mensaje de seguimiento se utilizan para convertir los archivos binarios en un formato legible.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>Ruta definida de la ubicación en la que se escriben los archivos de caché en los equipos. CLSAgent escribe los archivos de caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos de caché y los archivos de registro se escriben en el mismo directorio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>Puede definir una ruta de acceso UNC (convención de nomenclatura universal) para recibir los archivos de caché durante las operaciones de registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>Definido como el tiempo máximo, en días, que se pueden retener los archivos de caché.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>Definido como el porcentaje de espacio en disco que pueden utilizar los archivos de caché.</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>La versión mínima del CLSAgent que se permite ejecutar. Este elemento está pensado para Office 365.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Otros recursos

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

