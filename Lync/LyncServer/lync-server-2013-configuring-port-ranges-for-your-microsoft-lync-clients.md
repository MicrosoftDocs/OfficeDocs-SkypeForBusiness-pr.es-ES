---
title: 'Lync Server 2013: configuración de intervalos de puertos para los clientes de Microsoft Lync'
description: 'Lync Server 2013: configuración de intervalos de puertos para los clientes de Microsoft Lync.'
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
ms.openlocfilehash: 1e7fcabf81f8e0110010b1a4fb8e697fb0da986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569996"
---
# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="2c4e6-103">Configuración de intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c4e6-103">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c4e6-104">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="2c4e6-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="2c4e6-105">De forma predeterminada, las aplicaciones cliente de Lync pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-105">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="2c4e6-106">Sin embargo, para poder usar la calidad de servicio, tendrá que volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-106">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="2c4e6-107">Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-107">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c4e6-108">Los usuarios finales no pueden realizar estos cambios por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-108">End users cannot make these changes themselves.</span></span> <span data-ttu-id="2c4e6-109">Los cambios de Puerto solo los pueden realizar los administradores mediante el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-109">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="2c4e6-110">Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Microsoft Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-110">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="2c4e6-111">Suponiendo que no ha realizado ningún cambio en la configuración de conferencia después de instalar Lync Server 2013, debe obtener información que incluya estos valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-111">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="2c4e6-112">Si observa atentamente el resultado anterior, verá dos aspectos de importancia.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-112">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="2c4e6-113">En primer lugar, la propiedad los parámetros clientmediaportrangeenabled se establece en false:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-113">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="2c4e6-114">Esto es importante porque, cuando esta propiedad se establece en false, los clientes de Lync usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="2c4e6-114">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="2c4e6-115">Si desea restringir el uso a un conjunto específico de puertos (y esto es algo que desea hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-115">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="2c4e6-116">Esto se puede hacer con el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-116">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2c4e6-117">El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencia; sin embargo, estas opciones también se pueden aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencia).</span><span class="sxs-lookup"><span data-stu-id="2c4e6-117">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="2c4e6-118">Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específicos, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-118">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2c4e6-119">Como alternativa, puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-119">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2c4e6-120">La segunda importancia que verá es que el resultado del ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-120">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="2c4e6-121">Para poder implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-121">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="2c4e6-122">Por ejemplo, puede configurar los intervalos de puertos como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-122">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c4e6-123">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="2c4e6-123">Client Traffic Type</span></span></th>
<th><span data-ttu-id="2c4e6-124">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="2c4e6-124">Port Start</span></span></th>
<th><span data-ttu-id="2c4e6-125">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="2c4e6-125">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c4e6-126">Audio</span><span class="sxs-lookup"><span data-stu-id="2c4e6-126">Audio</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-127">50020</span><span class="sxs-lookup"><span data-stu-id="2c4e6-127">50020</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-128">20</span><span class="sxs-lookup"><span data-stu-id="2c4e6-128">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c4e6-129">Vídeo</span><span class="sxs-lookup"><span data-stu-id="2c4e6-129">Video</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-130">58000</span><span class="sxs-lookup"><span data-stu-id="2c4e6-130">58000</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-131">20</span><span class="sxs-lookup"><span data-stu-id="2c4e6-131">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c4e6-132">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2c4e6-132">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-133">42000</span><span class="sxs-lookup"><span data-stu-id="2c4e6-133">42000</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-134">20</span><span class="sxs-lookup"><span data-stu-id="2c4e6-134">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c4e6-135">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="2c4e6-135">File transfer</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-136">42020</span><span class="sxs-lookup"><span data-stu-id="2c4e6-136">42020</span></span></p></td>
<td><p><span data-ttu-id="2c4e6-137">20</span><span class="sxs-lookup"><span data-stu-id="2c4e6-137">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2c4e6-138">En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-138">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="2c4e6-139">Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos de 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-139">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="2c4e6-140">Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos usados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-140">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="2c4e6-141">(Por ejemplo, en los equipos cliente podría configurar el uso compartido de aplicaciones para usar, por ejemplo, los puertos de 10000 a 10019). Sin embargo, se recomienda que los intervalos de puertos de cliente sean un subconjunto de los intervalos de puertos del servidor.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-141">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="2c4e6-142">Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se configuraron 20 puertos para el uso compartido de aplicaciones en los clientes.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-142">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="2c4e6-143">Esto también se recomienda, pero no es una regla difícil y rápida.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-143">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="2c4e6-144">En general, puede considerar cada puerto disponible para representar una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de 100 sesiones de comunicación en un determinado momento.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-144">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="2c4e6-145">Como es probable que los servidores participen en muchas más conversaciones que los clientes, tiene sentido abrir muchos más puertos en los servidores que en los clientes.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-145">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="2c4e6-146">La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-146">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="2c4e6-147">Eso debería ser suficiente para la inmensa mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-147">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="2c4e6-148">Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencia, puede usar el siguiente comando del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-148">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="2c4e6-149">O bien, use este comando para asignar estos mismos intervalos de puertos para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-149">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="2c4e6-150">Los usuarios individuales deben cerrar sesión en Lync y, a continuación, volver a iniciar sesión antes de que estos cambios entren en vigor.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-150">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c4e6-151">También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="2c4e6-151">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="2c4e6-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c4e6-152">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

