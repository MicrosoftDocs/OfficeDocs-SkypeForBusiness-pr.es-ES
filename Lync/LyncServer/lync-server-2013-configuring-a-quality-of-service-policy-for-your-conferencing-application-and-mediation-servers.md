---
title: 'Lync Server 2013: configuración de una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4711c618669a8fe47a877b4adeafe7759564855f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="8feea-102">Configuración de una directiva de calidad de servicio en Lync Server 2013 para los servidores de conferencia, aplicación y mediación</span><span class="sxs-lookup"><span data-stu-id="8feea-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8feea-103">_**Última modificación del tema:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="8feea-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="8feea-p101">Configurar intervalos de puertos facilita el uso de Calidad de servicio, al hacer que todo el tráfico de un determinado tipo (por ejemplo, todo el tráfico de audio) se transmita a través del mismo conjunto de puertos. De este modo, resulta fácil para el sistema identificar y marcar un cierto paquete: si el puerto 49152 está reservado al tráfico de audio, todos los paquetes que se transmiten a través del puerto 49152 se pueden marcar con un código DSCP que indica que se trata de paquetes de audio. A su vez, esto permite a los enrutadores identificar el paquete como un paquete de audio y darle mayor prioridad que a los paquetes sin marcar (por ejemplo, los paquetes que se usan para copiar un archivo de un servidor a otro).</span><span class="sxs-lookup"><span data-stu-id="8feea-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="8feea-107">Sin embargo, el solo hecho de restringir un conjunto de puertos a un tipo específico de tráfico no hace que los paquetes que se transmiten a través de esos puertos se marquen con el código DSCP correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8feea-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="8feea-108">Además de definir intervalos de puertos, debe crear directivas de Calidad de servicio que especifiquen el código DSCP que se debe asociar a cada intervalo de puertos.</span><span class="sxs-lookup"><span data-stu-id="8feea-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="8feea-109">Para Microsoft Lync Server 2013 que normalmente implica la creación de dos directivas: una para el audio y otra para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="8feea-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="8feea-110">Las directivas de calidad de servicio se crean y administran con mayor facilidad mediante la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="8feea-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="8feea-111">(Estas mismas directivas también se pueden crear mediante directivas de seguridad local.</span><span class="sxs-lookup"><span data-stu-id="8feea-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="8feea-112">Sin embargo, esto requiere repetir el mismo procedimiento en todos los equipos.) El conjunto inicial de directivas QoS (uno para el audio y otro para el vídeo) debe aplicarse solo a los equipos con Lync Server que ejecuten el servidor de conferencia, el servidor de aplicaciones y/o los servicios de Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8feea-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="8feea-113">Si todos estos equipos se encuentran en la misma unidad organizativa de Active Directory, simplemente puede asignar el nuevo objeto de directiva de grupo (GPO) a esa unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="8feea-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="8feea-114">Como alternativa, puede realizar otros pasos para dirigir la nueva Directiva a los equipos especificados; por ejemplo, puede poner los equipos adecuados en un grupo de seguridad y, a continuación, usar el filtrado de seguridad de la Directiva de grupo para aplicar el GPO solo a ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8feea-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="8feea-115">Para crear una directiva de Calidad de servicio destinada a la administración de audio, inicie sesión en un equipo donde se haya instalado Administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="8feea-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="8feea-116">Abra la Administración de directivas de grupo (haga clic en **Inicio**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complemente el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="8feea-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="8feea-117">En la Administración de directivas de grupo, busque el contenedor en el que se deba crear la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="8feea-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="8feea-118">Por ejemplo, si todos los equipos de Lync Server están ubicados en una unidad organizativa llamada Lync Server, la nueva Directiva debe crearse en la unidad organizativa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8feea-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="8feea-119">Haga clic con el botón secundario en el contenedor que corresponda y, después, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="8feea-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="8feea-120">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **QoS de Lync Server**) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="8feea-121">Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="8feea-122">En el Editor de administración de directivas de grupo, expanda **Configuración del equipo**, expanda **Directivas**, expanda **Configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas** y, a continuación, haga clic en **Crear nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="8feea-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="8feea-123">En el cuadro de diálogo **QoS basada en directivas** , en la página de inicio, escriba un nombre para la nueva Directiva (por ejemplo, **QoS de Lync Server**) en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="8feea-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="8feea-124">Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**.</span><span class="sxs-lookup"><span data-stu-id="8feea-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="8feea-125">Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8feea-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="8feea-p107">En la siguiente página, asegúrese de que está activado **Todas las aplicaciones** y haga clic en **Siguiente**. Esto sirve, simplemente, para hacer que todas las aplicaciones relacionen los paquetes del intervalo de puertos especificado con el código DSCP especificado.</span><span class="sxs-lookup"><span data-stu-id="8feea-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="8feea-p108">En la tercera página, compruebe que están activados **Cualquier dirección IP de origen y Cualquier dirección IP de destino**, y haga clic en **Siguiente**. Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.</span><span class="sxs-lookup"><span data-stu-id="8feea-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="8feea-130">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**.</span><span class="sxs-lookup"><span data-stu-id="8feea-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="8feea-131">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="8feea-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="8feea-p110">Debajo del encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio. Por ejemplo, si reservó los puertos del 49152 al 57500 para el tráfico de audio, introduzca el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8feea-p111">El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 se utiliza a menudo para marcar paquetes de audio, no es necesario que use DSCP 46 para las comunicaciones de audio. Si ya ha implementado QoS y está usando otro código DSCP para el audio (por ejemplo, DSCP 40), debe configurar la directiva de Calidad de servicio para que utilice el mismo código (es decir, 40 para el audio). Si está implementando Calidad de servicio ahora, se recomienda usar DSCP 46 para el audio, simplemente, porque es el valor que se suele usar para marcar paquetes de audio.</span><span class="sxs-lookup"><span data-stu-id="8feea-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="8feea-p112">Después de crear la directiva de QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo (y, si lo desea, una tercera para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8feea-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="8feea-141">Utilice un nombre de directiva diferente (y único) (por ejemplo, **Vídeo Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="8feea-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="8feea-p113">Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)</span><span class="sxs-lookup"><span data-stu-id="8feea-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="8feea-p114">Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 57501 al 65535 para el vídeo, establezca el intervalo de puertos así: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="8feea-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="8feea-147">Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, sustituyendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8feea-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="8feea-148">Utilice un nombre de directiva diferente (y único) (por ejemplo, **Uso compartido de aplicaciones Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="8feea-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="8feea-p115">Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)</span><span class="sxs-lookup"><span data-stu-id="8feea-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="8feea-p116">Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 40803 al 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos así: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="8feea-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="8feea-154">Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8feea-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="8feea-155">Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="8feea-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="8feea-156">Este comando se puede ejecutar desde dentro del shell de administración de Lync Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="8feea-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="8feea-157">Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8feea-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="8feea-158">Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8feea-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="8feea-159">En un equipo de Lync Server, haga clic en **Inicio** y, después, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8feea-160">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8feea-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8feea-161">En el editor del registro, expanda **equipo**, expanda el **equipo local\_\_HKEY**, expanda **software**, expanda **directivas**, expanda **Microsoft**, expanda **Windows**y, a continuación, haga clic en **QoS**.</span><span class="sxs-lookup"><span data-stu-id="8feea-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="8feea-162">Debajo de **QoS**, debería ver las claves del Registro de cada una de las directivas de QoS que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="8feea-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="8feea-163">Por ejemplo, si ha creado dos nuevas directivas (una llamada QoS de audio de Lync Server y la otra llamada de QoS de Lync Server), debe entradas de registro para QoS de audio de Lync Server y QoS de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8feea-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="8feea-164">Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="8feea-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="8feea-165">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8feea-166">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8feea-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8feea-167">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="8feea-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="8feea-p120">Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="8feea-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="8feea-p121">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Cuando se haya creado el nuevo valor de registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre al valor.</span><span class="sxs-lookup"><span data-stu-id="8feea-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="8feea-p122">Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8feea-p122">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="8feea-174">Cierre el Editor del Registro y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="8feea-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

