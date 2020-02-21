---
title: Descripción de las opciones de configuración del servicio de registro centralizado
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
ms.openlocfilehash: b326f7ee869b060a423696817c21d7cb763bb0a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a6c12-102">Información sobre las opciones de configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6c12-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6c12-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a6c12-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a6c12-104">El servicio de registro centralizado está configurado para definir lo que debe recopilar el servicio de registro, cómo lo recopila, dónde se recopilará y cuál será la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a6c12-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="a6c12-105">Estas opciones se definen de forma global (es decir, para toda la implementación) o para un sitio (es decir, un sitio con nombre de la implementación).</span><span class="sxs-lookup"><span data-stu-id="a6c12-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="a6c12-106">Cualquier registro que defina utilizará las configuraciones apropiadas para la identidad que utiliza para iniciar, detener, vaciar y buscar registros.</span><span class="sxs-lookup"><span data-stu-id="a6c12-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="a6c12-107">Para mostrar la configuración actual del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="a6c12-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="a6c12-108">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a6c12-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a6c12-109">Escriba lo siguiente en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="a6c12-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="a6c12-110">Puede restringir o ampliar el ámbito de las opciones de configuración que se devuelven al definir <CODE>-Identity</CODE> y un ámbito, como "site: Redmond" para devolver solo el CsClsConfiguration para el sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="a6c12-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="a6c12-111">Si desea obtener información detallada sobre una parte determinada de la configuración, puede canalizar la salida a otro cmdlet de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6c12-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="a6c12-112">Por ejemplo, para obtener detalles sobre los escenarios definidos en la configuración del sitio "Redmond", escriba:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="a6c12-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="a6c12-113">![Resultado de ejemplo de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Resultado de ejemplo de Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="a6c12-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="a6c12-114">El resultado del cmdlet muestra la configuración actual del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="a6c12-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a6c12-115">Opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="a6c12-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="a6c12-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6c12-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-117"><strong>Identidad</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p103">Identifica el ámbito y el nombre de esta configuración. Hay solamente una configuración global y una configuración por sitio.</span><span class="sxs-lookup"><span data-stu-id="a6c12-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-121">Listado de todos los escenarios que se definen para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="a6c12-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-123">Términos de búsqueda definidos para la configuración.</span><span class="sxs-lookup"><span data-stu-id="a6c12-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="a6c12-124">Office 365, no en implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="a6c12-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-126">Grupos de seguridad definidos que controlan quiénes (es decir, miembros de los grupos de seguridad) pueden ver equipos basados en el sitio en el que se encuentran.</span><span class="sxs-lookup"><span data-stu-id="a6c12-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="a6c12-127">Sitio, en este contexto, es el sitio tal como se define en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="a6c12-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-128"><strong>Regiones</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-129">Las regiones definidas se utilizan para reunir SecurityGroups en una región, por ejemplo EMEA.</span><span class="sxs-lookup"><span data-stu-id="a6c12-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p106">Ruta definida de la ubicación en la que se escriben los archivos de registro en los equipos. CLSAgent escribe los archivos de registro y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="a6c12-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p107">El parámetro indica el tamaño máximo del archivo de registro antes de que se cree un nuevo archivo de registro de seguimiento de eventos (.etl). Un nuevo archivo de registro se crea cuando se alcanza el tamaño definido incluso si aún no se ha alcanzado el tiempo máximo establecido en EtlFileRolloverMinutes.</span><span class="sxs-lookup"><span data-stu-id="a6c12-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p108">Cantidad máxima definida de tiempo, en minutos, que puede durar un registro antes de que se cree un nuevo archivo .etl. Un nuevo archivo de registro se crea cuando expira el tiempo definido incluso si aún no se ha alcanzado el tamaño máximo establecido en EtlFileRolloverSizeMB.</span><span class="sxs-lookup"><span data-stu-id="a6c12-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p109">Ubicación en la que se buscará archivos con formato de mensaje de seguimiento. Los archivos con formato de mensaje de seguimiento se utilizan para convertir los archivos binarios en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="a6c12-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-p110">Ruta definida de la ubicación en la que se escriben los archivos de caché en los equipos. CLSAgent escribe los archivos de caché y se ejecuta en el contexto del servicio de red. En este caso, %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. De manera predeterminada, los archivos de caché y los archivos de registro se escriben en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="a6c12-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-149">Puede definir una ruta de acceso UNC (convención de nomenclatura universal) para recibir los archivos de caché durante las operaciones de registro.</span><span class="sxs-lookup"><span data-stu-id="a6c12-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-151">Definido como el tiempo máximo, en días, que se pueden retener los archivos de caché.</span><span class="sxs-lookup"><span data-stu-id="a6c12-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-153">Definido como el porcentaje de espacio en disco que pueden utilizar los archivos de caché.</span><span class="sxs-lookup"><span data-stu-id="a6c12-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-154"><strong>Puede componentthrottlelimit</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-155">Definido como la cantidad máxima de seguimientos por segundo que puede producir un componente antes de que se active el limitador de aceleración automático.</span><span class="sxs-lookup"><span data-stu-id="a6c12-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a6c12-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-157">Cantidad de veces en 60 segundos que puede excederse el ComponentThrottleLimit.</span><span class="sxs-lookup"><span data-stu-id="a6c12-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a6c12-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a6c12-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="a6c12-159">La versión mínima del CLSAgent que se permite ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a6c12-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="a6c12-160">Este elemento está pensado para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6c12-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6c12-161">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a6c12-161">See Also</span></span>


[<span data-ttu-id="a6c12-162">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6c12-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="a6c12-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a6c12-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="a6c12-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a6c12-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="a6c12-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a6c12-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="a6c12-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a6c12-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

