---
title: Configurar intervalos de puertos y una directiva de calidad de servicio para los clientes
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
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos para sus clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.
ms.openlocfilehash: ce1690c295f1f5ed991780919370e5dbf5b5d6b1
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35204017"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="b6736-103">Configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b6736-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="b6736-104">En este artículo se describe cómo configurar intervalos de puertos para sus clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b6736-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="b6736-105">Configurar intervalos de puertos</span><span class="sxs-lookup"><span data-stu-id="b6736-105">Configure port ranges</span></span>

<span data-ttu-id="b6736-106">De forma predeterminada, las aplicaciones cliente de Skype empresarial pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes.</span><span class="sxs-lookup"><span data-stu-id="b6736-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="b6736-107">Sin embargo, para usar la calidad de servicio, tendrá que reasignar los diversos tipos de tráfico (audio, vídeo, multimedia, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos.</span><span class="sxs-lookup"><span data-stu-id="b6736-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="b6736-108">Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6736-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="b6736-109">Los usuarios finales no pueden realizar estos cambios por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="b6736-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="b6736-110">Los administradores solo pueden hacer cambios en el puerto mediante el cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6736-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="b6736-111">Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="b6736-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="b6736-112">Suponiendo que no ha realizado ningún cambio en la configuración de conferencia después de instalar Skype empresarial Server, debe obtener información que incluya estos valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="b6736-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="b6736-113">Si examina detenidamente la salida anterior, verá dos cuestiones de importancia.</span><span class="sxs-lookup"><span data-stu-id="b6736-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="b6736-114">En primer lugar, la propiedad ClientMediaPortRangeEnabled se establece en false:</span><span class="sxs-lookup"><span data-stu-id="b6736-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="b6736-115">Eso es importante porque, cuando esta propiedad se establece en false, los clientes de Skype empresarial usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puertos (por ejemplo, ClientMediaPort o ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="b6736-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="b6736-116">Si desea restringir el uso a un conjunto de puertos especificado (y esto es algo que quiera hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="b6736-117">Esto se puede realizar con el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b6736-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b6736-118">El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencias; sin embargo, esta configuración también se puede aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencias).</span><span class="sxs-lookup"><span data-stu-id="b6736-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="b6736-119">Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específico, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="b6736-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b6736-120">También puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="b6736-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b6736-121">La segunda importancia que observará es que la salida de ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:</span><span class="sxs-lookup"><span data-stu-id="b6736-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="b6736-122">Para implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único.</span><span class="sxs-lookup"><span data-stu-id="b6736-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="b6736-123">Por ejemplo, puede configurar los intervalos de puertos como este:</span><span class="sxs-lookup"><span data-stu-id="b6736-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6736-124">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="b6736-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="b6736-125">Inicio de Puerto</span><span class="sxs-lookup"><span data-stu-id="b6736-125">Port Start</span></span></th>
<th><span data-ttu-id="b6736-126">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="b6736-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6736-127">Audio</span><span class="sxs-lookup"><span data-stu-id="b6736-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="b6736-128">50020</span><span class="sxs-lookup"><span data-stu-id="b6736-128">50020</span></span></p></td>
<td><p><span data-ttu-id="b6736-129">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6736-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="b6736-130">Video</span></span></p></td>
<td><p><span data-ttu-id="b6736-131">58000</span><span class="sxs-lookup"><span data-stu-id="b6736-131">58000</span></span></p></td>
<td><p><span data-ttu-id="b6736-132">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6736-133">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b6736-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="b6736-134">42000</span><span class="sxs-lookup"><span data-stu-id="b6736-134">42000</span></span></p></td>
<td><p><span data-ttu-id="b6736-135">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6736-136">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="b6736-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="b6736-137">42020</span><span class="sxs-lookup"><span data-stu-id="b6736-137">42020</span></span></p></td>
<td><p><span data-ttu-id="b6736-138">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b6736-139">En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores.</span><span class="sxs-lookup"><span data-stu-id="b6736-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="b6736-140">Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="b6736-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="b6736-141">Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos que se usan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b6736-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="b6736-142">(Por ejemplo, en los equipos cliente, puede configurar el uso compartido de aplicaciones para que lo use, por ejemplo, los puertos 10000 a 10019). Sin embargo, le recomendamos que los intervalos de puertos de cliente sean un subconjunto de intervalos de puertos de servidor.</span><span class="sxs-lookup"><span data-stu-id="b6736-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="b6736-143">Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se reservaron 20 puertos para el uso compartido de aplicaciones en los clientes.</span><span class="sxs-lookup"><span data-stu-id="b6736-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="b6736-144">Esto también se recomienda, pero no es una regla de hardware y rápido.</span><span class="sxs-lookup"><span data-stu-id="b6736-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="b6736-145">En general, puede considerar que cada puerto disponible representa una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de las sesiones de comunicación de 100 en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b6736-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="b6736-146">Dado que es probable que los servidores adquieran parte de muchas más conversaciones que clientes, tiene sentido abrir muchos más puertos en servidores que en los clientes.</span><span class="sxs-lookup"><span data-stu-id="b6736-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="b6736-147">La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b6736-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="b6736-148">Eso debería ser suficiente para la gran mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b6736-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="b6736-149">Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencias, puede usar el siguiente comando de Shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="b6736-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="b6736-150">O bien, use este comando para asignar estos mismos intervalos de puerto para todas las opciones de configuración de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="b6736-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="b6736-151">Los usuarios individuales deben cerrar sesión en Skype empresarial y, a continuación, iniciar sesión de nuevo antes de que estos cambios se hagan efectivos.</span><span class="sxs-lookup"><span data-stu-id="b6736-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="b6736-152">También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="b6736-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="b6736-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6736-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="b6736-154">Configurar directivas de calidad de servicio para clientes que ejecutan Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6736-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="b6736-155">Además de especificar los intervalos de puertos para que los usen sus clientes de Skype empresarial, también debe crear directivas de calidad de servicio por separado que se aplicarán a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="b6736-156">(Las directivas de calidad de servicio creadas para servidores de conferencia, aplicaciones y mediación no se deben aplicar a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Skype empresarial y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b6736-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="b6736-157">En el ejemplo siguiente se usa este conjunto de intervalos de puerto para crear una directiva de audio y una directiva de vídeo:</span><span class="sxs-lookup"><span data-stu-id="b6736-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6736-158">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="b6736-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="b6736-159">Inicio de Puerto</span><span class="sxs-lookup"><span data-stu-id="b6736-159">Port Start</span></span></th>
<th><span data-ttu-id="b6736-160">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="b6736-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6736-161">Audio</span><span class="sxs-lookup"><span data-stu-id="b6736-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="b6736-162">50020</span><span class="sxs-lookup"><span data-stu-id="b6736-162">50020</span></span></p></td>
<td><p><span data-ttu-id="b6736-163">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6736-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="b6736-164">Video</span></span></p></td>
<td><p><span data-ttu-id="b6736-165">58000</span><span class="sxs-lookup"><span data-stu-id="b6736-165">58000</span></span></p></td>
<td><p><span data-ttu-id="b6736-166">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6736-167">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b6736-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="b6736-168">42000</span><span class="sxs-lookup"><span data-stu-id="b6736-168">42000</span></span></p></td>
<td><p><span data-ttu-id="b6736-169">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6736-170">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="b6736-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="b6736-171">42020</span><span class="sxs-lookup"><span data-stu-id="b6736-171">42020</span></span></p></td>
<td><p><span data-ttu-id="b6736-172">veinte</span><span class="sxs-lookup"><span data-stu-id="b6736-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b6736-173">Para crear una directiva de audio de calidad de servicio para equipos con Windows 10, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="b6736-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="b6736-174">Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b6736-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="b6736-175">En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="b6736-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="b6736-176">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="b6736-177">Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.</span><span class="sxs-lookup"><span data-stu-id="b6736-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="b6736-178">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6736-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="b6736-179">Haga clic con el botón secundario en la Directiva recién creada y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b6736-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="b6736-180">En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="b6736-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="b6736-181">En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="b6736-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="b6736-182">Seleccione **especificar valor de DSCP** y establezca el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="b6736-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="b6736-183">Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b6736-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="b6736-184">En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable**, escriba **Lync. exe** como nombre y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b6736-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="b6736-185">Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="b6736-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="b6736-186">En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b6736-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="b6736-187">Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.</span><span class="sxs-lookup"><span data-stu-id="b6736-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="b6736-188">En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** .</span><span class="sxs-lookup"><span data-stu-id="b6736-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="b6736-189">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Skype empresarial Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="b6736-190">En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**.</span><span class="sxs-lookup"><span data-stu-id="b6736-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="b6736-191">En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio.</span><span class="sxs-lookup"><span data-stu-id="b6736-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="b6736-192">Por ejemplo, si ha reservado los puertos 50020 a través de los puertos 50039 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="b6736-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="b6736-193">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b6736-193">Click **Finish**.</span></span>

<span data-ttu-id="b6736-194">Después de crear la directiva QoS para el audio, debe crear una segunda Directiva para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="b6736-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="b6736-195">Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:</span><span class="sxs-lookup"><span data-stu-id="b6736-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="b6736-196">Use un nombre de directiva diferente (y único).</span><span class="sxs-lookup"><span data-stu-id="b6736-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="b6736-197">Establezca el valor de DSCP en **34** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="b6736-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="b6736-198">(Como se ha indicado anteriormente, no tiene que usar el valor de DSCP 34; simplemente debe asignar un valor de DSCP diferente al utilizado para el audio).</span><span class="sxs-lookup"><span data-stu-id="b6736-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="b6736-199">Use el intervalo de puertos configurado previamente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b6736-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="b6736-200">Por ejemplo, si ha reservado los puertos 58000 a 58019 para el vídeo, establezca el intervalo de puertos en: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="b6736-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="b6736-201">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice estas sustituciones:</span><span class="sxs-lookup"><span data-stu-id="b6736-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="b6736-202">Use un nombre de directiva diferente (y único) (por ejemplo, **uso compartido de aplicaciones de Skype empresarial Server**).</span><span class="sxs-lookup"><span data-stu-id="b6736-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="b6736-203">Establezca el valor de DSCP en **24** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="b6736-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="b6736-204">(Nuevamente, este valor no tiene que ser 24; simplemente debe ser diferente de los valores de DSCP usados para el audio y el vídeo).</span><span class="sxs-lookup"><span data-stu-id="b6736-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="b6736-205">Use el intervalo de puertos configurado previamente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b6736-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="b6736-206">Por ejemplo, si ha reservado los puertos 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="b6736-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="b6736-207">Para una directiva de transferencia de archivos:</span><span class="sxs-lookup"><span data-stu-id="b6736-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="b6736-208">Use un nombre de directiva diferente (y único) (por ejemplo, transferencias de **archivos de Skype empresarial Server**).</span><span class="sxs-lookup"><span data-stu-id="b6736-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="b6736-209">Establezca el valor de DSCP en **14**.</span><span class="sxs-lookup"><span data-stu-id="b6736-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="b6736-210">(Nuevamente, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).</span><span class="sxs-lookup"><span data-stu-id="b6736-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="b6736-211">Use el intervalo de puertos configurado previamente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6736-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="b6736-212">Por ejemplo, si ha reservado los puertos 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="b6736-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="b6736-213">Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="b6736-214">Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="b6736-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="b6736-215">Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador.</span><span class="sxs-lookup"><span data-stu-id="b6736-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="b6736-216">Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b6736-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="b6736-217">Tenga en cuenta que estas directivas deben ir dirigidas a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="b6736-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="b6736-218">No se deben aplicar a servidores que ejecuten Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b6736-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="b6736-219">Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6736-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="b6736-220">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b6736-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="b6736-221">En el cuadro de diálogo **Ejecutar** , \*\*\*\* escriba regedit y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b6736-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="b6736-222">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="b6736-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="b6736-223">Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="b6736-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="b6736-224">Después de crear la nueva clave del registro, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="b6736-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="b6736-225">Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="b6736-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="b6736-226">Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="b6736-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="b6736-227">Haga doble clic en **no usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="b6736-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="b6736-228">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6736-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="b6736-229">Cierre el editor del registro y eboot su equipo.</span><span class="sxs-lookup"><span data-stu-id="b6736-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="b6736-230">Configurar la calidad de servicio en equipos con varios adaptadores de red</span><span class="sxs-lookup"><span data-stu-id="b6736-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="b6736-231">Si tiene un equipo con varios adaptadores de red, es posible que ocasionalmente se encuentre con problemas en los que los valores de DSCP se muestran como 0x00 en lugar de con el valor configurado.</span><span class="sxs-lookup"><span data-stu-id="b6736-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="b6736-232">Esto suele ocurrir en equipos en los que uno o varios de los adaptadores de red no pueden obtener acceso al dominio de Active Directory (por ejemplo, si se usan para una red privada).</span><span class="sxs-lookup"><span data-stu-id="b6736-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="b6736-233">En casos como ese, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.</span><span class="sxs-lookup"><span data-stu-id="b6736-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="b6736-234">Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro.</span><span class="sxs-lookup"><span data-stu-id="b6736-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="b6736-235">Esto se puede realizar mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b6736-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="b6736-236">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b6736-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="b6736-237">En el cuadro de diálogo **Ejecutar** , \*\*\*\* escriba regedit y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b6736-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="b6736-238">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="b6736-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="b6736-239">Si no ve una clave del registro denominada **QoS** , haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, después, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="b6736-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="b6736-240">Después de crear la nueva clave, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="b6736-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="b6736-241">Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="b6736-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="b6736-242">Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="b6736-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="b6736-243">Haga doble clic en **no usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="b6736-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="b6736-244">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6736-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="b6736-245">Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b6736-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6736-246">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6736-246">See also</span></span>

[<span data-ttu-id="b6736-247">Crear un objeto de directiva de grupo en Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6736-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
