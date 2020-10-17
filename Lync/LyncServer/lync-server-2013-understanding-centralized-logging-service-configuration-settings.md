---
title: Descripción de las opciones de configuración del servicio de registro centralizado
description: Descripción de las opciones de configuración del servicio de registro centralizado.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f99dbffe15c4b3f0dc13d231c3a2732a8554397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542406"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Información sobre las opciones de configuración del servicio de registro centralizado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El servicio de registro centralizado está configurado para definir lo que debe recopilar el servicio de registro, cómo lo recopila, dónde se recopilará y cuál será la configuración del registro. Estas opciones se definen de forma global (es decir, para toda la implementación) o para un sitio (es decir, un sitio con nombre de la implementación). Cualquier registro que defina utilizará las configuraciones apropiadas para la identidad que utiliza para iniciar, detener, vaciar y buscar registros.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para mostrar la configuración actual del servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente en un símbolo del sistema:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Puede restringir o ampliar el ámbito de las opciones de configuración que se devuelven al definir <CODE>-Identity</CODE> y un ámbito, como "site: Redmond" para devolver solo el CsClsConfiguration para el sitio Redmond. Si desea obtener información detallada sobre una parte determinada de la configuración, puede canalizar la salida a otro cmdlet de Windows PowerShell. Por ejemplo, para obtener detalles sobre los escenarios definidos en la configuración del sitio "Redmond", escriba: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Resultado de ejemplo de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Resultado de ejemplo de Get-CsClsConfiguration.")
    
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
    <td><p><strong>Identidad</strong></p></td>
    <td><p>Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>Listado de todos los escenarios que se definen para esta configuración.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Términos de búsqueda definidos para la configuración. Office 365 o Microsoft 365, no en implementaciones locales.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>Grupos de seguridad definidos que controlan quiénes (es decir, miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran. Sitio, en este contexto, es el sitio tal como se define en Topology Builder.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Regiones</strong></p></td>
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
    <td><p><strong>Puede componentthrottlelimit</strong></p></td>
    <td><p>Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>La versión mínima del CLSAgent que se permite ejecutar. Este elemento está pensado para Office 365 o Microsoft 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>Consulte también


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

