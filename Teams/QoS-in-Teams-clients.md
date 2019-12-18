---
title: Implementar Calidad de servicio en clientes de Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implemente la calidad de servicio (QoS) para los clientes de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3447f86be825099b7fada63fecd1b106f94cd80a
ms.sourcegitcommit: 2b76e6a9a6ba0eb391e4adba5402eb572d1dc61f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2019
ms.locfileid: "40303872"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="67d3f-103">Configurar QoS en clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="67d3f-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="67d3f-104">Puede usar QoS basada en directivas en la Directiva de grupo para establecer el intervalo de puertos de origen para el valor predefinido de DSCP en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="67d3f-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="67d3f-105">Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="67d3f-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="67d3f-106">*Tabla 1. Intervalos de puerto iniciales recomendados*</span><span class="sxs-lookup"><span data-stu-id="67d3f-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="67d3f-107">Tipo de tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="67d3f-107">Media traffic type</span></span>| <span data-ttu-id="67d3f-108">Intervalo de puertos de origen del cliente</span><span class="sxs-lookup"><span data-stu-id="67d3f-108">Client source port range</span></span> |<span data-ttu-id="67d3f-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="67d3f-109">Protocol</span></span>|<span data-ttu-id="67d3f-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="67d3f-110">DSCP value</span></span>|<span data-ttu-id="67d3f-111">Clase de DSCP</span><span class="sxs-lookup"><span data-stu-id="67d3f-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="67d3f-112">Audio</span><span class="sxs-lookup"><span data-stu-id="67d3f-112">Audio</span></span>| <span data-ttu-id="67d3f-113">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="67d3f-113">50,000–50,019</span></span>|<span data-ttu-id="67d3f-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="67d3f-114">TCP/UDP</span></span>|<span data-ttu-id="67d3f-115">46</span><span class="sxs-lookup"><span data-stu-id="67d3f-115">46</span></span>|<span data-ttu-id="67d3f-116">Desvío rápido (EF)</span><span class="sxs-lookup"><span data-stu-id="67d3f-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="67d3f-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="67d3f-117">Video</span></span>| <span data-ttu-id="67d3f-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="67d3f-118">50,020–50,039</span></span>|<span data-ttu-id="67d3f-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="67d3f-119">TCP/UDP</span></span>|<span data-ttu-id="67d3f-120">34</span><span class="sxs-lookup"><span data-stu-id="67d3f-120">34</span></span>|<span data-ttu-id="67d3f-121">Desvío garantizado (AF41)</span><span class="sxs-lookup"><span data-stu-id="67d3f-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="67d3f-122">Aplicación/pantalla compartida</span><span class="sxs-lookup"><span data-stu-id="67d3f-122">Application/Screen Sharing</span></span>| <span data-ttu-id="67d3f-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="67d3f-123">50,040–50,059</span></span>|<span data-ttu-id="67d3f-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="67d3f-124">TCP/UDP</span></span>|<span data-ttu-id="67d3f-125">18</span><span class="sxs-lookup"><span data-stu-id="67d3f-125">18</span></span>|<span data-ttu-id="67d3f-126">Reenvío asegurado (AF21)</span><span class="sxs-lookup"><span data-stu-id="67d3f-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="67d3f-127">Siempre que sea posible, establezca la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="67d3f-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="67d3f-128">Los pasos siguientes son muy similares a la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes de Skype empresarial Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que pueden no ser necesarios.</span><span class="sxs-lookup"><span data-stu-id="67d3f-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="67d3f-129">Para crear una directiva de audio de QoS para equipos con Windows 10 Unidos a un dominio, primero debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="67d3f-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="67d3f-130">Abra administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="67d3f-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="67d3f-131">En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="67d3f-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="67d3f-132">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, la nueva Directiva debe crearse en la unidad organizativa clientes.</span><span class="sxs-lookup"><span data-stu-id="67d3f-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="67d3f-133">Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="67d3f-134">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="67d3f-135">Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="67d3f-136">En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="67d3f-137">En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="67d3f-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="67d3f-138">Seleccione **especificar valor de DSCP** y establezca el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="67d3f-139">Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="67d3f-140">En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable** **y, a**continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="67d3f-141">Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de equipos.</span><span class="sxs-lookup"><span data-stu-id="67d3f-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="67d3f-142">En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="67d3f-143">Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado los paquetes y del equipo (dirección IP) que recibirá los paquetes.</span><span class="sxs-lookup"><span data-stu-id="67d3f-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="67d3f-144">En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo al que se aplica esta directiva de QoS** .</span><span class="sxs-lookup"><span data-stu-id="67d3f-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="67d3f-145">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados.</span><span class="sxs-lookup"><span data-stu-id="67d3f-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="67d3f-146">En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="67d3f-147">En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio.</span><span class="sxs-lookup"><span data-stu-id="67d3f-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="67d3f-148">Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="67d3f-149">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="67d3f-149">Click **Finish**.</span></span>

1. <span data-ttu-id="67d3f-150">Repita los pasos 5-10 para crear directivas de vídeo y de uso compartido de aplicaciones y escritorio, sustituyendo los valores correspondientes en los pasos 6 y 10.</span><span class="sxs-lookup"><span data-stu-id="67d3f-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="67d3f-151">Las nuevas directivas que haya creado no surtirán efecto hasta que se actualice la Directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="67d3f-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="67d3f-152">Aunque la Directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="67d3f-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="67d3f-153">En cada equipo para el que desee actualizar la Directiva de grupo, abra un símbolo del sistema como administrador (*Ejecutar como administrador*).</span><span class="sxs-lookup"><span data-stu-id="67d3f-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="67d3f-154">En el símbolo del sistema, escriba</span><span class="sxs-lookup"><span data-stu-id="67d3f-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="67d3f-155">Comprobar las marcas de DSCP en el objeto de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="67d3f-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="67d3f-156">Para comprobar que se han establecido los valores del objeto de directiva de grupo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="67d3f-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="67d3f-157">Abra un símbolo del sistema como administrador (*Ejecutar como administrador*).</span><span class="sxs-lookup"><span data-stu-id="67d3f-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="67d3f-158">En el símbolo del sistema, escriba</span><span class="sxs-lookup"><span data-stu-id="67d3f-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="67d3f-159">Esto generará un informe de los GPO aplicados y lo enviará a un archivo de texto denominado *GP. txt*.</span><span class="sxs-lookup"><span data-stu-id="67d3f-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="67d3f-160">Para obtener un informe HTML más legible denominado *GP. html*, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67d3f-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="67d3f-161">En el archivo generado, busque el encabezado **Applied Group Policy Objects** y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente se encuentran en la lista de directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="67d3f-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="67d3f-162">Abra el editor del registro y vaya a</span><span class="sxs-lookup"><span data-stu-id="67d3f-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="67d3f-163">Directivas\_\\de\_software\\\\del equipo local\\de\\HKEY Microsoft Windows QoS</span><span class="sxs-lookup"><span data-stu-id="67d3f-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="67d3f-164">Compruebe los valores de las entradas del registro que se muestran en la tabla 2.</span><span class="sxs-lookup"><span data-stu-id="67d3f-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="67d3f-165">*Tabla 2. Valores de las entradas del registro de Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="67d3f-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="67d3f-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="67d3f-166">Name</span></span>          |  <span data-ttu-id="67d3f-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="67d3f-167">Type</span></span>  |    <span data-ttu-id="67d3f-168">Datos</span><span class="sxs-lookup"><span data-stu-id="67d3f-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="67d3f-169">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="67d3f-169">Application Name</span></span>    | <span data-ttu-id="67d3f-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-170">REG_SZ</span></span> |  <span data-ttu-id="67d3f-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="67d3f-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="67d3f-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="67d3f-172">DSCP Value</span></span>       | <span data-ttu-id="67d3f-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-173">REG_SZ</span></span> |     <span data-ttu-id="67d3f-174">46</span><span class="sxs-lookup"><span data-stu-id="67d3f-174">46</span></span>      |
   |        <span data-ttu-id="67d3f-175">IP local</span><span class="sxs-lookup"><span data-stu-id="67d3f-175">Local IP</span></span>        | <span data-ttu-id="67d3f-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="67d3f-177">Longitud del prefijo de IP local</span><span class="sxs-lookup"><span data-stu-id="67d3f-177">Local IP Prefix Length</span></span> | <span data-ttu-id="67d3f-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="67d3f-179">Puerto local</span><span class="sxs-lookup"><span data-stu-id="67d3f-179">Local Port</span></span>       | <span data-ttu-id="67d3f-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-180">REG_SZ</span></span> | <span data-ttu-id="67d3f-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="67d3f-181">50000-50019</span></span> |
   |        <span data-ttu-id="67d3f-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="67d3f-182">Protocol</span></span>        | <span data-ttu-id="67d3f-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="67d3f-184">IP remota</span><span class="sxs-lookup"><span data-stu-id="67d3f-184">Remote IP</span></span>        | <span data-ttu-id="67d3f-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="67d3f-186">Prefijo IP remoto</span><span class="sxs-lookup"><span data-stu-id="67d3f-186">Remote IP Prefix</span></span>    | <span data-ttu-id="67d3f-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="67d3f-188">Puerto remoto</span><span class="sxs-lookup"><span data-stu-id="67d3f-188">Remote Port</span></span>       | <span data-ttu-id="67d3f-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="67d3f-190">Velocidad de limitación</span><span class="sxs-lookup"><span data-stu-id="67d3f-190">Throttle Rate</span></span>      | <span data-ttu-id="67d3f-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67d3f-191">REG_SZ</span></span> |     <span data-ttu-id="67d3f-192">-1</span><span class="sxs-lookup"><span data-stu-id="67d3f-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="67d3f-193">Compruebe que el valor de la entrada del nombre de la aplicación es correcto para el cliente que está usando y compruebe que tanto el valor de DSCP como las entradas del puerto local reflejan la configuración del objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="67d3f-193">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
