---
title: Implementar calidad de servicio (QoS) en clientes de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo usar calidad de servicio (QoS) para optimizar el tráfico de red para el cliente de escritorio de Microsoft Teams.
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
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094788"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="3d227-103">Implementar calidad de servicio (QoS) en clientes de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d227-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="3d227-104">Puede usar calidad de servicio (QoS) basada en directivas dentro de la directiva de grupo para establecer el intervalo de puertos de origen para el valor DSCP predefinido en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d227-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="3d227-105">Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3d227-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="3d227-106">*Tabla 1. Rangos de puerto iniciales recomendados*</span><span class="sxs-lookup"><span data-stu-id="3d227-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="3d227-107">Tipo de tráfico de medios </span><span class="sxs-lookup"><span data-stu-id="3d227-107">Media traffic type</span></span>| <span data-ttu-id="3d227-108">Rango de puertos de origen del cliente </span><span class="sxs-lookup"><span data-stu-id="3d227-108">Client source port range</span></span> |<span data-ttu-id="3d227-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="3d227-109">Protocol</span></span>|<span data-ttu-id="3d227-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="3d227-110">DSCP value</span></span>|<span data-ttu-id="3d227-111">Clase DSCP</span><span class="sxs-lookup"><span data-stu-id="3d227-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="3d227-112">Audio</span><span class="sxs-lookup"><span data-stu-id="3d227-112">Audio</span></span>| <span data-ttu-id="3d227-113">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="3d227-113">50,000–50,019</span></span>|<span data-ttu-id="3d227-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3d227-114">TCP/UDP</span></span>|<span data-ttu-id="3d227-115">46</span><span class="sxs-lookup"><span data-stu-id="3d227-115">46</span></span>|<span data-ttu-id="3d227-116">Desvío rápido (EF)</span><span class="sxs-lookup"><span data-stu-id="3d227-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="3d227-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="3d227-117">Video</span></span>| <span data-ttu-id="3d227-118">50 020 – 50 039</span><span class="sxs-lookup"><span data-stu-id="3d227-118">50,020–50,039</span></span>|<span data-ttu-id="3d227-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3d227-119">TCP/UDP</span></span>|<span data-ttu-id="3d227-120">34</span><span class="sxs-lookup"><span data-stu-id="3d227-120">34</span></span>|<span data-ttu-id="3d227-121">Desvío garantizado (AF41)</span><span class="sxs-lookup"><span data-stu-id="3d227-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="3d227-122">Aplicación/Compartir pantalla</span><span class="sxs-lookup"><span data-stu-id="3d227-122">Application/Screen Sharing</span></span>| <span data-ttu-id="3d227-123">50 040 – 50 059</span><span class="sxs-lookup"><span data-stu-id="3d227-123">50,040–50,059</span></span>|<span data-ttu-id="3d227-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3d227-124">TCP/UDP</span></span>|<span data-ttu-id="3d227-125">18</span><span class="sxs-lookup"><span data-stu-id="3d227-125">18</span></span>|<span data-ttu-id="3d227-126">Desvío garantizado (AF21)</span><span class="sxs-lookup"><span data-stu-id="3d227-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="3d227-127">Siempre que sea posible, configure la configuración de QoS basada en directivas dentro de un objeto de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="3d227-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="3d227-128">Los pasos siguientes son muy similares a Configurar intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype Empresarial  [Server,](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)que tiene algunos detalles adicionales que pueden no ser necesarios.</span><span class="sxs-lookup"><span data-stu-id="3d227-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="3d227-129">Para crear una directiva de audio de QoS para equipos con Windows 10 unido al dominio, inicie sesión primero en un equipo en el que se haya instalado la administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="3d227-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="3d227-130">Abra Administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en Administración de directivas de grupo) y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3d227-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="3d227-131">En Administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="3d227-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="3d227-132">Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **Clientes,** la nueva directiva debe crearse en la unidad organizativa Clientes.</span><span class="sxs-lookup"><span data-stu-id="3d227-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="3d227-133">Haga clic con el botón derecho en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y Vincule aquí**.</span><span class="sxs-lookup"><span data-stu-id="3d227-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="3d227-134">En el cuadro de diálogo Nuevo **GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="3d227-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="3d227-135">Haga clic con el botón derecho en la directiva recién creada y, a continuación, haga clic **en Editar.**</span><span class="sxs-lookup"><span data-stu-id="3d227-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="3d227-136">En el Editor de administración de directivas de grupo, **expanda** Configuración del equipo, expanda Configuración de **Windows**, haga clic con el botón derecho en **QoS** basado en directivas y, a continuación, haga clic **en Crear nueva directiva.**</span><span class="sxs-lookup"><span data-stu-id="3d227-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="3d227-137">En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el **cuadro** Nombre.</span><span class="sxs-lookup"><span data-stu-id="3d227-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="3d227-138">Seleccione **Especificar valor DSCP** y establezca el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="3d227-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="3d227-139">Deje **especificar la tasa de limitación saliente** no seleccionada y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="3d227-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="3d227-140">En la página siguiente, seleccione Solo aplicaciones con este nombre **ejecutable,** escriba el nombre **Teams.exe** y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="3d227-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="3d227-141">Esta configuración indica a la directiva que solo priorice el tráfico que coincida desde el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d227-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="3d227-142">En la tercera página, asegúrese de que todas las direcciones **IP** de origen y Cualquier dirección **IP** de destino están seleccionadas y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="3d227-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="3d227-143">Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que envió los paquetes y del equipo (dirección IP) que recibirá los paquetes.</span><span class="sxs-lookup"><span data-stu-id="3d227-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="3d227-144">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable Seleccionar el protocolo que se aplica a esta directiva de **QoS.**</span><span class="sxs-lookup"><span data-stu-id="3d227-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="3d227-145">TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados.</span><span class="sxs-lookup"><span data-stu-id="3d227-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="3d227-146">En el encabezado **Especificar el número de puerto de origen,** seleccione Desde este puerto o rango de **origen.**</span><span class="sxs-lookup"><span data-stu-id="3d227-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="3d227-147">En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audio.</span><span class="sxs-lookup"><span data-stu-id="3d227-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="3d227-148">Por ejemplo, si ha reservado los puertos 50000 a los puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="3d227-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="3d227-149">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3d227-149">Click **Finish**.</span></span>

1. <span data-ttu-id="3d227-150">Repita los pasos 5 a 10 para crear directivas para uso compartido de aplicaciones y vídeo, sustituyendo los valores adecuados en los pasos 6 y 10.</span><span class="sxs-lookup"><span data-stu-id="3d227-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="3d227-151">Las nuevas directivas que haya creado no se verán vigentes hasta que se actualice la directiva de grupo en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3d227-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="3d227-152">Aunque la directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3d227-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="3d227-153">En cada equipo para el que quiera actualizar la directiva de grupo, abra un símbolo del sistema como administrador *(Ejecutar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="3d227-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="3d227-154">En el símbolo del sistema, escriba</span><span class="sxs-lookup"><span data-stu-id="3d227-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="3d227-155">Comprobar marcas dscp en el objeto directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="3d227-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="3d227-156">Para comprobar que se han establecido los valores del objeto directiva de grupo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3d227-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="3d227-157">Abrir un símbolo del sistema como administrador *(Ejecutar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="3d227-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="3d227-158">En el símbolo del sistema, escriba</span><span class="sxs-lookup"><span data-stu-id="3d227-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="3d227-159">Esto generará un informe de GPO aplicados y lo enviará a un archivo de texto denominado *gp.txt*.</span><span class="sxs-lookup"><span data-stu-id="3d227-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="3d227-160">Para obtener un informe HTML más legible denominado *gp.html*, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3d227-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="3d227-161">En el archivo generado, busque el título **Objetos** de directiva de grupo aplicados y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente están en la lista de directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3d227-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="3d227-162">Abra el Editor del Registro y vaya a</span><span class="sxs-lookup"><span data-stu-id="3d227-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="3d227-163">Directivas de \_ software HKEY LOCAL \_ MACHINE de Microsoft Windows \\ \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="3d227-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="3d227-164">Compruebe los valores de las entradas del Registro que se muestran en la Tabla 2.</span><span class="sxs-lookup"><span data-stu-id="3d227-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="3d227-165">*Tabla 2. Valores para entradas de registro de Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="3d227-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="3d227-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d227-166">Name</span></span>          |  <span data-ttu-id="3d227-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d227-167">Type</span></span>  |    <span data-ttu-id="3d227-168">Datos</span><span class="sxs-lookup"><span data-stu-id="3d227-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="3d227-169">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3d227-169">Application Name</span></span>    | <span data-ttu-id="3d227-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-170">REG_SZ</span></span> |  <span data-ttu-id="3d227-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="3d227-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="3d227-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="3d227-172">DSCP Value</span></span>       | <span data-ttu-id="3d227-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-173">REG_SZ</span></span> |     <span data-ttu-id="3d227-174">46</span><span class="sxs-lookup"><span data-stu-id="3d227-174">46</span></span>      |
   |        <span data-ttu-id="3d227-175">IP local</span><span class="sxs-lookup"><span data-stu-id="3d227-175">Local IP</span></span>        | <span data-ttu-id="3d227-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="3d227-177">Longitud del prefijo de IP local</span><span class="sxs-lookup"><span data-stu-id="3d227-177">Local IP Prefix Length</span></span> | <span data-ttu-id="3d227-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="3d227-179">Puerto local</span><span class="sxs-lookup"><span data-stu-id="3d227-179">Local Port</span></span>       | <span data-ttu-id="3d227-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-180">REG_SZ</span></span> | <span data-ttu-id="3d227-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="3d227-181">50000-50019</span></span> |
   |        <span data-ttu-id="3d227-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="3d227-182">Protocol</span></span>        | <span data-ttu-id="3d227-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="3d227-184">IP remota</span><span class="sxs-lookup"><span data-stu-id="3d227-184">Remote IP</span></span>        | <span data-ttu-id="3d227-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="3d227-186">Prefijo IP remoto</span><span class="sxs-lookup"><span data-stu-id="3d227-186">Remote IP Prefix</span></span>    | <span data-ttu-id="3d227-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="3d227-188">Puerto remoto</span><span class="sxs-lookup"><span data-stu-id="3d227-188">Remote Port</span></span>       | <span data-ttu-id="3d227-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="3d227-190">Velocidad de limitación</span><span class="sxs-lookup"><span data-stu-id="3d227-190">Throttle Rate</span></span>      | <span data-ttu-id="3d227-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3d227-191">REG_SZ</span></span> |     <span data-ttu-id="3d227-192">-1</span><span class="sxs-lookup"><span data-stu-id="3d227-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="3d227-193">Compruebe que el valor de la entrada Nombre de aplicación es correcto para el cliente que usa y compruebe que las entradas Valor DSCP y Puerto local reflejen la configuración en el objeto Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="3d227-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3d227-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3d227-194">Related topics</span></span>

[<span data-ttu-id="3d227-195">Implementar calidad de servicio (QoS) en Teams</span><span class="sxs-lookup"><span data-stu-id="3d227-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)