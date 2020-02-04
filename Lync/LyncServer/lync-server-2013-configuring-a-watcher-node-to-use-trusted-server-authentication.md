---
title: Configurar un nodo de monitor para usar autenticación de servidor de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="8872b-102">Configuración de un nodo de monitor en Lync Server 2013 para usar la autenticación de servidor de confianza</span><span class="sxs-lookup"><span data-stu-id="8872b-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8872b-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8872b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8872b-104">Si el equipo nodo de observador está dentro de la red perimetral, el uso de la autenticación de servidor de confianza puede reducir en gran medida los impuestos de administración para mantener un único certificado en lugar de varias contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="8872b-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="8872b-105">El primer paso para configurar la autenticación de servidor de confianza es crear un grupo de aplicaciones de confianza para hospedar el equipo del nodo de supervisor.</span><span class="sxs-lookup"><span data-stu-id="8872b-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="8872b-106">Una vez creado el grupo de aplicaciones de confianza, debe configurar las transacciones sintéticas en ese nodo de observador para que se ejecuten como una aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="8872b-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8872b-107">Una aplicación de confianza es una aplicación con un estado de confianza que se asigna como parte de Lync Server 2013, pero que no es una parte integrada del producto.</span><span class="sxs-lookup"><span data-stu-id="8872b-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="8872b-108">El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8872b-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="8872b-109">Para crear un grupo de aplicaciones de confianza, abra el shell de administración de Lync Server 2013 y ejecute un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="8872b-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="8872b-110">Para más información sobre los parámetros que se usan en el comando anterior, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8872b-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="8872b-111">Get-Help New-CsTrustedApplicationPool-Full | número</span><span class="sxs-lookup"><span data-stu-id="8872b-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="8872b-112">Después de crear el grupo de aplicaciones de confianza, configure el equipo del nodo de supervisión para que ejecute transacciones sintéticas como aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8872b-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="8872b-113">Esto se realiza mediante el cmdlet **New-CsTrustedApplication** y un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="8872b-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="8872b-114">Cuando se complete el comando anterior y se haya creado la aplicación de confianza, ejecute enable-CsTopology para asegurarse de que los cambios surtan efecto:</span><span class="sxs-lookup"><span data-stu-id="8872b-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="8872b-115">Después de ejecutar enable-CsTopology, le recomendamos que reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="8872b-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="8872b-116">Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8872b-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="8872b-117">Configuración de un certificado predeterminado en el nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="8872b-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="8872b-118">Cada nodo de monitor debe tener un certificado predeterminado asignado mediante el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8872b-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="8872b-119">**Para asignar un certificado predeterminado**</span><span class="sxs-lookup"><span data-stu-id="8872b-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="8872b-120">Haga clic en **Inicio**, seleccione **todos los programas**, **Lync Server**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8872b-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="8872b-121">En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server** y, a continuación, haga clic en **Ejecutar** en la solicitud de encabezado **, instalar o asignar certificado**.</span><span class="sxs-lookup"><span data-stu-id="8872b-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8872b-122">Si el botón <STRONG>Ejecutar</STRONG> está deshabilitado, es posible que primero tenga que hacer clic en <STRONG>Ejecutar</STRONG> en <STRONG>instalar almacén de configuración local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8872b-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="8872b-123">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8872b-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="8872b-124">Si ya tiene un certificado que se puede usar como certificado predeterminado, haga clic en **predeterminado** en el Asistente para certificados y, a continuación, haga clic en **asignar**.</span><span class="sxs-lookup"><span data-stu-id="8872b-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="8872b-125">Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.</span><span class="sxs-lookup"><span data-stu-id="8872b-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="8872b-126">Si necesita solicitar un certificado para usar el certificado predeterminado, haga clic en **solicitar** y, a continuación, siga los pasos del Asistente para solicitud de certificados para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="8872b-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="8872b-127">Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8872b-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="8872b-128">Instalar y configurar un nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="8872b-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="8872b-129">Una vez que haya reiniciado el equipo del nodo de supervisión y haya configurado un certificado, tendrá que ejecutar el archivo Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="8872b-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="8872b-130">(Debe ejecutar Watchernode. msi en un equipo donde estén instalados los dos archivos del agente de Operations Manager y los componentes principales de Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="8872b-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="8872b-131">**Para instalar y configurar un nodo de monitor**</span><span class="sxs-lookup"><span data-stu-id="8872b-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="8872b-132">Abra el shell de administración de Lync Server haciendo clic en **Inicio**, en **todos los programas**, en **Lync Server**y en **consola de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8872b-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8872b-133">En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione Entrar (especifique la ruta de acceso real a su copia de Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="8872b-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8872b-134">También puede ejecutar Watchernode. msi desde una ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="8872b-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="8872b-135">Para abrir una ventana Comandos, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y, a continuación, haga clic en <STRONG>Ejecutar como administrador</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8872b-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="8872b-136">Cuando se abra la ventana de comandos, escriba el mismo comando anterior.</span><span class="sxs-lookup"><span data-stu-id="8872b-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="8872b-137">Tenga en cuenta que el par de nombre y valor en la autenticación de comando anterior = TrustedServer distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8872b-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="8872b-138">Debe escribirla exactamente como se muestra.</span><span class="sxs-lookup"><span data-stu-id="8872b-138">You must type it exactly as shown.</span></span> <span data-ttu-id="8872b-139">Se produce un error en el comando siguiente porque no usa la grafía de letras correcta:</span><span class="sxs-lookup"><span data-stu-id="8872b-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="8872b-140">C:\\herramientas\\Watchernode. msi Authentication = TrustedServer</span><span class="sxs-lookup"><span data-stu-id="8872b-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="8872b-141">Solo puede usar el modo TrustedServer con equipos que se encuentren en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="8872b-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="8872b-142">Cuando un nodo Monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8872b-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

