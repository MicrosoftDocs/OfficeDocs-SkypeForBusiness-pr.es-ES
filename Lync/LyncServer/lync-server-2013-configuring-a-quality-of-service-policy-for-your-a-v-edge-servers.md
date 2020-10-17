---
title: Configuración de una directiva de calidad de servicio para los servidores perimetrales A/V
description: Configurar una directiva de calidad de servicio para los servidores perimetrales A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec1f012260aa32df984925a86882a3201e07db0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560476"
---
# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="5f37b-103">Configurar una directiva de calidad de servicio para los servidores perimetrales A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f37b-103">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f37b-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5f37b-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5f37b-105">Además de crear directivas de QoS para los servidores de conferencia, aplicación y mediación, también debe crear directivas de audio y vídeo para el lado interno de sus servidores perimetrales A/V.</span><span class="sxs-lookup"><span data-stu-id="5f37b-105">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="5f37b-106">Sin embargo, las directivas usadas en los servidores perimetrales son diferentes de las que se usan en los servidores de conferencia, aplicación y mediación.</span><span class="sxs-lookup"><span data-stu-id="5f37b-106">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="5f37b-107">Para los servidores de conferencia, aplicación y mediación especifica un intervalo de puertos de origen; con los servidores perimetrales, debe especificar un intervalo de puertos de destino.</span><span class="sxs-lookup"><span data-stu-id="5f37b-107">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="5f37b-108">Debido a que no puede simplemente aplicar las directivas QoS del servidor de conferencia, aplicación y mediación a los servidores perimetrales: estas directivas simplemente no funcionan.</span><span class="sxs-lookup"><span data-stu-id="5f37b-108">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="5f37b-109">En su lugar, debe crear nuevas directivas y aplicar dichas directivas solo a los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="5f37b-109">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="5f37b-110">El siguiente procedimiento describe el proceso para crear objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad de servicio en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="5f37b-110">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="5f37b-111">Por supuesto, es posible que los servidores perimetrales sean servidores independientes que no tengan cuentas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f37b-111">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="5f37b-112">Si ese es el caso, puede usar la Directiva de grupo local en lugar de la Directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales con el editor de directivas de grupo local y debe crear de forma individual el mismo conjunto de directivas en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5f37b-112">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="5f37b-113">Para iniciar el editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f37b-113">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="5f37b-114">Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-114">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5f37b-115">En el cuadro de diálogo **Ejecutar** , escriba **gpedit. msc** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="5f37b-115">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="5f37b-116">Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="5f37b-116">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="5f37b-117">En ese caso, abra Administración de directivas de grupo (haga clic en **Inicio**, elija **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5f37b-117">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="5f37b-118">En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="5f37b-118">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="5f37b-119">Por ejemplo, si todos los equipos de Lync Server están ubicados en una unidad organizativa llamada Lync Server, la nueva Directiva debe crearse en la unidad organizativa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f37b-119">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="5f37b-120">Haga clic con el botón secundario en el contenedor que corresponda y, después, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-120">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="5f37b-121">En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Audio Lync Server**) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-121">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="5f37b-122">Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-122">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="5f37b-123">Desde aquí, el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:</span><span class="sxs-lookup"><span data-stu-id="5f37b-123">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="5f37b-124">En el editor de administración de directivas de grupo o el editor de directivas de grupo local, expanda **configuración del equipo**, **directivas**, **configuración de Windows**, haga clic con el botón secundario en **QoS basada en Directiva**y, a continuación, haga clic en **crear nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-124">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="5f37b-p105">En el cuadro de diálogo **QoS basada en directivas**, en la página que se abre, escriba un nombre para la nueva directiva (p. ej., **Audio Lync Server**) en el cuadro **Nombre**. Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje desactivada la casilla **Especificar velocidad de salida del acelerador** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="5f37b-p106">En la página siguiente, compruebe que la opción **Todas las aplicaciones** está seleccionada y haga clic en **Siguiente**. Esta configuración indica a la red que busque todos los paquetes con el valor 46 para DSCP, y no solo los paquetes creados por una aplicación en particular.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="5f37b-p107">En la tercera página, compruebe que las opciones **Cualquier dirección IP de origen** y **Cualquier dirección IP de destino** están seleccionadas y haga clic en **Siguiente**. Estas dos opciones garantizan que se gestionarán todos los paquetes, sin tener en cuenta el equipo (o dirección IP) que los envió y el equipo (o dirección IP) que los recibirá.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="5f37b-132">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-132">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="5f37b-133">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="5f37b-133">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="5f37b-134">En el encabezado **especifique el número de puerto de destino**, seleccione **desde este intervalo o puerto de destino**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-134">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="5f37b-135">En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio.</span><span class="sxs-lookup"><span data-stu-id="5f37b-135">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="5f37b-136">Por ejemplo, si ha reservado los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-136">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="5f37b-137">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-137">Click **Finish**.</span></span>

<span data-ttu-id="5f37b-138">Una vez que haya creado la directiva QoS para el tráfico de audio, debe crear una segunda Directiva para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5f37b-138">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="5f37b-139">Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f37b-139">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="5f37b-140">Utilice un nombre de directiva diferente (y único) (por ejemplo, **Vídeo Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="5f37b-140">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="5f37b-p111">Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)</span><span class="sxs-lookup"><span data-stu-id="5f37b-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="5f37b-144">Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5f37b-144">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="5f37b-145">Por ejemplo, si ha reservado los puertos del 57501 al 65535 para el vídeo, establezca el intervalo de puertos así: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-145">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="5f37b-146">De nuevo, debe configurarse como el intervalo de puertos de destino.</span><span class="sxs-lookup"><span data-stu-id="5f37b-146">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="5f37b-147">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, sustituyendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f37b-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="5f37b-148">Utilice un nombre de directiva diferente (y único) (por ejemplo, **Uso compartido de aplicaciones Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="5f37b-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="5f37b-p113">Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)</span><span class="sxs-lookup"><span data-stu-id="5f37b-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="5f37b-p114">Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 40803 al 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos así: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="5f37b-154">Las nuevas directivas que ha creado no tendrán efecto hasta que la Directiva de grupo se haya actualizado en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="5f37b-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="5f37b-155">Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="5f37b-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="5f37b-156">Este comando se puede ejecutar desde dentro de Lync Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="5f37b-156">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="5f37b-157">Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="5f37b-158">Tenga en cuenta que es posible que tenga que reiniciar el servidor perimetral incluso después de ejecutar Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="5f37b-158">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="5f37b-159">Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5f37b-159">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="5f37b-160">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-160">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5f37b-161">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="5f37b-161">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="5f37b-162">En el editor del registro, expanda el \*\* \_ \_ equipo local HKEY\*\*, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-162">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5f37b-p117">Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5f37b-p118">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de que se cree un nuevo valor del Registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5f37b-p119">Haga clic con el botón secundario en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Información del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5f37b-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="5f37b-169">Cierre el Editor del Registro y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="5f37b-169">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

