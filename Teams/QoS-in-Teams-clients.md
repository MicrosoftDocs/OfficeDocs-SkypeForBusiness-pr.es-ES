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
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91b761cafa15172ae3fb0126f5059408e1a5f7ca
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246201"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="acbff-103">Configurar QoS en clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="acbff-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="acbff-104">Puede usar QoS basada en directivas en la Directiva de grupo para establecer el intervalo de puertos de origen para el valor predefinido de DSCP en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="acbff-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="acbff-105">Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acbff-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="acbff-106">_Intervalos de puerto iniciales recomendados_</span><span class="sxs-lookup"><span data-stu-id="acbff-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="acbff-107">Tipo de tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="acbff-107">Media traffic type</span></span>| <span data-ttu-id="acbff-108">Intervalo de puertos de origen del cliente</span><span class="sxs-lookup"><span data-stu-id="acbff-108">Client source port range</span></span> |<span data-ttu-id="acbff-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="acbff-109">Protocol</span></span>|<span data-ttu-id="acbff-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="acbff-110">DSCP value</span></span>|<span data-ttu-id="acbff-111">Clase de DSCP</span><span class="sxs-lookup"><span data-stu-id="acbff-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="acbff-112">Audio</span><span class="sxs-lookup"><span data-stu-id="acbff-112">Audio</span></span>| <span data-ttu-id="acbff-113">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="acbff-113">50,000–50,019</span></span>|<span data-ttu-id="acbff-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="acbff-114">TCP/UDP</span></span>|<span data-ttu-id="acbff-115">46</span><span class="sxs-lookup"><span data-stu-id="acbff-115">46</span></span>|<span data-ttu-id="acbff-116">Desvío rápido (EF)</span><span class="sxs-lookup"><span data-stu-id="acbff-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="acbff-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="acbff-117">Video</span></span>| <span data-ttu-id="acbff-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="acbff-118">50,020–50,039</span></span>|<span data-ttu-id="acbff-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="acbff-119">TCP/UDP</span></span>|<span data-ttu-id="acbff-120">34</span><span class="sxs-lookup"><span data-stu-id="acbff-120">34</span></span>|<span data-ttu-id="acbff-121">Desvío garantizado (AF41)</span><span class="sxs-lookup"><span data-stu-id="acbff-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="acbff-122">Aplicación/pantalla compartida</span><span class="sxs-lookup"><span data-stu-id="acbff-122">Application/Screen Sharing</span></span>| <span data-ttu-id="acbff-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="acbff-123">50,040–50,059</span></span>|<span data-ttu-id="acbff-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="acbff-124">TCP/UDP</span></span>|<span data-ttu-id="acbff-125">18</span><span class="sxs-lookup"><span data-stu-id="acbff-125">18</span></span>|<span data-ttu-id="acbff-126">Reenvío asegurado (AF21)</span><span class="sxs-lookup"><span data-stu-id="acbff-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="acbff-127">Siempre que sea posible, establezca la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="acbff-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="acbff-128">Los pasos siguientes son muy similares a la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes de Skype empresarial Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que pueden no ser necesarios.</span><span class="sxs-lookup"><span data-stu-id="acbff-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="acbff-129">Para crear una directiva de audio de QoS para equipos con Windows 10 Unidos a un dominio, primero debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="acbff-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="acbff-130">Abra administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="acbff-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="acbff-131">En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="acbff-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="acbff-132">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, la nueva Directiva debe crearse en la uo cliente.</span><span class="sxs-lookup"><span data-stu-id="acbff-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="acbff-133">Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.</span><span class="sxs-lookup"><span data-stu-id="acbff-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="acbff-134">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="acbff-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="acbff-135">Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="acbff-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="acbff-136">En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="acbff-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="acbff-137">En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="acbff-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="acbff-138">Seleccione **especificar valor de DSCP** y establezca el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="acbff-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="acbff-139">Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="acbff-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="acbff-140">En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable** y, \*\*\*\* a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="acbff-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="acbff-141">Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de equipos.</span><span class="sxs-lookup"><span data-stu-id="acbff-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="acbff-142">En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="acbff-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="acbff-143">Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado los paquetes y del equipo (dirección IP) que recibirá los paquetes.</span><span class="sxs-lookup"><span data-stu-id="acbff-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="acbff-144">En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo al que se aplica esta directiva de QoS** .</span><span class="sxs-lookup"><span data-stu-id="acbff-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="acbff-145">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados.</span><span class="sxs-lookup"><span data-stu-id="acbff-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="acbff-146">En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**.</span><span class="sxs-lookup"><span data-stu-id="acbff-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="acbff-147">En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio.</span><span class="sxs-lookup"><span data-stu-id="acbff-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="acbff-148">Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="acbff-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="acbff-149">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="acbff-149">Click **Finish**.</span></span>

11. <span data-ttu-id="acbff-150">Repita los pasos 5-10 para crear directivas de vídeo y de uso compartido de aplicaciones y escritorio, sustituyendo los valores correspondientes en los pasos 6 y 10.</span><span class="sxs-lookup"><span data-stu-id="acbff-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="acbff-151">Las nuevas directivas que haya creado no surtirán efecto hasta que se actualice la Directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="acbff-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="acbff-152">Aunque la Directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="acbff-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="acbff-153">En cada equipo para el que desee actualizar la Directiva de grupo, abra una consola de comandos.</span><span class="sxs-lookup"><span data-stu-id="acbff-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="acbff-154">Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.</span><span class="sxs-lookup"><span data-stu-id="acbff-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="acbff-155">En el símbolo del sistema, escriba</span><span class="sxs-lookup"><span data-stu-id="acbff-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="acbff-156">Comprobar las marcas de DSCP en el objeto de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="acbff-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="acbff-157">Para comprobar que se han establecido los valores del objeto de directiva de grupo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="acbff-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="acbff-158">Abra una consola de comandos.</span><span class="sxs-lookup"><span data-stu-id="acbff-158">Open a command console.</span></span> <span data-ttu-id="acbff-159">Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.</span><span class="sxs-lookup"><span data-stu-id="acbff-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="acbff-160">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="acbff-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="acbff-161">Esto generará un informe y lo enviará a un archivo de texto denominado GP. txt.</span><span class="sxs-lookup"><span data-stu-id="acbff-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="acbff-162">Como alternativa, puede escribir el siguiente comando para generar los mismos datos en un informe HTML más legible denominado GP. html:</span><span class="sxs-lookup"><span data-stu-id="acbff-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="acbff-163">![Captura de pantalla de la ventana de la consola que ejecuta el comando Gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de la consola que ejecuta el comando Gpresult.")</span><span class="sxs-lookup"><span data-stu-id="acbff-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="acbff-164">En el archivo generado, busque el encabezado **Applied Group Policy Objects** y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente se encuentran en la lista de directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="acbff-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="acbff-165">Abra el editor del registro y vaya a:</span><span class="sxs-lookup"><span data-stu-id="acbff-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="acbff-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="acbff-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="acbff-167">Compruebe los valores de las entradas del registro que se muestran en la tabla 4.</span><span class="sxs-lookup"><span data-stu-id="acbff-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="acbff-168">_Tabla 4. Valores de las entradas del registro de Windows para QoS_</span><span class="sxs-lookup"><span data-stu-id="acbff-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="acbff-169">Nombre</span><span class="sxs-lookup"><span data-stu-id="acbff-169">Name</span></span>          |  <span data-ttu-id="acbff-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="acbff-170">Type</span></span>  |    <span data-ttu-id="acbff-171">Datos</span><span class="sxs-lookup"><span data-stu-id="acbff-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="acbff-172">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="acbff-172">Application Name</span></span>    | <span data-ttu-id="acbff-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-173">REG_SZ</span></span> |  <span data-ttu-id="acbff-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="acbff-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="acbff-175">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="acbff-175">DSCP Value</span></span>       | <span data-ttu-id="acbff-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-176">REG_SZ</span></span> |     <span data-ttu-id="acbff-177">46</span><span class="sxs-lookup"><span data-stu-id="acbff-177">46</span></span>      |
   |        <span data-ttu-id="acbff-178">IP local</span><span class="sxs-lookup"><span data-stu-id="acbff-178">Local IP</span></span>        | <span data-ttu-id="acbff-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="acbff-180">Longitud del prefijo de IP local</span><span class="sxs-lookup"><span data-stu-id="acbff-180">Local IP Prefix Length</span></span> | <span data-ttu-id="acbff-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="acbff-182">Puerto local</span><span class="sxs-lookup"><span data-stu-id="acbff-182">Local Port</span></span>       | <span data-ttu-id="acbff-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-183">REG_SZ</span></span> | <span data-ttu-id="acbff-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="acbff-184">50000-50019</span></span> |
   |        <span data-ttu-id="acbff-185">Protocolo</span><span class="sxs-lookup"><span data-stu-id="acbff-185">Protocol</span></span>        | <span data-ttu-id="acbff-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="acbff-187">IP remota</span><span class="sxs-lookup"><span data-stu-id="acbff-187">Remote IP</span></span>        | <span data-ttu-id="acbff-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="acbff-189">Prefijo IP remoto</span><span class="sxs-lookup"><span data-stu-id="acbff-189">Remote IP Prefix</span></span>    | <span data-ttu-id="acbff-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="acbff-191">Puerto remoto</span><span class="sxs-lookup"><span data-stu-id="acbff-191">Remote Port</span></span>       | <span data-ttu-id="acbff-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="acbff-193">Velocidad de limitación</span><span class="sxs-lookup"><span data-stu-id="acbff-193">Throttle Rate</span></span>      | <span data-ttu-id="acbff-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="acbff-194">REG_SZ</span></span> |     <span data-ttu-id="acbff-195">-1</span><span class="sxs-lookup"><span data-stu-id="acbff-195">-1</span></span>      |

5. <span data-ttu-id="acbff-196">Compruebe que el valor de la entrada del nombre de la aplicación es correcto para el cliente que está usando y compruebe que tanto el valor de DSCP como las entradas del puerto local reflejan la configuración del objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="acbff-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
