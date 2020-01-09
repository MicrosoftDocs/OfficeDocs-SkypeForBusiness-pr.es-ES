---
title: Configurar los usuarios y las opciones de configuración de la prueba del nodo de monitor
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: configurar las opciones de las cuentas de usuario y del nodo de monitor para las transacciones sintéticas de Skype empresarial Server.'
ms.openlocfilehash: 991b78a4581d616e79aaa4f096a76aad8636b632
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989035"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="90df2-103">Configurar los usuarios y las opciones de configuración de la prueba del nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="90df2-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="90df2-104">**Resumen:** Configure las cuentas de usuario y la configuración del nodo de monitor para las transacciones sintéticas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="90df2-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="90df2-105">Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90df2-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="90df2-106">[Configure las cuentas de usuario de prueba](test-users-and-settings-2019.md#testuser) que usarán estos nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="90df2-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="90df2-107">Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="90df2-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="90df2-108">Actualizar las opciones de configuración del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="90df2-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="90df2-109">Configurar cuentas de usuario de prueba</span><span class="sxs-lookup"><span data-stu-id="90df2-109">Configure Test User Accounts</span></span>
<span data-ttu-id="90df2-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="90df2-110"></span></span>

<span data-ttu-id="90df2-111">Las cuentas de prueba no necesitan representar personas reales, pero deben ser cuentas de Active Directory válidas.</span><span class="sxs-lookup"><span data-stu-id="90df2-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="90df2-112">Además, estas cuentas deben estar habilitadas para Skype empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="90df2-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="90df2-113">Si está usando el método de autenticación TrustedServer, solamente debe asegurarse de que estas cuentas existen y configurarlas como se ha indicado.</span><span class="sxs-lookup"><span data-stu-id="90df2-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="90df2-114">Debe asignar al menos tres usuarios de prueba para cada grupo que desee probar.</span><span class="sxs-lookup"><span data-stu-id="90df2-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="90df2-115">Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el shell de administración de Skype empresarial Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="90df2-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="90df2-116">Para ello, ejecute un comando similar al siguiente (estos comandos suponen que se han creado las tres cuentas de usuario de Active Directory y que estas cuentas están habilitadas para Skype empresarial Server):</span><span class="sxs-lookup"><span data-stu-id="90df2-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="90df2-p104">Debe incluir no solo la dirección SIP, sino también el nombre de usuario y una contraseña. Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que la escriba. El nombre de usuario se pueden especificar con el formato nombre de dominio\nombre de usuario que se muestra en el bloque de código anterior.</span><span class="sxs-lookup"><span data-stu-id="90df2-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="90df2-120">Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="90df2-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="90df2-121">Se debería devolver información similar a la siguiente para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="90df2-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="90df2-122">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="90df2-122">**UserName**</span></span>|<span data-ttu-id="90df2-123">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="90df2-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90df2-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="90df2-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="90df2-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="90df2-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="90df2-126">Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="90df2-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="90df2-127">Una vez creados los usuarios, puede crear un nodo de monitor con un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="90df2-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="90df2-p105">Este comando crea un nodo de monitor nuevo que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Skype Empresarial Server. Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor con el cmdlet Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="90df2-p105">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions. The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com. If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server. If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="90df2-132">Para validar que la detección automática de grupo de servidores de destino para el inicio de sesión se ha configurado correctamente en lugar de que esté destinado a un grupo directamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="90df2-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="90df2-133">Configurar pruebas extendidas</span><span class="sxs-lookup"><span data-stu-id="90df2-133">Configuring Extended Tests</span></span>

<span data-ttu-id="90df2-p106">Si desea habilitar la prueba de RTC, que comprueba la conectividad con la red telefónica pública conmutada, debe realizar tareas de configuración adicionales al establecer el nodo de monitor. En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC ejecutando un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="90df2-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="90df2-p107">Tenga en cuenta que los resultados de este comando se deben almacenar en una variable. En este ejemplo, se trata de una variable denominada $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="90df2-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="90df2-138">A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="90df2-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="90df2-139">Por ejemplo, en el siguiente comando se crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, y se agregan los tres usuarios de prueba que se crearon anteriormente y también el tipo de prueba RTC:</span><span class="sxs-lookup"><span data-stu-id="90df2-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="90df2-140">Tenga en cuenta que el comando anterior no se ejecutará correctamente si no instaló los archivos principales de Skype Empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="90df2-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="90df2-p109">Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest**. Los usuarios siempre se deben configurar con las directivas de voz deseadas. Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** con delimitadores de coma, como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="90df2-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="90df2-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="90df2-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="90df2-p110">Dado que el cmdlet **New-CsWatcherNodeConfiguration** se ha invocado sin usar el parámetro Tests, para el nodo de monitor solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada). Por lo tanto, el nodo de monitor probará estos componentes:</span><span class="sxs-lookup"><span data-stu-id="90df2-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="90df2-147">Registration</span><span class="sxs-lookup"><span data-stu-id="90df2-147">Registration</span></span>
    
- <span data-ttu-id="90df2-148">IM</span><span class="sxs-lookup"><span data-stu-id="90df2-148">IM</span></span>
    
- <span data-ttu-id="90df2-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="90df2-149">GroupIM</span></span>
    
- <span data-ttu-id="90df2-150">P2PAV (sesiones de audio/vídeo punto a punto)</span><span class="sxs-lookup"><span data-stu-id="90df2-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="90df2-151">AvConference (audio/conferencia)</span><span class="sxs-lookup"><span data-stu-id="90df2-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="90df2-152">Presence</span><span class="sxs-lookup"><span data-stu-id="90df2-152">Presence</span></span>
    
- <span data-ttu-id="90df2-153">ABS (servicio de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="90df2-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="90df2-154">ABWQ (servicio web de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="90df2-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="90df2-155">Los siguientes componentes no se probarán de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="90df2-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="90df2-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="90df2-156">ASConference</span></span>
    
- <span data-ttu-id="90df2-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="90df2-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="90df2-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="90df2-158">DataConference</span></span>
    
- <span data-ttu-id="90df2-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="90df2-159">DialinConferencing</span></span>
    
- <span data-ttu-id="90df2-160">ExumConnectivity (mensajería unificada de Exchange)</span><span class="sxs-lookup"><span data-stu-id="90df2-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="90df2-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="90df2-161">JoinLauncher</span></span>
    
- <span data-ttu-id="90df2-162">MCXP2PIM (mensajería instantánea de dispositivos móviles heredados)</span><span class="sxs-lookup"><span data-stu-id="90df2-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="90df2-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="90df2-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="90df2-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="90df2-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="90df2-165">PSTN (llamadas de puerta de enlace RTC, especificadas como una prueba extendida)</span><span class="sxs-lookup"><span data-stu-id="90df2-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="90df2-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="90df2-166">UcwaConference</span></span>
    
- <span data-ttu-id="90df2-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="90df2-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="90df2-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="90df2-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="90df2-169">Agregar y quitar transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="90df2-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="90df2-p111">Una vez configurado el nodo de monitor, puede usar el cmdlet Set-CsWatcherNodeConfiguration para agregar o quitar transacciones sintéticas en el nodo. Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="90df2-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="90df2-p112">Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="90df2-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="90df2-p113">Tenga en cuenta que se generará un error si ya se habilitaron una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="90df2-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="90df2-176">Set-CsWatcherNodeConfiguration: hay una secuencia de teclas duplicada 'DataConference' para la clave 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' o restricción de identidad identidad.</span><span class="sxs-lookup"><span data-stu-id="90df2-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="90df2-177">Cuando se produce este error, no se aplica ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="90df2-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="90df2-178">Es necesario volver a ejecutar el comando sin la prueba duplicada.</span><span class="sxs-lookup"><span data-stu-id="90df2-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="90df2-p115">Para quitar una transacción sintética de un nodo de monitor, use el método Remove. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:</span><span class="sxs-lookup"><span data-stu-id="90df2-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="90df2-p116">También puede usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o varias pruebas nuevas. Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba IM, puede configurar esto con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="90df2-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="90df2-183">Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la prueba IM.</span><span class="sxs-lookup"><span data-stu-id="90df2-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="90df2-184">Ver y probar la configuración de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="90df2-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="90df2-185">Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="90df2-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="90df2-186">El comando anterior devolverá información similar a la siguiente, según las transacciones sintéticas que se hayan asignado al nodo:</span><span class="sxs-lookup"><span data-stu-id="90df2-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="90df2-187">Registro de mensajes instantáneos de GroupIM P2PAV AvConference Presence PersistentChatMessage congresos</span><span class="sxs-lookup"><span data-stu-id="90df2-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="90df2-188">Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="90df2-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="90df2-189">Para comprobar que se haya creado un nodo de monitor, escriba el siguiente comando desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="90df2-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="90df2-190">Obtendrá una información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="90df2-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="90df2-191">Identity: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="90df2-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="90df2-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="90df2-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="90df2-193">TargetFqdn: atl-cs-001.litwareinc.com númeroDePuerto: 5061To comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="90df2-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="90df2-194">Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="90df2-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="90df2-195">Se ha instalado el rol de registrador necesario</span><span class="sxs-lookup"><span data-stu-id="90df2-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="90df2-196">Se ha creado la clave de registro necesaria (completado al ejecutar el cmdlet Set-Cs WatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="90df2-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="90df2-197">Los servidores ejecutan la versión correcta de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="90df2-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="90df2-198">Los puertos están bien configurados</span><span class="sxs-lookup"><span data-stu-id="90df2-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="90df2-199">Los usuarios de prueba asignados tienen las credenciales necesarias</span><span class="sxs-lookup"><span data-stu-id="90df2-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="90df2-200">Administración de nodos de monitor</span><span class="sxs-lookup"><span data-stu-id="90df2-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="90df2-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="90df2-201"></span></span>

<span data-ttu-id="90df2-202">Aparte de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **Set-CsWatcherNodeConfiguration**para llevar a cabo otras tareas importantes, como habilitar y deshabilitar el nodo de monitor o configurarlo para que use direcciones URL internas o externas cuando ejecute sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="90df2-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="90df2-p118">De forma predeterminada, los nodos de monitor están diseñadas para ejecutar periódicamente todas sus transacciones sintéticas habilitadas. En ocasiones, sin embargo, es posible que desee suspender esas operaciones. Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red y, a continuación, no hay ningún motivo para ejecutar las transacciones sintéticas. Estas transacciones darán lugar a un error si no hay conectividad de red. Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="90df2-p118">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="90df2-p119">Con este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor atl watcher 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="90df2-p119">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="90df2-p120">La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="90df2-p120">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="90df2-212">Con este comando se elimina toda la configuración de nodo de monitor del equipo en cuestión, lo que evita que se ejecuten transacciones sintéticas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90df2-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="90df2-213">Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos de sistema de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="90df2-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="90df2-p122">Cuando realizan pruebas, los nodos de monitor usan de forma predeterminada las direcciones URL externas de una organización, aunque se pueden configurar para que usen las direcciones URL internas. Esto permite que los administradores comprueben el acceso a la dirección URL de los usuarios de dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebURls en True ($True):</span><span class="sxs-lookup"><span data-stu-id="90df2-p122">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="90df2-218">Restablecer esta propiedad en el valor predeterminado de False ($False) hará que el monitor vuelva a usar las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="90df2-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="90df2-219">Instrucciones de configuración especiales para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="90df2-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="90df2-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="90df2-220"></span></span>

<span data-ttu-id="90df2-p123">La mayor parte de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal cual está. En la mayoría de los casos, en cuanto la transacción sintética se agrega a los valores de configuración del nodo de monitor, el nodo de monitor puede empezar a usar la transacción sintética durante las fases de prueba. Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se indica en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="90df2-p123">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="90df2-224">Transacciones sintéticas de conferencia de datos</span><span class="sxs-lookup"><span data-stu-id="90df2-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="90df2-225">Si el equipo que actúa como nodo de monitor no está en la red perimetral, lo más seguro es que no pueda ejecutar transacciones sintéticas de conferencia de datos, a menos que deshabilite la configuración de proxy del explorador Windows Internet Explorer® para la cuenta de servicio de red siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="90df2-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="90df2-226">En el equipo que actúa como nodo de monitor, haga clic sucesivamente en **Inicio**, **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="90df2-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="90df2-227">En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="90df2-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="90df2-228">Verá el siguiente mensaje que se muestra en la ventana de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="90df2-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="90df2-p124">BITSAdmin está en desuso y no se garantiza que esté disponible en futuras versiones de Windows. Las herramientas de administración para el servicio BITS ahora se proporcionan a través de cmdlets de BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90df2-p124">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="90df2-231">Configuración de proxy para la cuenta NetworkService establecida en NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="90df2-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="90df2-232">(conexión = predeterminada)</span><span class="sxs-lookup"><span data-stu-id="90df2-232">(connection = default)</span></span>
  
<span data-ttu-id="90df2-233">Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="90df2-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="90df2-234">Transacción sintética de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="90df2-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="90df2-235">La transacción sintética de Mensajería unificada de Exchange (UM) comprueba que los usuarios de prueba se pueden conectar a las cuentas de correo de voz hospedadas en Exchange.</span><span class="sxs-lookup"><span data-stu-id="90df2-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="90df2-236">Los usuarios de prueba deben estar configurados previamente con cuentas de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="90df2-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="90df2-237">Transacción sintética de chat persistente</span><span class="sxs-lookup"><span data-stu-id="90df2-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="90df2-238">Para usar la transacción sintética de chat persistente, en primer lugar se debe crear un canal y conceder permiso a los usuarios de prueba para que puedan usarlo.</span><span class="sxs-lookup"><span data-stu-id="90df2-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="90df2-239">Puede usar la transacción sintética de chat persistente para configurar este canal:</span><span class="sxs-lookup"><span data-stu-id="90df2-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="90df2-240">Esta tarea de configuración debe realizarse desde la empresa:</span><span class="sxs-lookup"><span data-stu-id="90df2-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="90df2-241">Si se realiza en un equipo que no es servidor, el usuario que ejecuta el cmdlet debe pertenecer al rol CsPersistentChatAdministrators de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="90df2-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="90df2-242">Si se realiza desde el propio servidor, el usuario que ejecuta el cmdlet debe pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="90df2-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="90df2-243">Transacción sintética de llamada punto a punto de RTC</span><span class="sxs-lookup"><span data-stu-id="90df2-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="90df2-244">La transacción sintética Test-CsPstnPeerToPeerCall confirma que es posible realizar y recibir llamadas a través de la Red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="90df2-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="90df2-245">Para ejecutar esta transacción sintética, se debe configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90df2-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="90df2-246">Dos usuarios de prueba habilitados para UC (el autor y el receptor).</span><span class="sxs-lookup"><span data-stu-id="90df2-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="90df2-247">Números de llamada directa a la extensión (DID) de cada cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="90df2-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="90df2-248">Directivas de VoIP y rutas de voz que permiten que las llamadas al número del receptor lleguen a la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="90df2-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="90df2-249">Una puerta de enlace RTC que acepta llamadas y medios que van a enrutar las llamadas al grupo de servidores principales de un destinatario, según el número marcado.</span><span class="sxs-lookup"><span data-stu-id="90df2-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="90df2-250">Transacción sintética de almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="90df2-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="90df2-251">La transacción sintética de tienda de contactos unificada verifica la capacidad de Skype empresarial Server para recuperar contactos en nombre de un usuario de Exchange.</span><span class="sxs-lookup"><span data-stu-id="90df2-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="90df2-252">Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="90df2-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="90df2-253">Autenticación de servidor a servidor Lyss-Exchange debe estar configurada.</span><span class="sxs-lookup"><span data-stu-id="90df2-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="90df2-254">Los usuarios de prueba deben tener un buzón de Exchange válido.</span><span class="sxs-lookup"><span data-stu-id="90df2-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="90df2-255">Después de que se cumplan estas condiciones, puede ejecutar el siguiente cmdlet de Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:</span><span class="sxs-lookup"><span data-stu-id="90df2-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="90df2-256">El proceso de migración de las listas de contactos de los usuarios de prueba a Exchange puede tardar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="90df2-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="90df2-257">Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca-Setup:</span><span class="sxs-lookup"><span data-stu-id="90df2-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="90df2-258">La ejecución de estas línea de comandos será correcta una vez finalizada la migración.</span><span class="sxs-lookup"><span data-stu-id="90df2-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="90df2-259">Transacción sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="90df2-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="90df2-260">La transacción sintética de mensajería instantánea XMPP (Extensible Messaging and Presence Protocol) requiere que la característica XMPP esté configurada con uno o más dominios federados.</span><span class="sxs-lookup"><span data-stu-id="90df2-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="90df2-261">Para habilitar la transacción sintética XMPP, se debe incluir un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP que pueda enrutarse.</span><span class="sxs-lookup"><span data-stu-id="90df2-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="90df2-262">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="90df2-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="90df2-263">En este ejemplo, tendrá que existir una regla de Skype empresarial Server para enrutar mensajes para litwareinc.com a una puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="90df2-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="90df2-264">Las puertas de enlace y los servidores proxy XMPP estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="90df2-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="90df2-265">Para obtener más información, consulte [migrar la Federación XMPP](../migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="90df2-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="90df2-266">Transacción sintética de Video Interop Server (VIS)</span><span class="sxs-lookup"><span data-stu-id="90df2-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="90df2-267">La transacción sintética del servidor de interoperabilidad de vídeo requiere que descargue e instale los archivos de compatibilidad con transacciones sintéticas ([VISSTSupportPackage. msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="90df2-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="90df2-268">Para instalar VISSTSupportPackage.msi, asegúrese de que las dependencias (en los requisitos del sistema) para el archivo msi ya estén instaladas.</span><span class="sxs-lookup"><span data-stu-id="90df2-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="90df2-269">Ejecute VISSTSupportPackage.msi para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="90df2-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="90df2-270">El archivo. msi instala todos los archivos en la siguiente ruta de acceso: "paquete de compatibilidad con la transacción sintética de%ProgramFiles%\VIS".</span><span class="sxs-lookup"><span data-stu-id="90df2-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="90df2-271">Para obtener más información sobre cómo ejecutar la transacción sintética, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="90df2-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="90df2-272">Cambiar la frecuencia de ejecución para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="90df2-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="90df2-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="90df2-273"></span></span>

<span data-ttu-id="90df2-274">De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="90df2-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="90df2-275">Las transacciones sintéticas se ejecutan de forma secuencial en un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="90df2-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="90df2-276">Se necesita un intervalo más largo para dar tiempo para que finalice todas las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="90df2-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="90df2-277">Si es conveniente ejecutar transacciones sintéticas más a menudo, deberá reducir el número de transacciones sintéticas que se ejecutan con un conjunto de usuarios determinado para que las pruebas puedan completarse en el intervalo de tiempo que desee con un tiempo de margen de flexibilidad para posibles retrasos en la red.</span><span class="sxs-lookup"><span data-stu-id="90df2-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="90df2-278">Si es necesario ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.</span><span class="sxs-lookup"><span data-stu-id="90df2-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="90df2-279">Para cambiar la frecuencia de ejecución de las transacciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="90df2-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="90df2-280">Abra System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="90df2-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="90df2-281">Haga clic en la sección creación.</span><span class="sxs-lookup"><span data-stu-id="90df2-281">Click Authoring section.</span></span> <span data-ttu-id="90df2-282">Haga clic en la sección reglas (en creación)</span><span class="sxs-lookup"><span data-stu-id="90df2-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="90df2-283">En la sección reglas, busque la regla con el nombre "regla principal de colección de rendimiento del Ejecutor de transacciones sintéticas"</span><span class="sxs-lookup"><span data-stu-id="90df2-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="90df2-284">Haga clic con el botón derecho en la regla y seleccione reemplazos, seleccione invalidar la regla y, a continuación, seleccione "para todos los objetos de clase: monitor de grupo"</span><span class="sxs-lookup"><span data-stu-id="90df2-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="90df2-285">En la ventana Propiedades de reemplazo, seleccione nombre de parámetro "frecuencia" y establezca el valor de invalidación en el valor que desee.</span><span class="sxs-lookup"><span data-stu-id="90df2-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="90df2-286">En la misma ventana, seleccione el módulo de administración al que se debe aplicar esta invalidación.</span><span class="sxs-lookup"><span data-stu-id="90df2-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="90df2-287">Uso de registro enriquecido para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="90df2-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="90df2-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="90df2-288"></span></span>

<span data-ttu-id="90df2-289">Las transacciones sintéticas son de gran utilidad para identificar problemas con el sistema.</span><span class="sxs-lookup"><span data-stu-id="90df2-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="90df2-290">Por ejemplo, el cmdlet Test-CsRegistration podría alertar a los administradores sobre posibles problemas de los usuarios para registrarse en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="90df2-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="90df2-291">Sin embargo, puede que se necesiten más detalles para determinar la causa real del error.</span><span class="sxs-lookup"><span data-stu-id="90df2-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="90df2-p133">Por este motivo, las transacciones sintéticas proporcionan registros enriquecidos que, para cada una acciones que lleva a cabo una transacción sintética, registran la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="90df2-p133">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="90df2-294">La hora a la que se inició la actividad.</span><span class="sxs-lookup"><span data-stu-id="90df2-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="90df2-295">La hora a la que finalizó la actividad.</span><span class="sxs-lookup"><span data-stu-id="90df2-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="90df2-296">La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia, iniciar sesión en Skype Empresarial Server o enviar mensaje instantáneo).</span><span class="sxs-lookup"><span data-stu-id="90df2-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="90df2-297">Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="90df2-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="90df2-298">Mensajes de registro SIP.</span><span class="sxs-lookup"><span data-stu-id="90df2-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="90df2-299">Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="90df2-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="90df2-300">Resultado neto de la ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="90df2-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="90df2-p134">Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro. Si está ejecutando manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar la variable de Windows PowerShell en la que se va a almacenar la información. Desde allí, tiene la opción de usar uno de estos dos métodos para guardar y ver mensajes de error en los registros enriquecidos en formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="90df2-p134">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="90df2-304">Para recuperar la información de solución, especifique el parámetro OutLoggerVariable, seguido de un nombre de variable que elija:</span><span class="sxs-lookup"><span data-stu-id="90df2-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="90df2-305">: No anteponga el carácter $ al nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="90df2-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="90df2-306">Use, por ejemplo, el nombre de variable RegistrationTest, no $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="90df2-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="90df2-307">Cuando ejecute este comando, verá una salida similar a esta:</span><span class="sxs-lookup"><span data-stu-id="90df2-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="90df2-308">FQDN de destino: atl-cs-001.litwareinc.com resultado: latencia de error: 00:00:00 mensaje de error: este equipo no tiene ningún certificado asignado.</span><span class="sxs-lookup"><span data-stu-id="90df2-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="90df2-309">Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="90df2-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="90df2-310">Para acceder a esta información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:</span><span class="sxs-lookup"><span data-stu-id="90df2-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="90df2-311">Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="90df2-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="90df2-312">Puede ver estos archivos con Windows Internet Explorer, Microsoft Visual Studio o con cualquier otra aplicación capaz de abrir archivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="90df2-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="90df2-313">Las transacciones sintéticas ejecutadas desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro por si se producen errores.</span><span class="sxs-lookup"><span data-stu-id="90df2-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="90df2-314">Estos registros no se generarán si se produce un error en la ejecución antes de que Skype Empresarial Server PowerShell pueda cargar y ejecutar la transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="90df2-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="90df2-315">De forma predeterminada, Skype empresarial Server guarda los archivos de registro en una carpeta que no está compartida.</span><span class="sxs-lookup"><span data-stu-id="90df2-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="90df2-316">Para que estos registros sean fácilmente accesibles, debe compartir esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="90df2-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="90df2-317">Por ejemplo: \\ATL-watcherer-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="90df2-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
