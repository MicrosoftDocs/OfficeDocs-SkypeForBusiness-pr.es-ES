---
title: Implementar calidad de servicio (QoS) en clientes de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo usar Calidad de servicio (QoS) para optimizar el tráfico de red del cliente de escritorio de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526407"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="f1112-103">Implementar calidad de servicio (QoS) en clientes de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1112-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="f1112-104">Puede usar QoS (Calidad de servicio) basada en directivas en la directiva de grupo para establecer el intervalo de puertos de origen para el valor de DSCP predefinido en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="f1112-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="f1112-105">Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1112-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="f1112-106">*Tabla 1. Intervalos de puertos iniciales recomendados*</span><span class="sxs-lookup"><span data-stu-id="f1112-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="f1112-107">Tipo de tráfico de medios </span><span class="sxs-lookup"><span data-stu-id="f1112-107">Media traffic type</span></span>| <span data-ttu-id="f1112-108">Rango de puertos de origen del cliente </span><span class="sxs-lookup"><span data-stu-id="f1112-108">Client source port range</span></span> |<span data-ttu-id="f1112-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f1112-109">Protocol</span></span>|<span data-ttu-id="f1112-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="f1112-110">DSCP value</span></span>|<span data-ttu-id="f1112-111">Clase DSCP</span><span class="sxs-lookup"><span data-stu-id="f1112-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="f1112-112">Audio</span><span class="sxs-lookup"><span data-stu-id="f1112-112">Audio</span></span>| <span data-ttu-id="f1112-113">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="f1112-113">50,000–50,019</span></span>|<span data-ttu-id="f1112-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f1112-114">TCP/UDP</span></span>|<span data-ttu-id="f1112-115">46</span><span class="sxs-lookup"><span data-stu-id="f1112-115">46</span></span>|<span data-ttu-id="f1112-116">Desvío rápido (EF)</span><span class="sxs-lookup"><span data-stu-id="f1112-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="f1112-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="f1112-117">Video</span></span>| <span data-ttu-id="f1112-118">50 020 – 50 039</span><span class="sxs-lookup"><span data-stu-id="f1112-118">50,020–50,039</span></span>|<span data-ttu-id="f1112-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f1112-119">TCP/UDP</span></span>|<span data-ttu-id="f1112-120">34</span><span class="sxs-lookup"><span data-stu-id="f1112-120">34</span></span>|<span data-ttu-id="f1112-121">Desvío garantizado (AF41)</span><span class="sxs-lookup"><span data-stu-id="f1112-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="f1112-122">Aplicación/Compartir pantalla</span><span class="sxs-lookup"><span data-stu-id="f1112-122">Application/Screen Sharing</span></span>| <span data-ttu-id="f1112-123">50 040 – 50 059</span><span class="sxs-lookup"><span data-stu-id="f1112-123">50,040–50,059</span></span>|<span data-ttu-id="f1112-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f1112-124">TCP/UDP</span></span>|<span data-ttu-id="f1112-125">18</span><span class="sxs-lookup"><span data-stu-id="f1112-125">18</span></span>|<span data-ttu-id="f1112-126">Desvío garantizado (AF21)</span><span class="sxs-lookup"><span data-stu-id="f1112-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="f1112-127">Siempre que sea posible, configure las opciones de QoS basadas en directivas dentro de un objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="f1112-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="f1112-128">Los pasos siguientes son muy similares a la configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype Empresarial  [Server,](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)que tiene algunos detalles adicionales que puede que no sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="f1112-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="f1112-129">Para crear una directiva de audio de QoS para equipos Windows 10 unidos a un dominio, primero inicie sesión en un equipo en el que se haya instalado la administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="f1112-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="f1112-130">Abra la administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en Administración de directivas de grupo) y, después, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1112-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="f1112-131">En Administración de directivas de grupo, busque el contenedor donde debe crearse la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="f1112-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="f1112-132">Por ejemplo, si todos los equipos cliente se encuentran en una UO denominada **Clientes,** la nueva directiva debe crearse en la UO Clientes.</span><span class="sxs-lookup"><span data-stu-id="f1112-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="f1112-133">Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincóquelo aquí.**</span><span class="sxs-lookup"><span data-stu-id="f1112-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="f1112-134">En el **cuadro de diálogo Nuevo GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="f1112-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="f1112-135">Haga clic con el botón derecho en la directiva recién creada y, a continuación, haga clic **en Editar.**</span><span class="sxs-lookup"><span data-stu-id="f1112-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="f1112-136">En el Editor de administración de directivas de grupo, expanda Configuración del **equipo,** Configuración de **Windows,** Haga clic con el botón derecho en **QoS** basada en directiva y, a continuación, haga clic **en Crear nueva directiva.**</span><span class="sxs-lookup"><span data-stu-id="f1112-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="f1112-137">En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el **cuadro** Nombre.</span><span class="sxs-lookup"><span data-stu-id="f1112-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="f1112-138">Seleccione **Especificar valor de DSCP** y establezca el valor en **46.**</span><span class="sxs-lookup"><span data-stu-id="f1112-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="f1112-139">Deje **la opción "Especificar velocidad de limitación** de salida" no seleccionada y, a continuación, haga clic **en Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f1112-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="f1112-140">En la página siguiente, seleccione Solo las aplicaciones con este nombre **ejecutable,** escriba el nombre **Teams.exe** y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f1112-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="f1112-141">Esta configuración indica a la directiva que solo priorice el tráfico de coincidencia desde el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="f1112-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="f1112-142">En la tercera página, asegúrese de seleccionar Cualquier dirección **IP** de origen y Cualquier **dirección IP** de destino y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f1112-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="f1112-143">Estas dos configuraciones garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que envió los paquetes y del equipo (dirección IP) que recibirán los paquetes.</span><span class="sxs-lookup"><span data-stu-id="f1112-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="f1112-144">En la página cuatro, seleccione **TCP y UDP** en el seleccionar el protocolo que esta directiva de **QoS aplica a** la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f1112-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="f1112-145">TCP (Protocolo de control de transmisión) y UDP (protocolo de datagramas de usuario) son los dos protocolos de red más usados.</span><span class="sxs-lookup"><span data-stu-id="f1112-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="f1112-146">En el encabezado **Especifique el número de puerto de origen,** seleccione Desde este puerto o rango de **origen.**</span><span class="sxs-lookup"><span data-stu-id="f1112-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="f1112-147">En el cuadro de texto correspondiente, escriba el intervalo de puertos reservado para las transmisiones de audio.</span><span class="sxs-lookup"><span data-stu-id="f1112-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="f1112-148">Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="f1112-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="f1112-149">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f1112-149">Click **Finish**.</span></span>

1. <span data-ttu-id="f1112-150">Repita los pasos del 5 al 10 para crear directivas de uso compartido de aplicaciones y vídeo, sustituyendo los valores apropiados en los pasos 6 y 10.</span><span class="sxs-lookup"><span data-stu-id="f1112-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="f1112-151">Las nuevas directivas que ha creado no efecto hasta que la directiva de grupo se actualice en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="f1112-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="f1112-152">Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1112-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="f1112-153">En cada equipo para el que quiera actualizar la directiva de grupo, abra un símbolo del sistema como administrador *(ejecutar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="f1112-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="f1112-154">En el símbolo del sistema, escribe</span><span class="sxs-lookup"><span data-stu-id="f1112-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="f1112-155">Comprobar marcas de DSCP en el objeto de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="f1112-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="f1112-156">Para comprobar que los valores del objeto de directiva de grupo se han establecido, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1112-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="f1112-157">Abrir un símbolo del sistema como administrador *(Ejecutar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="f1112-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="f1112-158">En el símbolo del sistema, escribe</span><span class="sxs-lookup"><span data-stu-id="f1112-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="f1112-159">Esto generará un informe de los GPO aplicados y lo enviará a un archivo de texto denominado *gp.txt.*</span><span class="sxs-lookup"><span data-stu-id="f1112-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="f1112-160">Para obtener un informe HTML más legible denominado *gp.html,* escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1112-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="f1112-161">En el archivo generado, busque el encabezado **Objetos** de directiva de grupo aplicados y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente están en la lista de directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="f1112-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="f1112-162">Abra el Editor del Registro y vaya a</span><span class="sxs-lookup"><span data-stu-id="f1112-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="f1112-163">Directivas de software DE MÁQUINA LOCAL de HKEY \_ \_ para \\ \\ \\ \\ \\ QoS de Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="f1112-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="f1112-164">Compruebe los valores de las entradas del Registro enumeradas en la tabla 2.</span><span class="sxs-lookup"><span data-stu-id="f1112-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="f1112-165">*Tabla 2. Valores de las entradas del registro de Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="f1112-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="f1112-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="f1112-166">Name</span></span>          |  <span data-ttu-id="f1112-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="f1112-167">Type</span></span>  |    <span data-ttu-id="f1112-168">Datos</span><span class="sxs-lookup"><span data-stu-id="f1112-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="f1112-169">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f1112-169">Application Name</span></span>    | <span data-ttu-id="f1112-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-170">REG_SZ</span></span> |  <span data-ttu-id="f1112-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="f1112-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="f1112-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="f1112-172">DSCP Value</span></span>       | <span data-ttu-id="f1112-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-173">REG_SZ</span></span> |     <span data-ttu-id="f1112-174">46</span><span class="sxs-lookup"><span data-stu-id="f1112-174">46</span></span>      |
   |        <span data-ttu-id="f1112-175">IP local</span><span class="sxs-lookup"><span data-stu-id="f1112-175">Local IP</span></span>        | <span data-ttu-id="f1112-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="f1112-177">Longitud del prefijo de IP local</span><span class="sxs-lookup"><span data-stu-id="f1112-177">Local IP Prefix Length</span></span> | <span data-ttu-id="f1112-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="f1112-179">Puerto local</span><span class="sxs-lookup"><span data-stu-id="f1112-179">Local Port</span></span>       | <span data-ttu-id="f1112-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-180">REG_SZ</span></span> | <span data-ttu-id="f1112-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="f1112-181">50000-50019</span></span> |
   |        <span data-ttu-id="f1112-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f1112-182">Protocol</span></span>        | <span data-ttu-id="f1112-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="f1112-184">IP remota</span><span class="sxs-lookup"><span data-stu-id="f1112-184">Remote IP</span></span>        | <span data-ttu-id="f1112-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="f1112-186">Prefijo IP remoto</span><span class="sxs-lookup"><span data-stu-id="f1112-186">Remote IP Prefix</span></span>    | <span data-ttu-id="f1112-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="f1112-188">Puerto remoto</span><span class="sxs-lookup"><span data-stu-id="f1112-188">Remote Port</span></span>       | <span data-ttu-id="f1112-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="f1112-190">Velocidad de limitación</span><span class="sxs-lookup"><span data-stu-id="f1112-190">Throttle Rate</span></span>      | <span data-ttu-id="f1112-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f1112-191">REG_SZ</span></span> |     <span data-ttu-id="f1112-192">-1</span><span class="sxs-lookup"><span data-stu-id="f1112-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="f1112-193">Compruebe que el valor de la entrada de nombre de aplicación es correcto para el cliente que está usando y compruebe que las entradas de valor de DSCP y puerto local reflejen la configuración en el objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="f1112-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f1112-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f1112-194">Related topics</span></span>

[<span data-ttu-id="f1112-195">Implementar calidad de servicio (QoS) en Teams</span><span class="sxs-lookup"><span data-stu-id="f1112-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)