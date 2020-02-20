---
title: 'Lync Server 2013: configuración de un nodo de monitor para usar la autenticación de credenciales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 473aba5f76d2c48d51b80ec413e003b3fe241d0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="9e5e5-102">Configuración de un nodo de monitor para usar la autenticación de credenciales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e5e5-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e5e5-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9e5e5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9e5e5-p101">Si el equipo del nodo del observador se encuentra fuera de la red perimetral, debe seguir un procedimiento ligeramente diferente para configurar el nodo del observador a fin de que ejecute las transacciones sintéticas. De manera específica, no debe crear un grupo de servidores de aplicaciones de confianza y una aplicación de confianza, y debe instalar un certificado que habilita el nodo del observador para que envíe alertas a un equipo dentro de la red perimetral. Esto significa que tendrá que completar dos tareas independientes:</span><span class="sxs-lookup"><span data-stu-id="9e5e5-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="9e5e5-107">Actualizar la pertenencia al grupo Administradores de solo lectura local de RTC del equipo</span><span class="sxs-lookup"><span data-stu-id="9e5e5-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="9e5e5-108">Instalar los archivos de configuración del nodo del observador</span><span class="sxs-lookup"><span data-stu-id="9e5e5-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="9e5e5-109">Actualización de la pertenencia al grupo Administradores de solo lectura local de RTC</span><span class="sxs-lookup"><span data-stu-id="9e5e5-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="9e5e5-p102">Si su nodo de observador se encuentra fuera de la red perimetral, debe agregar la cuenta del servicio de red al grupo Administradores de solo lectura local de RTC al equipo del nodo de observador. Para ello, complete el siguiente procedimiento en el nodo de observador:</span><span class="sxs-lookup"><span data-stu-id="9e5e5-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="9e5e5-112">Haga clic en  \*\*Inicio \*\*, haga clic con el botón secundario en  \*\*Equipo \*\* y, a continuación, haga clic en  \*\*Administrar \*\*.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="9e5e5-113">En el Administrador de servidores, expanda **Configuración**, **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="9e5e5-114">En el panel Grupos, haga doble clic en **RTC Local Read-only Administrators**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="9e5e5-115">En el cuadro de diálogo **Propiedades de RTC Local Read-only Administrators**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="9e5e5-116">En el cuadro de diálogo para **seleccionar usuarios, equipos, cuentas de servicio o grupos**, haga clic en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="9e5e5-117">En el cuadro de diálogo **Ubicaciones**, seleccione el nombre del equipo del nodo de observador y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="9e5e5-118">En el cuadro **Escribir los nombres de objeto para seleccionar**, escriba **Servicio de red** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="9e5e5-119">En el cuadro de diálogo **Propiedades de RTC Local Read-only Administrators**, haga clic en **Aceptar** y, a continuación, cierre **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="9e5e5-120">Reinicie el equipo del nodo de observador.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="9e5e5-121">Instalación de los archivos de configuración del nodo de observador</span><span class="sxs-lookup"><span data-stu-id="9e5e5-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="9e5e5-122">Una vez se ha iniciado el equipo del nodo de observador, el siguiente paso es ejecutar el archivo Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="9e5e5-123">Para ejecutar este archivo, abra el shell de administración de Lync Server 2013 haciendo clic en **Inicio**, en **todos los programas**, en **Lync Server 2013**y, a continuación, en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="9e5e5-124">En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione Entrar (Asegúrese de especificar la ruta de acceso real a su copia de Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="9e5e5-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="9e5e5-p104">Como se ha descrito con anterioridad, Watchernode.msi también se puede ejecutar desde una ventana de comando. Para abrir una ventana de comando, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y, a continuación, haga clic en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana del comando, escriba el mismo comando que se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="9e5e5-128">El modo Negotiate se usa en cualquier momento que el nodo de observador no se puede configurar como un grupo de servidores de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="9e5e5-129">En este modo, los administradores tendrá que administrar contraseñas de usuario de prueba en el nodo de observador.</span><span class="sxs-lookup"><span data-stu-id="9e5e5-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

