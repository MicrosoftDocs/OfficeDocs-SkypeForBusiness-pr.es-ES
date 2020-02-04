---
title: Configuración de los usuarios de prueba y los parámetros de configuración del nodo Monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4f62a-102">Configuración de los usuarios de prueba y la configuración de los nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f62a-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f62a-103">_**Última modificación del tema:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="4f62a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="4f62a-104">Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f62a-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="4f62a-105">Cree las cuentas de prueba que usarán estos nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="4f62a-106">Si usa el método de autenticación Negotiate, también debe usar el cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) para habilitar estas cuentas de prueba para su uso en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="4f62a-107">Actualizar las opciones de configuración del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="4f62a-108">Esta sección trata:</span><span class="sxs-lookup"><span data-stu-id="4f62a-108">This section covers:</span></span>

  - <span data-ttu-id="4f62a-109">Configuración de las cuentas de usuario de prueba</span><span class="sxs-lookup"><span data-stu-id="4f62a-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="4f62a-110">Configuración de un nodo de monitor básico con las transacciones sintéticas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="4f62a-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="4f62a-111">Configurar pruebas extendidas</span><span class="sxs-lookup"><span data-stu-id="4f62a-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="4f62a-112">Agregar y quitar transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="4f62a-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="4f62a-113">Ver y probar la configuración de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="4f62a-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="4f62a-114">Configuración de las cuentas de usuario de prueba</span><span class="sxs-lookup"><span data-stu-id="4f62a-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="4f62a-115">Los usuarios de prueba no necesitan representar personas reales, pero deben ser cuentas válidas de servicios de dominio de Active Directory; Además, estas cuentas deben estar habilitadas para Lync Server 2013, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="4f62a-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="4f62a-116">Si usa el método de autenticación TrustedServer, todo lo que tiene que hacer es asegurarse de que estas cuentas existen y se han configurado tal y como se especifica aquí.</span><span class="sxs-lookup"><span data-stu-id="4f62a-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="4f62a-117">Debe asignar al menos tres usuarios de prueba para cada grupo que desee probar.</span><span class="sxs-lookup"><span data-stu-id="4f62a-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="4f62a-118">Si usa el método de autenticación Negotiate, también debe usar el cmdlet **set-CsTestUserCredential** y el shell de administración de Lync Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="4f62a-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="4f62a-119">Puede hacerlo ejecutando un comando similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="4f62a-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="4f62a-120">(Estos comandos suponen que las tres cuentas de usuario de Active Directory ya se han creado y que estas cuentas se han habilitado para Lync Server 2013.):</span><span class="sxs-lookup"><span data-stu-id="4f62a-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="4f62a-121">Tenga en cuenta que debe incluir no solo la dirección SIP sino también el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="4f62a-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="4f62a-122">Si no incluye la contraseña establecida, CsTestUserCredential le pedirá que introduzca esa información.</span><span class="sxs-lookup"><span data-stu-id="4f62a-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="4f62a-123">El nombre de usuario se puede especificar con el formato\\de nombre de usuario del nombre de usuario que se muestra arriba o usando el formato de usuario Name@domain nombre; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f62a-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="4f62a-124">Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4f62a-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="4f62a-125">Se debe devolver información similar a la siguiente para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="4f62a-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="4f62a-126">Configuración de un nodo de monitor básico con las transacciones sintéticas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="4f62a-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="4f62a-127">Después de que se hayan creado los usuarios de prueba, puede crear un nodo de monitor con un comando parecido a este:</span><span class="sxs-lookup"><span data-stu-id="4f62a-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="4f62a-128">Este comando crea un nodo de monitor nuevo que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="4f62a-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="4f62a-129">El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4f62a-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="4f62a-130">Si el nodo de monitor usa la autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f62a-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="4f62a-131">Si el nodo de monitor usa el método de autenticación Negotiate, también debe habilitar estas cuentas de usuario para el nodo de monitor mediante el cmdlet **set-CsTestUserCredential** .</span><span class="sxs-lookup"><span data-stu-id="4f62a-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="4f62a-132">Configurar pruebas extendidas</span><span class="sxs-lookup"><span data-stu-id="4f62a-132">Configuring Extended Tests</span></span>

<span data-ttu-id="4f62a-133">Si desea habilitar la red de telefonía pública conmutada (prueba RTC), que verifica la conectividad con la red de telefonía pública conmutada, tendrá que realizar cierta configuración adicional al configurar el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="4f62a-134">En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC.</span><span class="sxs-lookup"><span data-stu-id="4f62a-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="4f62a-135">Para ello, ejecute un comando similar a este desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4f62a-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="4f62a-136">Tenga en cuenta que los resultados de este comando deben almacenarse en una variable.</span><span class="sxs-lookup"><span data-stu-id="4f62a-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="4f62a-137">En este ejemplo, esa es una variable denominada $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="4f62a-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="4f62a-138">En este punto, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4f62a-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="4f62a-139">Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, agregando los tres usuarios de prueba que se crearon previamente y también agregando el tipo de prueba RTC:</span><span class="sxs-lookup"><span data-stu-id="4f62a-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="4f62a-140">Tenga en cuenta que el comando anterior fallará si no ha instalado los archivos principales de Lync Server y la base de datos RTCLocal en el equipo del nodo de supervisor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="4f62a-141">Para probar varias directivas de voz, debe crear una prueba extendida para cada Directiva mediante el cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="4f62a-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="4f62a-142">Los usuarios asignados a esta prueba deben estar configurados con las directivas de voz deseadas.</span><span class="sxs-lookup"><span data-stu-id="4f62a-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="4f62a-143">Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f62a-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="4f62a-144">Si se llama New-CsWatcherNodeConfiguration sin usar el parámetro tests, significa que solo las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) se habilitarán para el nuevo nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="4f62a-145">Esto significa que el nodo de monitor probará los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="4f62a-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="4f62a-146">Registration</span><span class="sxs-lookup"><span data-stu-id="4f62a-146">Registration</span></span>

  - <span data-ttu-id="4f62a-147">IM</span><span class="sxs-lookup"><span data-stu-id="4f62a-147">IM</span></span>

  - <span data-ttu-id="4f62a-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="4f62a-148">GroupIM</span></span>

  - <span data-ttu-id="4f62a-149">P2PAV (sesiones de audio/vídeo punto a punto)</span><span class="sxs-lookup"><span data-stu-id="4f62a-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="4f62a-150">AvConference (audio/conferencia)</span><span class="sxs-lookup"><span data-stu-id="4f62a-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="4f62a-151">Presence</span><span class="sxs-lookup"><span data-stu-id="4f62a-151">Presence</span></span>

  - <span data-ttu-id="4f62a-152">ABS (servicio de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="4f62a-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="4f62a-153">ABWQ (servicio web de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="4f62a-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="4f62a-154">PSTN (llamadas de puerta de enlace RTC, especificadas como una prueba extendida).</span><span class="sxs-lookup"><span data-stu-id="4f62a-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="4f62a-155">De forma predeterminada, la RTC está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4f62a-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="4f62a-156">En este caso, la prueba solo está habilitada porque el comando habilitó la RTC con el parámetro ExtendedTests).</span><span class="sxs-lookup"><span data-stu-id="4f62a-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="4f62a-157">Esto también significa que los siguientes componentes no se probarán de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="4f62a-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="4f62a-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="4f62a-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="4f62a-159">MCXP2PIM (mensajería instantánea para dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="4f62a-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="4f62a-160">ExumConnectivity (mensajería unificada de Exchange)</span><span class="sxs-lookup"><span data-stu-id="4f62a-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="4f62a-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="4f62a-161">JoinLauncher</span></span>

  - <span data-ttu-id="4f62a-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="4f62a-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="4f62a-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="4f62a-163">DataConference</span></span>

  - <span data-ttu-id="4f62a-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="4f62a-164">XmppIM</span></span>

  - <span data-ttu-id="4f62a-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="4f62a-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="4f62a-166">Agregar y quitar transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="4f62a-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="4f62a-167">Una vez que se ha configurado un nodo de monitor, puede usar el cmdlet **set-CsWatcherNodeConfiguration** para agregar o quitar las transacciones sintéticas del nodo.</span><span class="sxs-lookup"><span data-stu-id="4f62a-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="4f62a-168">Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f62a-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="4f62a-169">Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas.</span><span class="sxs-lookup"><span data-stu-id="4f62a-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="4f62a-170">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f62a-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="4f62a-171">Tenga en cuenta que se producirá un error si una o más de estas pruebas (por ejemplo, congresos) ya se han habilitado en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="4f62a-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="4f62a-172">En este caso, aparecerá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f62a-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="4f62a-173">Cuando se produce este error, no se aplica ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="4f62a-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="4f62a-174">Se debe volver a ejecutar el comando con la prueba duplicada eliminada.</span><span class="sxs-lookup"><span data-stu-id="4f62a-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="4f62a-175">Para quitar una transacción sintética de un nodo de monitor, use el método Remove en lugar del método Add.</span><span class="sxs-lookup"><span data-stu-id="4f62a-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="4f62a-176">Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:</span><span class="sxs-lookup"><span data-stu-id="4f62a-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="4f62a-177">También puede usar el método replace para reemplazar todas las pruebas habilitadas actualmente con una o más pruebas nuevas.</span><span class="sxs-lookup"><span data-stu-id="4f62a-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="4f62a-178">Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba de mi, puede configurarlo con este comando:</span><span class="sxs-lookup"><span data-stu-id="4f62a-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="4f62a-179">Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas en el nodo de monitor especificado, excepto para la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="4f62a-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="4f62a-180">Ver y probar la configuración de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="4f62a-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="4f62a-181">Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="4f62a-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="4f62a-182">El comando anterior devolverá información similar a la siguiente, en función de las transacciones sintéticas que se hayan asignado al nodo:</span><span class="sxs-lookup"><span data-stu-id="4f62a-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="4f62a-183">Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="4f62a-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="4f62a-184">Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" | Select-Object-pruebas ExpandProperty | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="4f62a-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="4f62a-185">Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4f62a-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="4f62a-186">Recibirá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f62a-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="4f62a-187">Para comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4f62a-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="4f62a-188">El comando anterior probará cada nodo de monitor de la implementación y le informará de si:</span><span class="sxs-lookup"><span data-stu-id="4f62a-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="4f62a-189">Se ha instalado el rol de registrador requerido.</span><span class="sxs-lookup"><span data-stu-id="4f62a-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="4f62a-190">Cuando ejecutó Set-CsWatcherNodeConfiguration, se creó la clave de registro requerida.</span><span class="sxs-lookup"><span data-stu-id="4f62a-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="4f62a-191">Los servidores ejecutan la versión correcta de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f62a-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="4f62a-192">Tus puertos se han configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f62a-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="4f62a-193">Los usuarios de prueba asignados tienen las credenciales necesarias.</span><span class="sxs-lookup"><span data-stu-id="4f62a-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

