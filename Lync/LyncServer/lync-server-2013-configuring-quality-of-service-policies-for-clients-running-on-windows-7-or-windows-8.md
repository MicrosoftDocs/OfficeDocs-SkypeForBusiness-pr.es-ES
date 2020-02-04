---
title: 'Lync Server 2013: configuración de directivas de calidad de servicio para clientes que ejecutan Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc06f5079fc6876c85324af67bd22be12f85a3c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="dbe0a-102">Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que funcionen en Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="dbe0a-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbe0a-103">_**Última modificación del tema:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="dbe0a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="dbe0a-104">Además de especificar intervalos de puerto para que los usen sus clientes de Lync, también debe crear directivas de calidad de servicio por separado que se aplicarán a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="dbe0a-105">(Las directivas de calidad de servicio creadas para servidores de conferencia, aplicaciones y mediación no se deben aplicar a los equipos cliente). Esta información se aplica únicamente a los equipos que ejecutan el cliente de Lync 2013 y Windows 7 o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="dbe0a-106">En el ejemplo siguiente se usa este conjunto de intervalos de puerto para crear una directiva de audio y una directiva de vídeo:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbe0a-107">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="dbe0a-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="dbe0a-108">Inicio de Puerto</span><span class="sxs-lookup"><span data-stu-id="dbe0a-108">Port Start</span></span></th>
<th><span data-ttu-id="dbe0a-109">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="dbe0a-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbe0a-110">Audio</span><span class="sxs-lookup"><span data-stu-id="dbe0a-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-111">50020</span><span class="sxs-lookup"><span data-stu-id="dbe0a-111">50020</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-112">veinte</span><span class="sxs-lookup"><span data-stu-id="dbe0a-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe0a-113">Vídeo</span><span class="sxs-lookup"><span data-stu-id="dbe0a-113">Video</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-114">58000</span><span class="sxs-lookup"><span data-stu-id="dbe0a-114">58000</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-115">veinte</span><span class="sxs-lookup"><span data-stu-id="dbe0a-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbe0a-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dbe0a-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-117">42000</span><span class="sxs-lookup"><span data-stu-id="dbe0a-117">42000</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-118">veinte</span><span class="sxs-lookup"><span data-stu-id="dbe0a-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbe0a-119">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="dbe0a-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-120">42020</span><span class="sxs-lookup"><span data-stu-id="dbe0a-120">42020</span></span></p></td>
<td><p><span data-ttu-id="dbe0a-121">veinte</span><span class="sxs-lookup"><span data-stu-id="dbe0a-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dbe0a-122">Para crear una directiva de audio de calidad de servicio para equipos con Windows 7 o Windows 8, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="dbe0a-123">Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="dbe0a-124">En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="dbe0a-125">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="dbe0a-126">Haga clic con el botón secundario en el contenedor correspondiente y luego haga clic en **crear un GPO en este dominio y vincúlelo aquí**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="dbe0a-127">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **audio de Lync**) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="dbe0a-128">Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="dbe0a-129">En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **directivas**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="dbe0a-130">En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva (por ejemplo, **audio de Lync**) en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="dbe0a-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="dbe0a-131">Seleccione **especificar valor de DSCP** y establezca el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="dbe0a-132">Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="dbe0a-133">En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable** , escriba el nombre **Lync. exe**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="dbe0a-134">Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="dbe0a-135">En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="dbe0a-136">Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="dbe0a-137">En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** .</span><span class="sxs-lookup"><span data-stu-id="dbe0a-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="dbe0a-138">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="dbe0a-139">En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="dbe0a-140">En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="dbe0a-141">Por ejemplo, si ha reservado los puertos 50020 a través de los puertos 50039 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="dbe0a-142">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-142">Click **Finish**.</span></span>

<span data-ttu-id="dbe0a-143">Después de crear la directiva QoS para el audio, debe crear una segunda Directiva para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="dbe0a-144">Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="dbe0a-145">Use un nombre de directiva diferente (y único) (por ejemplo, **vídeo de Lync**).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="dbe0a-146">Establezca el valor de DSCP en **34** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="dbe0a-147">(Como se ha indicado anteriormente, no tiene que usar el valor de DSCP 34; simplemente debe asignar un valor de DSCP diferente al utilizado para el audio).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="dbe0a-148">Use el intervalo de puertos configurado previamente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="dbe0a-149">Por ejemplo, si ha reservado los puertos 58000 a 58019 para el vídeo, establezca el intervalo de puertos en: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="dbe0a-150">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice estas sustituciones:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="dbe0a-151">Use un nombre de directiva diferente (y único) (por ejemplo, **compartir aplicaciones de Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="dbe0a-152">Establezca el valor de DSCP en **24** en lugar de 46.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="dbe0a-153">(Nuevamente, este valor no tiene que ser 24; simplemente debe ser diferente de los valores de DSCP usados para el audio y el vídeo).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="dbe0a-154">Use el intervalo de puertos configurado previamente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="dbe0a-155">Por ejemplo, si ha reservado los puertos 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="dbe0a-156">Para una directiva de transferencia de archivos:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="dbe0a-157">Use un nombre de directiva diferente (y único) (por ejemplo, **transferencias de archivos de Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="dbe0a-158">Establezca el valor de DSCP en **14**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="dbe0a-159">(Nuevamente, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="dbe0a-160">Use el intervalo de puertos configurado previamente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="dbe0a-161">Por ejemplo, si ha reservado los puertos 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="dbe0a-162">Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="dbe0a-163">Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="dbe0a-164">Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="dbe0a-165">Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="dbe0a-166">Tenga en cuenta que estas directivas deben ir dirigidas a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="dbe0a-167">No se deben aplicar a servidores que ejecuten Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="dbe0a-168">Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="dbe0a-169">Haga clic en **Inicio** y, después, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dbe0a-170">En el cuadro de diálogo **Ejecutar** , escriba **regedit** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="dbe0a-171">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="dbe0a-172">Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="dbe0a-173">Después de crear la nueva clave del registro, escriba **QoS** y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="dbe0a-174">Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="dbe0a-175">Después de crear el nuevo valor del registro, escriba **no use NLA** y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="dbe0a-176">Haga doble clic en **no usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="dbe0a-177">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="dbe0a-178">Cierre el editor del registro y, a continuación, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="dbe0a-179">Configuración de la calidad de servicio en equipos con varios adaptadores de red</span><span class="sxs-lookup"><span data-stu-id="dbe0a-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="dbe0a-180">Si tiene un equipo con varios adaptadores de red, ocasionalmente puede encontrarse con problemas en los que los valores de DSCP se muestran como 0x00 en lugar del valor configurado.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="dbe0a-181">Esto suele ocurrir en equipos en los que uno o varios de los adaptadores de red no pueden obtener acceso al dominio de Active Directory (por ejemplo, si se usan para una red privada).</span><span class="sxs-lookup"><span data-stu-id="dbe0a-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="dbe0a-182">En casos como ese, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="dbe0a-183">Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="dbe0a-184">Esto se puede realizar mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="dbe0a-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="dbe0a-185">Haga clic en **Inicio** y, después, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dbe0a-186">En el cuadro de diálogo **Ejecutar** , escriba **regedit** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="dbe0a-187">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="dbe0a-188">Si no ve una clave del registro denominada **QoS** , haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, después, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="dbe0a-189">Una vez creada la nueva clave, escriba **QoS** y, a continuación, presione Entrar para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="dbe0a-190">Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="dbe0a-191">Después de crear el nuevo valor del registro, escriba **no use NLA** y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="dbe0a-192">Haga doble clic en **no usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="dbe0a-193">En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="dbe0a-194">Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="dbe0a-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

