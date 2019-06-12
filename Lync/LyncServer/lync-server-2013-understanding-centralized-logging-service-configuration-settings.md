---
title: Descripción de las opciones de configuración del servicio de registro centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Descripción de la configuración del servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El servicio de registro centralizado está configurado para definir qué debe recopilar el servicio de registro, cómo se recopila, de dónde se recopilará y de cuál es la configuración de registro. Define estas configuraciones de modo global (es decir, para toda la implementación) o para un sitio (es decir, para un sitio específico de la implementación). Cualquier registro que defina utilizará la configuración apropiada de la identidad que utiliza para iniciar, detener, vaciar y buscar registros.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para mostrar la configuración del servicio de registro centralizado actual

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en un símbolo de la línea de comandos:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Puede restringir o expandir el ámbito de los parámetros de configuración devueltos por <CODE>-Identity</CODE> la definición de un ámbito, como "sitio: Redmond" para devolver solo el CsClsConfiguration del sitio Redmond. Si desea detalles sobre una parte determinada de la configuración, puede canalizar la salida en otro cmdlet de Windows PowerShell. Por ejemplo, para obtener detalles sobre los escenarios definidos en la configuración del sitio "Redmond", escriba lo siguiente:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Salida de ejemplo de Get-CsClsConfiguration.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Salida de ejemplo de Get-CsClsConfiguration.")
    
    El resultado del cmdlet muestra la configuración actual del servicio de registro centralizado.
    
    
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
    <td><p>Grupos de seguridad definidos que controlan quiénes (es decir, qué miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. Sitio, en este contexto, es el sitio definido en el generador de topología.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Regions</strong></p></td>
    <td><p>Las regiones definidas se utilizan para recopilar SecurityGroups en una región, por ejemplo EMEA.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>Ruta de acceso definida a la ubicación donde se escriben los archivos de registro en los equipos. CLSAgent escribe los archivos de registro y se ejecuta en el contexto del servicio de red. En este caso,% TEMP% se expande a%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido, incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Ubicación en la que se buscarán archivos con formato de mensaje de seguimiento. Los archivos de formato de mensaje de seguimiento se usan para convertir los archivos binarios en un formato legible para el usuario.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Ruta de acceso definida de la ubicación en la que se escriben los archivos caché en los equipos. CLSAgent escribe los archivos caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos caché y los archivos de registro se escriben en el mismo directorio.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>Puede definir una ruta de acceso de convención de nomenclatura universal (UNC) para recibir los archivos caché durante las operaciones de registro.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Definido como el tiempo máximo, en días, que se pueden retener los archivos caché.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Definido como el porcentaje de espacio en disco que pueden utilizar los archivos caché.</p></td>
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


</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

