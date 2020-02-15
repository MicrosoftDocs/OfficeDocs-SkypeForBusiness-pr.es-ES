---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar los intervalos de puertos para los clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045893"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="ba43b-103">Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ba43b-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="ba43b-104">En este artículo se describe cómo configurar los intervalos de puertos para los clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba43b-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="ba43b-105">Configuración de intervalos de puertos</span><span class="sxs-lookup"><span data-stu-id="ba43b-105">Configure port ranges</span></span>

<span data-ttu-id="ba43b-106">De forma predeterminada, las aplicaciones cliente de Skype empresarial pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes.</span><span class="sxs-lookup"><span data-stu-id="ba43b-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="ba43b-107">Sin embargo, para poder usar la calidad de servicio, tendrá que volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos.</span><span class="sxs-lookup"><span data-stu-id="ba43b-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="ba43b-108">Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ba43b-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="ba43b-109">Los usuarios finales no pueden realizar estos cambios por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="ba43b-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="ba43b-110">Los cambios de Puerto solo los pueden realizar los administradores mediante el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ba43b-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="ba43b-111">Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="ba43b-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="ba43b-112">Suponiendo que no ha realizado ningún cambio en la configuración de conferencia desde que instaló Skype empresarial Server, debe obtener información que incluya estos valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="ba43b-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="ba43b-113">Si observa atentamente el resultado anterior, verá dos aspectos de importancia.</span><span class="sxs-lookup"><span data-stu-id="ba43b-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="ba43b-114">En primer lugar, la propiedad los parámetros clientmediaportrangeenabled se establece en false:</span><span class="sxs-lookup"><span data-stu-id="ba43b-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="ba43b-115">Esto es importante porque, cuando esta propiedad se establece en false, los clientes de Skype empresarial usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="ba43b-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="ba43b-116">Si desea restringir el uso a un conjunto específico de puertos (y esto es algo que desea hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente.</span><span class="sxs-lookup"><span data-stu-id="ba43b-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="ba43b-117">Esto se puede hacer con el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ba43b-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="ba43b-118">El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencia; sin embargo, estas opciones también se pueden aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencia).</span><span class="sxs-lookup"><span data-stu-id="ba43b-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="ba43b-119">Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específicos, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="ba43b-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="ba43b-120">Como alternativa, puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="ba43b-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="ba43b-121">La segunda importancia que verá es que el resultado del ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:</span><span class="sxs-lookup"><span data-stu-id="ba43b-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="ba43b-122">Para poder implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único.</span><span class="sxs-lookup"><span data-stu-id="ba43b-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="ba43b-123">Por ejemplo, puede configurar los intervalos de puertos como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="ba43b-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba43b-124">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="ba43b-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="ba43b-125">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="ba43b-125">Port Start</span></span></th>
<th><span data-ttu-id="ba43b-126">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="ba43b-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba43b-127">Audio</span><span class="sxs-lookup"><span data-stu-id="ba43b-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="ba43b-128">50020</span><span class="sxs-lookup"><span data-stu-id="ba43b-128">50020</span></span></p></td>
<td><p><span data-ttu-id="ba43b-129">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba43b-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="ba43b-130">Video</span></span></p></td>
<td><p><span data-ttu-id="ba43b-131">58000</span><span class="sxs-lookup"><span data-stu-id="ba43b-131">58000</span></span></p></td>
<td><p><span data-ttu-id="ba43b-132">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba43b-133">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ba43b-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="ba43b-134">42000</span><span class="sxs-lookup"><span data-stu-id="ba43b-134">42000</span></span></p></td>
<td><p><span data-ttu-id="ba43b-135">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba43b-136">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="ba43b-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="ba43b-137">42020</span><span class="sxs-lookup"><span data-stu-id="ba43b-137">42020</span></span></p></td>
<td><p><span data-ttu-id="ba43b-138">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba43b-139">En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores.</span><span class="sxs-lookup"><span data-stu-id="ba43b-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="ba43b-140">Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos de 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="ba43b-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="ba43b-141">Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos usados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ba43b-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="ba43b-142">(Por ejemplo, en los equipos cliente podría configurar el uso compartido de aplicaciones para usar, por ejemplo, los puertos de 10000 a 10019). Sin embargo, se recomienda que los intervalos de puertos de cliente sean un subconjunto de los intervalos de puertos del servidor.</span><span class="sxs-lookup"><span data-stu-id="ba43b-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="ba43b-143">Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se configuraron 20 puertos para el uso compartido de aplicaciones en los clientes.</span><span class="sxs-lookup"><span data-stu-id="ba43b-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="ba43b-144">También se recomienda esto, pero no es una regla difícil y rápida.</span><span class="sxs-lookup"><span data-stu-id="ba43b-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="ba43b-145">En general, puede considerar cada puerto disponible para representar una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de 100 sesiones de comunicación en un determinado momento.</span><span class="sxs-lookup"><span data-stu-id="ba43b-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="ba43b-146">Como es probable que los servidores participen en muchas más conversaciones que los clientes, tiene sentido abrir muchos más puertos en los servidores que en los clientes.</span><span class="sxs-lookup"><span data-stu-id="ba43b-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="ba43b-147">La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba43b-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="ba43b-148">Eso debería ser suficiente para la inmensa mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ba43b-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="ba43b-149">Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencia, puede usar el siguiente comando del shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="ba43b-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="ba43b-150">O bien, use este comando para asignar estos mismos intervalos de puertos para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="ba43b-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="ba43b-151">Los usuarios individuales deben cerrar sesión en Skype empresarial y, a continuación, volver a iniciar sesión antes de que estos cambios entren en vigor.</span><span class="sxs-lookup"><span data-stu-id="ba43b-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="ba43b-152">También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="ba43b-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="ba43b-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba43b-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="ba43b-154">Configurar directivas de calidad de servicio para clientes que se ejecutan en Windows 10</span><span class="sxs-lookup"><span data-stu-id="ba43b-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="ba43b-155">Además de especificar intervalos de puertos para su uso por parte de los clientes de Skype empresarial, también debe crear directivas de calidad de servicio independientes que se aplicarán a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="ba43b-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="ba43b-156">(Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Skype empresarial y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ba43b-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="ba43b-157">En el ejemplo siguiente utiliza este conjunto de intervalos de puertos para crear una directiva de audio y una directiva de vídeo:</span><span class="sxs-lookup"><span data-stu-id="ba43b-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba43b-158">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="ba43b-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="ba43b-159">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="ba43b-159">Port Start</span></span></th>
<th><span data-ttu-id="ba43b-160">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="ba43b-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba43b-161">Audio</span><span class="sxs-lookup"><span data-stu-id="ba43b-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="ba43b-162">50020</span><span class="sxs-lookup"><span data-stu-id="ba43b-162">50020</span></span></p></td>
<td><p><span data-ttu-id="ba43b-163">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba43b-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="ba43b-164">Video</span></span></p></td>
<td><p><span data-ttu-id="ba43b-165">58000</span><span class="sxs-lookup"><span data-stu-id="ba43b-165">58000</span></span></p></td>
<td><p><span data-ttu-id="ba43b-166">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba43b-167">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ba43b-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="ba43b-168">42000</span><span class="sxs-lookup"><span data-stu-id="ba43b-168">42000</span></span></p></td>
<td><p><span data-ttu-id="ba43b-169">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba43b-170">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="ba43b-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="ba43b-171">42020</span><span class="sxs-lookup"><span data-stu-id="ba43b-171">42020</span></span></p></td>
<td><p><span data-ttu-id="ba43b-172">20</span><span class="sxs-lookup"><span data-stu-id="ba43b-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba43b-173">Para crear una directiva de audio de calidad de servicio para equipos con Windows 10, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="ba43b-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="ba43b-174">Abra administración de directivas de grupo (haga clic en **Inicio**, elija **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ba43b-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="ba43b-175">En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="ba43b-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="ba43b-176">Por ejemplo, si todos los equipos cliente están ubicados en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.</span><span class="sxs-lookup"><span data-stu-id="ba43b-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="ba43b-177">Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="ba43b-178">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="ba43b-179">Haga clic con el botón secundario en la Directiva recién creada y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="ba43b-180">En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en Directiva**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="ba43b-181">En el cuadro de diálogo **QoS basada en directivas** , en la página de inicio, escriba un nombre para la nueva Directiva en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="ba43b-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="ba43b-182">Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="ba43b-183">Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="ba43b-184">En la página siguiente, seleccione **solo aplicaciones con este nombre de archivo ejecutable**, escriba **Lync. exe** como nombre y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="ba43b-185">Esta configuración le indica a la Directiva que solo Asigne prioridades de tráfico de coincidencia desde el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba43b-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="ba43b-186">En la tercera página, asegúrese de que **todas las** direcciones IP de origen y de **destino** estén seleccionadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="ba43b-187">Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.</span><span class="sxs-lookup"><span data-stu-id="ba43b-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="ba43b-188">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="ba43b-189">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Skype empresarial Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="ba43b-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="ba43b-p117">En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto asociado, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos de 50020 a 50039 para el tráfico de audio, escriba el intervalo de puertos con el formato: **50020:50039**. Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="ba43b-p118">Después de crear la directiva de QoS para audio, deberá crear una segunda directiva para el vídeo. Para ello, siga el mismo procedimiento básico que ha seguido para la directiva de audio, con las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="ba43b-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="ba43b-196">Use un nombre de directiva diferente (y único).</span><span class="sxs-lookup"><span data-stu-id="ba43b-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="ba43b-p119">Ajuste el valor de DSCP en **34**, en lugar de 46. (Como ya se ha mencionado, no tiene que utilizar el valor 34 para DSCP, sino asignar a DSCP un valor diferente al usado para el audio.)</span><span class="sxs-lookup"><span data-stu-id="ba43b-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="ba43b-199">Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ba43b-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ba43b-200">Por ejemplo, si ha reservado los puertos de 58000 a 58019 para el vídeo, establezca el intervalo de puertos en este: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="ba43b-201">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="ba43b-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="ba43b-202">Use un nombre de directiva diferente (y único) (por ejemplo, **uso compartido de aplicaciones de Skype empresarial Server**).</span><span class="sxs-lookup"><span data-stu-id="ba43b-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="ba43b-p121">Ajuste el valor de DSCP en **24**, en lugar de 46. (También en este caso, este valor no tiene por qué ser 24, sino que debe ser diferente a los valores de DSCP utilizados para el audio y el vídeo.)</span><span class="sxs-lookup"><span data-stu-id="ba43b-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="ba43b-205">Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ba43b-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ba43b-206">Por ejemplo, si ha reservado los puertos de 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="ba43b-207">Para una directiva de transferencia de archivos:</span><span class="sxs-lookup"><span data-stu-id="ba43b-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="ba43b-208">Use un nombre de directiva diferente (y único) (por ejemplo, **transferencias de archivos de Skype empresarial Server**).</span><span class="sxs-lookup"><span data-stu-id="ba43b-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="ba43b-209">Ajuste el valor de DSCP en **14**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="ba43b-210">(Una vez más, este valor no tiene por qué ser 14, sino simplemente un código DSCP único.)</span><span class="sxs-lookup"><span data-stu-id="ba43b-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="ba43b-211">Usar el intervalo de puertos configurado anteriormente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba43b-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="ba43b-212">Por ejemplo, si ha reservado los puertos de 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="ba43b-p125">Las directivas nuevas que ha creado no tendrán efecto hasta que se actualice Directiva de grupos en los equipos cliente. Aunque la Directiva de grupos se actualiza periódicamente de forma automática, puede forzar una actualización inmediata ejecutando el siguiente comando en todos los equipos en los que es necesario actualizar la Directiva de grupos:</span><span class="sxs-lookup"><span data-stu-id="ba43b-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="ba43b-p126">Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comando con las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="ba43b-217">Recuerde que estas directivas deben ir dirigidas a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="ba43b-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="ba43b-218">No se deben aplicar a los servidores que ejecutan Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ba43b-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="ba43b-219">Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ba43b-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="ba43b-220">Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ba43b-221">En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="ba43b-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ba43b-222">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="ba43b-223">Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="ba43b-224">Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="ba43b-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="ba43b-225">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="ba43b-226">Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="ba43b-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ba43b-227">Haga doble clic en **No usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="ba43b-228">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **información del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ba43b-229">Cierre el editor del registro y eboot el equipo.</span><span class="sxs-lookup"><span data-stu-id="ba43b-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="ba43b-230">Configurar la calidad de servicio en equipos con varios adaptadores de red</span><span class="sxs-lookup"><span data-stu-id="ba43b-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="ba43b-231">Si tiene un equipo con varios adaptadores de red, en ocasiones puede que se ejecute en problemas en los que los valores DSCP se muestran como 0x00 en lugar del valor configurado.</span><span class="sxs-lookup"><span data-stu-id="ba43b-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="ba43b-232">Esto ocurrirá, generalmente, en equipos en los que uno o más adaptadores de red no pueden acceder al dominio de Active Directory (por ejemplo, si estos adaptadores de red se utilizan para una red privada).</span><span class="sxs-lookup"><span data-stu-id="ba43b-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="ba43b-233">En esos casos, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.</span><span class="sxs-lookup"><span data-stu-id="ba43b-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="ba43b-234">Si desea etiquetar los valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor para el registro.</span><span class="sxs-lookup"><span data-stu-id="ba43b-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="ba43b-235">Se puede hacer siguiendo este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ba43b-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="ba43b-236">Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ba43b-237">En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="ba43b-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ba43b-238">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="ba43b-239">Si no ve una clave de registro con la etiqueta **QoS**, haga clic con el botón secundario en **Tcpip**, seleccione **Nuevo** y, a continuación, haga clic en **Clave**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="ba43b-240">Una vez creada la clave nueva, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="ba43b-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="ba43b-241">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="ba43b-242">Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="ba43b-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ba43b-243">Haga doble clic en **No usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="ba43b-244">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **información del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba43b-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="ba43b-245">Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="ba43b-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba43b-246">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba43b-246">See also</span></span>

[<span data-ttu-id="ba43b-247">Crear un objeto de directiva de grupo en Windows 10</span><span class="sxs-lookup"><span data-stu-id="ba43b-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
