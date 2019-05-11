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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artículo describe cómo configurar los intervalos de puertos para clientes y la configuración de las directivas de calidad de servicio de Skype para Business Server para los clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 9377274b625af7a4ed93b46a0f6a741e89eee1eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913072"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="3412d-103">Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3412d-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="3412d-104">Este artículo describe cómo configurar los intervalos de puertos para clientes y la configuración de las directivas de calidad de servicio de Skype para Business Server para los clientes que se ejecutan en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3412d-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="3412d-105">Configurar intervalos de puertos</span><span class="sxs-lookup"><span data-stu-id="3412d-105">Configure port ranges</span></span>

<span data-ttu-id="3412d-106">De forma predeterminada, Skype para aplicaciones empresariales de cliente pueden usar cualquier puerto entre puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto es debido a que los intervalos de puertos no se habilitan automáticamente para los clientes.</span><span class="sxs-lookup"><span data-stu-id="3412d-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="3412d-107">Para poder usar la calidad de servicio, sin embargo, debe volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos único.</span><span class="sxs-lookup"><span data-stu-id="3412d-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="3412d-108">Esto puede realizarse mediante el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3412d-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="3412d-109">Los usuarios finales no pueden realizar estos cambios ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="3412d-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="3412d-110">Cambios de puerto sólo pueden realizar los administradores con el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3412d-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="3412d-111">Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde dentro de la Skype de consola de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="3412d-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="3412d-112">Suponiendo que no ha realizado ningún cambio en la configuración de conferencia desde que instaló Skype para Business Server, debería obtener información que incluya estos valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="3412d-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="3412d-113">Si examina atentamente el resultado anterior, verá dos cosas de importancia.</span><span class="sxs-lookup"><span data-stu-id="3412d-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="3412d-114">En primer lugar, la propiedad de los parámetros ClientMediaPortRangeEnabled está establecida en False:</span><span class="sxs-lookup"><span data-stu-id="3412d-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="3412d-115">Que es importante porque, cuando se establece esta propiedad en False, Skype para clientes empresariales va a usar cualquier puerto disponible entre los puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="3412d-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="3412d-116">Si desea restringir el uso a un conjunto de puertos especificado (y esto es algo que desea hacer si tiene previsto en la implementación de calidad de servicio), primero debe habilitar intervalos de puertos de medios de cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="3412d-117">Que se puede realizar mediante el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3412d-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3412d-118">El comando anterior permite intervalos de puertos de medios de cliente para la colección global de opciones de configuración de la conferencia; Sin embargo, estas opciones de configuración también pueden aplicarse en el ámbito de sitio o el ámbito de servicio (sólo para el servidor de conferencia servicio).</span><span class="sxs-lookup"><span data-stu-id="3412d-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="3412d-119">Para habilitar intervalos para un sitio específico o el servidor, de puertos de medios de cliente especificar la identidad de ese sitio o el servidor cuando se llama a Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="3412d-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3412d-120">Como alternativa, puede usar este comando para habilitar intervalos de puertos para todas las opciones de configuración de conferencia:</span><span class="sxs-lookup"><span data-stu-id="3412d-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3412d-121">La segunda cosa de importancia que observará es que los resultados de muestra que, de forma predeterminada, los intervalos de puertos multimedia configurados para cada tipo de tráfico de red son idénticos:</span><span class="sxs-lookup"><span data-stu-id="3412d-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="3412d-122">Para implementar QoS, cada uno de estos intervalos de puertos deberá ser único.</span><span class="sxs-lookup"><span data-stu-id="3412d-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="3412d-123">Por ejemplo, puede configurar los intervalos de puertos como esta:</span><span class="sxs-lookup"><span data-stu-id="3412d-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3412d-124">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="3412d-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="3412d-125">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="3412d-125">Port Start</span></span></th>
<th><span data-ttu-id="3412d-126">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="3412d-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3412d-127">Audio</span><span class="sxs-lookup"><span data-stu-id="3412d-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="3412d-128">50020</span><span class="sxs-lookup"><span data-stu-id="3412d-128">50020</span></span></p></td>
<td><p><span data-ttu-id="3412d-129">20</span><span class="sxs-lookup"><span data-stu-id="3412d-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3412d-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="3412d-130">Video</span></span></p></td>
<td><p><span data-ttu-id="3412d-131">58000</span><span class="sxs-lookup"><span data-stu-id="3412d-131">58000</span></span></p></td>
<td><p><span data-ttu-id="3412d-132">20</span><span class="sxs-lookup"><span data-stu-id="3412d-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3412d-133">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3412d-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3412d-134">42000</span><span class="sxs-lookup"><span data-stu-id="3412d-134">42000</span></span></p></td>
<td><p><span data-ttu-id="3412d-135">20</span><span class="sxs-lookup"><span data-stu-id="3412d-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3412d-136">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="3412d-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="3412d-137">42020</span><span class="sxs-lookup"><span data-stu-id="3412d-137">42020</span></span></p></td>
<td><p><span data-ttu-id="3412d-138">20</span><span class="sxs-lookup"><span data-stu-id="3412d-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3412d-139">En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores.</span><span class="sxs-lookup"><span data-stu-id="3412d-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="3412d-140">Por ejemplo, en los servidores, uso compartido de aplicaciones se ha configurado para utilizar puertos 40803 y 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para utilizar puertos 42000 a través de 42019.</span><span class="sxs-lookup"><span data-stu-id="3412d-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="3412d-141">Esto, demasiado, se realiza principalmente para facilitar la administración de QoS: puertos de cliente no es necesario que representar un subconjunto de los puertos utilizados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3412d-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="3412d-142">(Por ejemplo, en los equipos cliente se puede configurar uso compartido de aplicaciones para que utilice, por ejemplo, puertos 10000 a través de 10019.) Sin embargo, se recomienda que realice su cliente puerto rangos un subconjunto de los intervalos de puertos de servidor.</span><span class="sxs-lookup"><span data-stu-id="3412d-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="3412d-143">Además, es posible que haya observado que los 8348 puertos estaban reservados para uso compartido en los servidores de aplicaciones, pero sólo 20 puertos estaban reservados para uso compartido en los clientes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3412d-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="3412d-144">Esto es demasiado, se recomienda, pero no es una una regla.</span><span class="sxs-lookup"><span data-stu-id="3412d-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="3412d-145">En general, se puede tener en cuenta cada puerto disponible para representar una sesión de comunicación único: si dispone de 100 puertos disponibles en un intervalo de puertos, lo que significa que el equipo en cuestión podría participar en, como máximo, 100 sesiones de comunicación en cualquier momento dado.</span><span class="sxs-lookup"><span data-stu-id="3412d-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="3412d-146">Debido a que los servidores es probable que va a participar en muchas conversaciones más que los clientes, tiene sentido abrir muchas más puertos en servidores que en los clientes.</span><span class="sxs-lookup"><span data-stu-id="3412d-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="3412d-147">20 puertos de anulación de configuración de aplicación de uso compartido en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado y todos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3412d-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="3412d-148">Que debería ser suficiente para la mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3412d-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="3412d-149">Para asignar los intervalos de puertos anteriores a la colección global de la configuración de conferencia, puede usar el siguiente Skype para el comando de Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="3412d-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="3412d-150">O bien, use este comando para asignar estos intervalos de puertos misma para todas las conferencias de los valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="3412d-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="3412d-151">Los usuarios individuales deben cerrar la sesión de Skype para la empresa y, a continuación, vuelva a iniciarla antes de que estos cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="3412d-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="3412d-152">Puede también habilitar intervalos de puertos de medios de cliente y, a continuación, asignar los intervalos de puertos, con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="3412d-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="3412d-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3412d-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="3412d-154">Configurar directivas de calidad de servicio para los clientes que se ejecutan en Windows 10</span><span class="sxs-lookup"><span data-stu-id="3412d-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="3412d-155">Además de especificar intervalos de puertos para su uso por su Skype para clientes empresariales, también debe crear directivas distintas de calidad de servicio que se aplicará a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="3412d-156">(Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente.) Esta información sólo se aplica a los equipos que ejecutan el Skype para clientes empresariales y 10 de Windows.</span><span class="sxs-lookup"><span data-stu-id="3412d-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="3412d-157">En el ejemplo siguiente se usa este conjunto de intervalos de puertos para crear una directiva de audio y una directiva de vídeo:</span><span class="sxs-lookup"><span data-stu-id="3412d-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3412d-158">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="3412d-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="3412d-159">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="3412d-159">Port Start</span></span></th>
<th><span data-ttu-id="3412d-160">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="3412d-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3412d-161">Audio</span><span class="sxs-lookup"><span data-stu-id="3412d-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="3412d-162">50020</span><span class="sxs-lookup"><span data-stu-id="3412d-162">50020</span></span></p></td>
<td><p><span data-ttu-id="3412d-163">20</span><span class="sxs-lookup"><span data-stu-id="3412d-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3412d-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="3412d-164">Video</span></span></p></td>
<td><p><span data-ttu-id="3412d-165">58000</span><span class="sxs-lookup"><span data-stu-id="3412d-165">58000</span></span></p></td>
<td><p><span data-ttu-id="3412d-166">20</span><span class="sxs-lookup"><span data-stu-id="3412d-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3412d-167">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3412d-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3412d-168">42000</span><span class="sxs-lookup"><span data-stu-id="3412d-168">42000</span></span></p></td>
<td><p><span data-ttu-id="3412d-169">20</span><span class="sxs-lookup"><span data-stu-id="3412d-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3412d-170">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="3412d-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="3412d-171">42020</span><span class="sxs-lookup"><span data-stu-id="3412d-171">42020</span></span></p></td>
<td><p><span data-ttu-id="3412d-172">20</span><span class="sxs-lookup"><span data-stu-id="3412d-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3412d-173">Para crear una directiva de audio de calidad de servicio para equipos Windows 10, primero inicie sesión en un equipo donde se ha instalado Administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="3412d-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="3412d-174">Abra Administración de directivas de grupo (haga clic en **Inicio**, elija **Herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="3412d-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="3412d-175">En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="3412d-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="3412d-176">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada a clientes, se debe crear la nueva directiva en la unidad organizativa de cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="3412d-177">Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="3412d-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="3412d-178">En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3412d-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="3412d-179">Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3412d-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="3412d-180">En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva**y, a continuación, haga clic en **Crear nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="3412d-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="3412d-181">En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="3412d-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="3412d-182">Seleccione **Especificar el valor de DSCP** y establezca el valor **46**.</span><span class="sxs-lookup"><span data-stu-id="3412d-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="3412d-183">Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3412d-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="3412d-184">En la página siguiente, asegúrese de que **todas las aplicaciones** está activada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3412d-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="3412d-185">Esta opción indica a la red para buscar todos los paquetes con un marcado DSCP 46, no sólo de paquetes de creados mediante una aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="3412d-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="3412d-186">En la tercera página, asegúrese de que **cualquier dirección IP de origen** y **cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3412d-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="3412d-187">Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) enviado esos paquetes y qué equipo (dirección IP) recibirán los paquetes.</span><span class="sxs-lookup"><span data-stu-id="3412d-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="3412d-188">En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** .</span><span class="sxs-lookup"><span data-stu-id="3412d-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="3412d-189">TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más utilizados por Skype para Business Server y sus aplicaciones de cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="3412d-190">Bajo el encabezado, **Especifique el número de puerto de origen**, seleccione **desde este intervalo o el puerto de origen**.</span><span class="sxs-lookup"><span data-stu-id="3412d-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="3412d-191">En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="3412d-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="3412d-192">Por ejemplo, si ha reservado puertos 50020 a través de los puertos 50039 el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="3412d-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="3412d-193">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3412d-193">Click **Finish**.</span></span>

<span data-ttu-id="3412d-194">Después de haber creado la directiva de QoS para el audio, a continuación, debe crear una segunda directiva para vídeo.</span><span class="sxs-lookup"><span data-stu-id="3412d-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="3412d-195">Para crear una directiva para el vídeo, siga el mismo procedimiento básico seguido al crear la directiva de audio, realizar las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="3412d-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="3412d-196">Use un nombre de directiva diferente (y único).</span><span class="sxs-lookup"><span data-stu-id="3412d-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="3412d-197">Establezca el valor DSCP a **34** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="3412d-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="3412d-198">(Como se indicó anteriormente, no es necesario usar el valor de DSCP 34; simplemente debe asignar un valor DSCP distinto del que se utilizó para el audio).</span><span class="sxs-lookup"><span data-stu-id="3412d-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="3412d-199">Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="3412d-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="3412d-200">Por ejemplo, si lo ha reservado puertos 58000 a través de 58019 para el vídeo, establezca el intervalo de puertos a la siguiente: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="3412d-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="3412d-201">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="3412d-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="3412d-202">Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para compartir aplicaciones de servidor de negocio**).</span><span class="sxs-lookup"><span data-stu-id="3412d-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="3412d-203">Establezca el valor de DSCP en **24** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="3412d-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="3412d-204">(De nuevo, este valor no tiene que ser 24; simplemente debe ser diferente de los valores DSCP usados para audio y vídeo).</span><span class="sxs-lookup"><span data-stu-id="3412d-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="3412d-205">Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="3412d-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="3412d-206">Por ejemplo, si lo ha reservado puertos 42000 a través de 42019 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="3412d-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="3412d-207">Para una directiva de transferencia de archivo:</span><span class="sxs-lookup"><span data-stu-id="3412d-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="3412d-208">Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para las transferencias de archivos de servidor empresarial**).</span><span class="sxs-lookup"><span data-stu-id="3412d-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="3412d-209">Establezca el valor DSCP a **14**.</span><span class="sxs-lookup"><span data-stu-id="3412d-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="3412d-210">(De nuevo, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).</span><span class="sxs-lookup"><span data-stu-id="3412d-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="3412d-211">Utilice el intervalo de puerto configurado anteriormente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3412d-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="3412d-212">Por ejemplo, si lo ha reservado puertos 42020 a través de 42039 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="3412d-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="3412d-213">Las nuevas directivas que ha creado no tendrán efecto hasta que se ha actualizado la directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="3412d-214">Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="3412d-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="3412d-215">Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador.</span><span class="sxs-lookup"><span data-stu-id="3412d-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="3412d-216">Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3412d-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="3412d-217">Tenga en cuenta que deben ser destinadas estas directivas a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3412d-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="3412d-218">No debe aplicarse a los servidores que ejecutan Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3412d-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="3412d-219">Para ayudar a garantizar que los paquetes de red están marcados con el valor DSCP adecuado, también debe crear una nueva entrada del registro en cada equipo completando el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="3412d-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="3412d-220">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="3412d-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="3412d-221">En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3412d-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="3412d-222">En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="3412d-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3412d-223">Secundario **Tcpip**, elija **nuevo**y, a continuación, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="3412d-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="3412d-224">Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="3412d-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3412d-225">Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**.</span><span class="sxs-lookup"><span data-stu-id="3412d-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="3412d-226">Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="3412d-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3412d-227">Haga doble clic en **no usa NLA**.</span><span class="sxs-lookup"><span data-stu-id="3412d-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="3412d-228">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3412d-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="3412d-229">Cierre el Editor del registro y eboot su equipo.</span><span class="sxs-lookup"><span data-stu-id="3412d-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="3412d-230">Configuración de calidad de servicio en equipos con varios adaptadores de red</span><span class="sxs-lookup"><span data-stu-id="3412d-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="3412d-231">Si tiene un equipo que tenga varios adaptadores de red, es posible que ejecute cada cierto tiempo problemas donde se muestran los valores de DSCP como 0 x 00 en lugar de con el valor configurado.</span><span class="sxs-lookup"><span data-stu-id="3412d-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="3412d-232">Normalmente, esto se producirá en los equipos donde uno o varios de los adaptadores de red no son capaz de obtener acceso a su dominio de Active Directory (por ejemplo, si se utilizan estos adaptadores para una red privada).</span><span class="sxs-lookup"><span data-stu-id="3412d-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="3412d-233">En casos como, valores de DSCP se etiquetarán para los adaptadores que pueden tener acceso al dominio, pero no se etiquetará para los adaptadores que no se pueden tener acceso al dominio.</span><span class="sxs-lookup"><span data-stu-id="3412d-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="3412d-234">Si desea que los valores DSCP de etiqueta para todos los adaptadores de red en un equipo, incluidos los adaptadores que no tienen acceso a su dominio, debe agregar y configurar un valor en el registro.</span><span class="sxs-lookup"><span data-stu-id="3412d-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="3412d-235">Es posible que al completar el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="3412d-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="3412d-236">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="3412d-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="3412d-237">En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3412d-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="3412d-238">En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="3412d-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3412d-239">Si no ve una clave del registro con la etiqueta **QoS** , a continuación, haga clic en **TCP/IP**, elija **nuevo**y, a continuación, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="3412d-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="3412d-240">Una vez creada la nueva clave, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="3412d-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3412d-241">Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**.</span><span class="sxs-lookup"><span data-stu-id="3412d-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="3412d-242">Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="3412d-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3412d-243">Haga doble clic en **no usa NLA**.</span><span class="sxs-lookup"><span data-stu-id="3412d-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="3412d-244">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3412d-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="3412d-245">Después de crear y configurar el nuevo valor del registro, debe reiniciar el equipo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="3412d-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="3412d-246">Vea también</span><span class="sxs-lookup"><span data-stu-id="3412d-246">See also</span></span>

[<span data-ttu-id="3412d-247">Crear un objeto de directiva de grupo en Windows 10</span><span class="sxs-lookup"><span data-stu-id="3412d-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
