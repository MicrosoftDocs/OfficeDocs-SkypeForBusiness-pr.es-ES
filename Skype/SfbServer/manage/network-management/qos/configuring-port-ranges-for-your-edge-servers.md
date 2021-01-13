---
title: Configuración de intervalos de puertos y calidad de servicio para los servidores perimetrales
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos para servidores perimetrales y cómo configurar una directiva de calidad de servicio para los servidores perimetrales A/V.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832910"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="92a16-103">Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="92a16-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="92a16-104">En este artículo se describe cómo configurar intervalos de puertos para servidores perimetrales y cómo configurar una directiva de calidad de servicio para los servidores perimetrales A/V.</span><span class="sxs-lookup"><span data-stu-id="92a16-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="92a16-105">Configurar intervalos de puertos</span><span class="sxs-lookup"><span data-stu-id="92a16-105">Configure port ranges</span></span>

<span data-ttu-id="92a16-106">Con los servidores perimetrales, no es necesario configurar intervalos de puertos independientes para el uso compartido de audio, vídeo y aplicaciones; Del mismo modo, los intervalos de puertos usados para los servidores perimetrales no tienen que coincidir con los intervalos de puertos usados con los servidores de conferencia, aplicación y mediación.</span><span class="sxs-lookup"><span data-stu-id="92a16-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="92a16-107">Antes de continuar con nuestro ejemplo, es importante destacar que, aunque esta opción existe, le recomendamos que no cambie los intervalos de puertos, ya que esto puede afectar negativamente a algunos escenarios si sale del intervalo de puertos 50000.</span><span class="sxs-lookup"><span data-stu-id="92a16-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="92a16-108">Por ejemplo, supongamos que ha configurado los servidores de conferencia, aplicación y mediación para usar estos intervalos de puertos:</span><span class="sxs-lookup"><span data-stu-id="92a16-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92a16-109">Tipo de paquete</span><span class="sxs-lookup"><span data-stu-id="92a16-109">Packet Type</span></span></th>
<th><span data-ttu-id="92a16-110">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="92a16-110">Starting Port</span></span></th>
<th><span data-ttu-id="92a16-111">Número de puertos reservados</span><span class="sxs-lookup"><span data-stu-id="92a16-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92a16-112">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="92a16-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="92a16-113">40803</span><span class="sxs-lookup"><span data-stu-id="92a16-113">40803</span></span></p></td>
<td><p><span data-ttu-id="92a16-114">8348</span><span class="sxs-lookup"><span data-stu-id="92a16-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a16-115">Audio</span><span class="sxs-lookup"><span data-stu-id="92a16-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="92a16-116">49152</span><span class="sxs-lookup"><span data-stu-id="92a16-116">49152</span></span></p></td>
<td><p><span data-ttu-id="92a16-117">8348</span><span class="sxs-lookup"><span data-stu-id="92a16-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a16-118">Vídeo</span><span class="sxs-lookup"><span data-stu-id="92a16-118">Video</span></span></p></td>
<td><p><span data-ttu-id="92a16-119">57500</span><span class="sxs-lookup"><span data-stu-id="92a16-119">57500</span></span></p></td>
<td><p><span data-ttu-id="92a16-120">8034</span><span class="sxs-lookup"><span data-stu-id="92a16-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a16-121"><strong>Totales</strong></span><span class="sxs-lookup"><span data-stu-id="92a16-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="92a16-122">24730</span><span class="sxs-lookup"><span data-stu-id="92a16-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92a16-123">Como puede ver, los intervalos de puertos para el uso compartido de audio, vídeo y aplicaciones comienzan en el puerto 40803 y abarcan un total de 24732 puertos.</span><span class="sxs-lookup"><span data-stu-id="92a16-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="92a16-124">Si lo prefiere, puede configurar un servidor perimetral determinado para usar estos valores de puerto generales ejecutando un comando similar a este desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="92a16-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="92a16-125">También puede usar el comando siguiente para configurar simultáneamente todos los servidores perimetrales de su organización:</span><span class="sxs-lookup"><span data-stu-id="92a16-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="92a16-126">Puede comprobar la configuración de puerto actual para los servidores perimetrales mediante este comando del Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="92a16-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="92a16-127">De nuevo, aunque proporcionamos estas opciones, te recomendamos encarecidamente que dejes las cosas como están para la configuración del puerto.</span><span class="sxs-lookup"><span data-stu-id="92a16-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="92a16-128">Configurar una directiva de QoS para los servidores perimetrales A/V</span><span class="sxs-lookup"><span data-stu-id="92a16-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="92a16-129">Además de crear directivas de QoS para los servidores de conferencia, aplicación y mediación, también debe crear directivas de audio y vídeo para el lado interno de los servidores perimetrales A/V.</span><span class="sxs-lookup"><span data-stu-id="92a16-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="92a16-130">Sin embargo, las directivas usadas en los servidores perimetrales son diferentes de las directivas usadas en los servidores de conferencia, aplicación y mediación.</span><span class="sxs-lookup"><span data-stu-id="92a16-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="92a16-131">Para los servidores de conferencia, aplicación y mediación, ha especificado un intervalo de puertos de origen; con los servidores perimetrales, debe especificar un intervalo de puertos de destino.</span><span class="sxs-lookup"><span data-stu-id="92a16-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="92a16-132">Por este problema, no puede simplemente aplicar las directivas qoS del servidor de conferencia, aplicación y mediación a los servidores perimetrales: estas directivas simplemente no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="92a16-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="92a16-133">En su lugar, debe crear nuevas directivas y aplicar esas directivas solo a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="92a16-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="92a16-134">El siguiente procedimiento describe el proceso para crear objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad de servicio en servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="92a16-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="92a16-135">Por supuesto, es posible que los servidores perimetrales sean servidores independientes que no tengan cuentas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92a16-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="92a16-136">Si ese es el caso, puede usar la directiva de grupo local en lugar de la directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales con el Editor de directivas de grupo local y debe crear individualmente el mismo conjunto de directivas en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="92a16-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="92a16-137">Para iniciar el Editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92a16-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="92a16-138">Haga clic en **Inicio** y luego en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="92a16-139">En el **cuadro de** diálogo Ejecutar, **escriba gpedit.msc** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="92a16-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="92a16-140">Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo donde se haya instalado la administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="92a16-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="92a16-141">En ese caso, abra Administración de directivas de grupo (haga clic en Inicio **,** seleccione Herramientas administrativas y, a continuación, haga clic en Administración de directivas de **grupo)** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="92a16-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="92a16-142">En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="92a16-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="92a16-143">Por ejemplo, si todos los equipos de Skype Empresarial Server se encuentran en una unidad organizativa denominada Skype Empresarial Server, la nueva directiva debe crearse en la unidad organizativa de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="92a16-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="92a16-144">Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincularlo aquí.**</span><span class="sxs-lookup"><span data-stu-id="92a16-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="92a16-145">En el cuadro de diálogo Nuevo **GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre (por ejemplo, Audio de Skype Empresarial **Server)** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="92a16-146">Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic **en Editar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="92a16-147">Desde aquí, el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:</span><span class="sxs-lookup"><span data-stu-id="92a16-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="92a16-148">En el Editor de administración de directivas de grupo o en el Editor de directivas de grupo local, expanda Configuración del **equipo,** **Directivas,** Configuración de **Windows,** haga clic con el botón secundario en **QoS** basada en directivas y, a continuación, haga clic en Crear nueva **directiva.**</span><span class="sxs-lookup"><span data-stu-id="92a16-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="92a16-149">En el cuadro de diálogo **QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, Audio de Skype Empresarial **Server)** en el cuadro **Nombre.**</span><span class="sxs-lookup"><span data-stu-id="92a16-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="92a16-150">Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="92a16-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="92a16-151">Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92a16-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="92a16-152">En la página siguiente, asegúrese de que **todas las aplicaciones** están seleccionadas y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92a16-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="92a16-153">Esta configuración indica a la red que busque todos los paquetes con el valor 46 para DSCP, y no solo los paquetes creados por una aplicación en particular.</span><span class="sxs-lookup"><span data-stu-id="92a16-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="92a16-154">En la tercera página, asegúrese de que esté seleccionada cualquier dirección **IP** de origen y cualquier dirección **IP** de destino y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92a16-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="92a16-155">Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.</span><span class="sxs-lookup"><span data-stu-id="92a16-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="92a16-156">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**.</span><span class="sxs-lookup"><span data-stu-id="92a16-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="92a16-157">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Skype Empresarial Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="92a16-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="92a16-158">Bajo el encabezado **Especificar el número de puerto de destino**, seleccione Desde este puerto o intervalo de **destino.**</span><span class="sxs-lookup"><span data-stu-id="92a16-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="92a16-159">En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio.</span><span class="sxs-lookup"><span data-stu-id="92a16-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="92a16-160">Por ejemplo, si ha reservado los puertos 49152 a los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="92a16-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="92a16-161">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-161">Click **Finish**.</span></span>

<span data-ttu-id="92a16-162">Después de crear la directiva de QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="92a16-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="92a16-163">Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92a16-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="92a16-164">Use un nombre de directiva diferente (y único) (por ejemplo, Vídeo de **Skype Empresarial Server).**</span><span class="sxs-lookup"><span data-stu-id="92a16-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="92a16-p113">Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)</span><span class="sxs-lookup"><span data-stu-id="92a16-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="92a16-168">Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="92a16-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="92a16-169">Por ejemplo, si ha reservado los puertos 57501 a 65535 para vídeo, establezca el intervalo de puertos en: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="92a16-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="92a16-170">De nuevo, debe configurarse como el intervalo de puertos de destino.</span><span class="sxs-lookup"><span data-stu-id="92a16-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="92a16-171">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, realizando las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="92a16-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="92a16-172">Use un nombre de directiva diferente (y único) (por ejemplo, Uso compartido de aplicaciones de **Skype Empresarial Server).**</span><span class="sxs-lookup"><span data-stu-id="92a16-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="92a16-p115">Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)</span><span class="sxs-lookup"><span data-stu-id="92a16-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="92a16-176">Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="92a16-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="92a16-177">Por ejemplo, si ha reservado los puertos 40803 a 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="92a16-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="92a16-178">Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la directiva de grupo en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="92a16-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="92a16-179">Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="92a16-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="92a16-180">Este comando se puede ejecutar desde Skype Empresarial Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="92a16-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="92a16-181">Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="92a16-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="92a16-182">Tenga en cuenta que es posible que tenga que reiniciar el servidor perimetral incluso después de ejecutar Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="92a16-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="92a16-183">Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="92a16-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="92a16-184">Haga clic en **Inicio** y luego en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="92a16-185">En el **cuadro de** diálogo Ejecutar, **escriba regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="92a16-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="92a16-186">En el Editor del Registro, expanda **HKEY \_ LOCAL \_ MACHINE**, **SYSTEM**, **CurrentControlSet**, expand **services** y, a continuación, **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="92a16-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="92a16-187">Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**.</span><span class="sxs-lookup"><span data-stu-id="92a16-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="92a16-188">Después de crear la nueva clave del Registro, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="92a16-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="92a16-189">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="92a16-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="92a16-190">Después de crear el nuevo valor del Registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="92a16-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="92a16-191">Haga clic con el botón secundario en **No usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="92a16-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="92a16-192">En el **cuadro de diálogo Editar** cadena, escriba **1** en el cuadro de datos **Valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92a16-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="92a16-193">Cierre el Editor del Registro y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="92a16-193">Close the Registry Editor and reboot your computer.</span></span>
