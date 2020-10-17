---
title: 'Lync Server 2013: configurar directivas de calidad de servicio para clientes que ejecutan Windows 7 o Windows 8'
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
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534977"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="3dc5a-102">Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que ejecutan Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="3dc5a-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dc5a-103">_**Última modificación del tema:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="3dc5a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="3dc5a-104">Además de especificar intervalos de puertos para su uso por parte de los clientes de Lync, también debe crear directivas de calidad de servicio independientes que se aplicarán a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="3dc5a-105">(Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Lync 2013 y Windows 7 o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="3dc5a-106">En el ejemplo siguiente utiliza este conjunto de intervalos de puertos para crear una directiva de audio y una directiva de vídeo:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dc5a-107">Tipo de tráfico de cliente</span><span class="sxs-lookup"><span data-stu-id="3dc5a-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="3dc5a-108">Puerto inicial</span><span class="sxs-lookup"><span data-stu-id="3dc5a-108">Port Start</span></span></th>
<th><span data-ttu-id="3dc5a-109">Intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="3dc5a-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dc5a-110">Audio</span><span class="sxs-lookup"><span data-stu-id="3dc5a-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-111">50020</span><span class="sxs-lookup"><span data-stu-id="3dc5a-111">50020</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-112">20</span><span class="sxs-lookup"><span data-stu-id="3dc5a-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dc5a-113">Vídeo</span><span class="sxs-lookup"><span data-stu-id="3dc5a-113">Video</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-114">58000</span><span class="sxs-lookup"><span data-stu-id="3dc5a-114">58000</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-115">20</span><span class="sxs-lookup"><span data-stu-id="3dc5a-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dc5a-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3dc5a-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-117">42000</span><span class="sxs-lookup"><span data-stu-id="3dc5a-117">42000</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-118">20</span><span class="sxs-lookup"><span data-stu-id="3dc5a-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dc5a-119">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="3dc5a-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-120">42020</span><span class="sxs-lookup"><span data-stu-id="3dc5a-120">42020</span></span></p></td>
<td><p><span data-ttu-id="3dc5a-121">20</span><span class="sxs-lookup"><span data-stu-id="3dc5a-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3dc5a-122">Para crear una directiva de audio de calidad de servicio para equipos con Windows 7 o Windows 8, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="3dc5a-123">Abra la Administración de directivas de grupo (haga clic en **Inicio**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complemente el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="3dc5a-p103">En la Administración de directivas de grupo, busque el contenedor en el que se deba crear la nueva directiva. Por ejemplo, si todos los equipos cliente están ubicados en una OU denominada Clientes, la nueva directiva se deberá crear en la OU Clientes.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p103">In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="3dc5a-126">Haga clic con el botón secundario en el contenedor apropiado y, a continuación, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="3dc5a-127">En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Lync Audio**) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="3dc5a-128">Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="3dc5a-129">En el Editor de la Administración de directivas de grupo, expanda **Configuración de equipo**, expanda **Directivas**, expanda **Configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas** y, a continuación, haga clic en **Crear nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="3dc5a-p104">En el cuadro de diálogo **QoS basada en directivas**, en la página de inicio, escriba un nombre para la directiva nueva (por ejemplo, **Lync Audio**) en el cuadro **Nombre**. Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p104">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="3dc5a-133">En la página siguiente, seleccione **sólo aplicaciones con este nombre de archivo ejecutable** y escriba el nombre **Lync.exe**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="3dc5a-134">Esta configuración le indica a la Directiva que solo Asigne prioridades de tráfico que coincidan con el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="3dc5a-p106">En la tercera página, compruebe que las opciones **Cualquier dirección IP de origen** y **Cualquier dirección IP de destino** están seleccionadas y haga clic en **Siguiente**. Estas dos opciones garantizan que se gestionarán todos los paquetes, sin tener en cuenta el equipo (o dirección IP) que los envió y el equipo (o dirección IP) que los recibirá.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="3dc5a-137">En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="3dc5a-138">TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="3dc5a-p108">En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto asociado, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos de 50020 a 50039 para el tráfico de audio, escriba el intervalo de puertos con el formato: **50020:50039**. Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p108">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="3dc5a-p109">Después de crear la directiva de QoS para audio, deberá crear una segunda directiva para el vídeo. Para ello, siga el mismo procedimiento básico que ha seguido para la directiva de audio, con las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p109">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="3dc5a-145">Use un nombre de directiva diferente (y único), por ejemplo, **Lync Video**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="3dc5a-p110">Ajuste el valor de DSCP en **34**, en lugar de 46. (Como ya se ha mencionado, no tiene que utilizar el valor 34 para DSCP, sino asignar a DSCP un valor diferente al usado para el audio.)</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p110">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="3dc5a-p111">Use el intervalo de puertos para el tráfico de vídeo que ha configurado anteriormente. Por ejemplo, si reservó los puertos de 58000 a 58019 para el vídeo, ajuste el intervalo de puertos del siguiente modo: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p111">Use the previously-configured port range for video traffic. For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="3dc5a-150">Si decide crear una directiva para la administración del tráfico del uso compartido de aplicaciones, realice las siguientes sustituciones:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="3dc5a-151">Use un nombre de directiva diferente (y único), como puede ser **Lync Server Application Sharing**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="3dc5a-p112">Ajuste el valor de DSCP en **24**, en lugar de 46. (También en este caso, este valor no tiene por qué ser 24, sino que debe ser diferente a los valores de DSCP utilizados para el audio y el vídeo.)</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p112">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="3dc5a-p113">Use el intervalo de puertos para el tráfico de vídeo que ha configurado anteriormente. Por ejemplo, si reservó los puertos de 42000 a 42019 para el uso compartido de aplicaciones, ajuste el intervalo de puertos del siguiente modo: **42019:42000**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p113">Use the previously-configured port range for video traffic. For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="3dc5a-156">Para una directiva de transferencia de archivos:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="3dc5a-157">Use un nombre de directiva diferente (y único), como puede ser **Lync Server File Transfer**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="3dc5a-p114">Ajuste el valor de DSCP en **14**. (Una vez más, este valor no tiene por qué ser 14, sino simplemente un código DSCP único.)</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p114">Set the DSCP value to **14**. (Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="3dc5a-160">Use el intervalo de puertos configurado anteriormente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="3dc5a-161">Por ejemplo, si reservó los puertos de 42020 a 42039 para el uso compartido de aplicaciones, ajuste el intervalo de puertos del siguiente modo: **42039:42020**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="3dc5a-p116">Las directivas nuevas que ha creado no tendrán efecto hasta que se actualice Directiva de grupos en los equipos cliente. Aunque la Directiva de grupos se actualiza periódicamente de forma automática, puede forzar una actualización inmediata ejecutando el siguiente comando en todos los equipos en los que es necesario actualizar la Directiva de grupos:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p116">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="3dc5a-p117">Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comando con las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p117">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="3dc5a-166">Recuerde que estas directivas deben ir dirigidas a los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="3dc5a-167">No se deben aplicar a los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="3dc5a-168">Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="3dc5a-169">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="3dc5a-170">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="3dc5a-171">En el editor del registro, expanda el \*\* \_ \_ equipo local HKEY\*\*, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3dc5a-p119">Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3dc5a-p120">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Cuando se haya creado el nuevo valor de registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre al valor.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3dc5a-p121">Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p121">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="3dc5a-178">Cierre el Editor del Registro y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="3dc5a-179">Configuración de la Calidad de servicio en equipos con varios adaptadores de red</span><span class="sxs-lookup"><span data-stu-id="3dc5a-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="3dc5a-p122">Si tiene un equipo con varios adaptadores de red, habrá ocasiones en las que los valores DSCP se muestren como 0x00, en lugar del valor configurado. Esto ocurrirá, generalmente, en equipos en los que uno o más adaptadores de red no pueden acceder al dominio de Active Directory (por ejemplo, si estos adaptadores de red se utilizan para una red privada). En esos casos, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p122">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value. This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network). In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="3dc5a-p123">Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro. Para ello:</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p123">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry. That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="3dc5a-185">Haga clic en **Inicio** y, a continuación, en \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="3dc5a-186">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="3dc5a-187">En el editor del registro, expanda el \*\* \_ \_ equipo local HKEY\*\*, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="3dc5a-p124">Si no ve una clave de registro con la etiqueta **QoS**, haga clic con el botón secundario en **Tcpip**, seleccione **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la clave nueva, escriba **QoS** y pulse ENTRAR para cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p124">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**. After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="3dc5a-p125">Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Cuando se haya creado el nuevo valor de registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre al valor.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="3dc5a-p126">Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos del valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-p126">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="3dc5a-194">Después de crear y configurar el nuevo valor de registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="3dc5a-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

