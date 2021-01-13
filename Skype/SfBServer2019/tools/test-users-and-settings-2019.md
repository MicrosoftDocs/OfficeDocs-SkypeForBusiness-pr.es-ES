---
title: Configuración de usuarios y opciones de prueba de nodo de monitor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: configure las cuentas de usuario de prueba y las opciones del nodo de monitor para las transacciones sintéticas de Skype Empresarial Server.'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812770"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="57412-103">Configuración de usuarios y opciones de prueba de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="57412-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="57412-104">**Resumen:** Configure las cuentas de usuario de prueba y las opciones del nodo de monitor para las transacciones sintéticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57412-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="57412-105">Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57412-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="57412-106">[Configure las cuentas de usuario de prueba](test-users-and-settings-2019.md#testuser) para que las utilicen estos nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="57412-107">Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="57412-108">Actualizar las opciones de configuración del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="57412-109">Configurar cuentas de usuario de prueba</span><span class="sxs-lookup"><span data-stu-id="57412-109">Configure Test User Accounts</span></span>
<span data-ttu-id="57412-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="57412-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="57412-111">Las cuentas de prueba no necesitan representar personas reales, pero deben ser cuentas válidas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57412-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="57412-112">Además, estas cuentas deben estar habilitadas para Skype Empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para Telefonía IP empresarial (para usar la transacción sintética de Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="57412-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="57412-113">Si usa el método de autenticación TrustedServer, todo lo que necesita hacer es asegurarse de que estas cuentas existen y configurarlas como se indica.</span><span class="sxs-lookup"><span data-stu-id="57412-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="57412-114">Debe asignar al menos tres usuarios de prueba para cada grupo de servidores que desee probar.</span><span class="sxs-lookup"><span data-stu-id="57412-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="57412-115">Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el Shell de administración de Skype Empresarial Server para permitir que estas cuentas de prueba funcionen con las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="57412-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="57412-116">Para ello, ejecute un comando similar al siguiente (estos comandos suponen que se han creado las tres cuentas de usuario de Active Directory y que estas cuentas están habilitadas para Skype Empresarial Server):</span><span class="sxs-lookup"><span data-stu-id="57412-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="57412-117">Debe incluir no solo la dirección SIP, sino también el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="57412-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="57412-118">Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que escriba esa información.</span><span class="sxs-lookup"><span data-stu-id="57412-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="57412-119">El nombre de usuario se puede especificar mediante el formato nombre de dominio #A0 que se muestra en el bloque de código anterior.</span><span class="sxs-lookup"><span data-stu-id="57412-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="57412-120">Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="57412-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="57412-121">Se devolverá información similar a esta para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="57412-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="57412-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="57412-122">**UserName**</span></span>|<span data-ttu-id="57412-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="57412-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57412-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="57412-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="57412-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="57412-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="57412-126">Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="57412-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="57412-127">Una vez creados los usuarios de prueba, puede crear un nodo de monitor mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="57412-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="57412-128">Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="57412-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="57412-129">El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="57412-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="57412-130">Si el nodo de monitor usa autenticación TrustedServer, las tres cuentas de prueba pueden ser cuentas de usuario válidas habilitadas para Active Directory y Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57412-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="57412-131">Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor mediante el cmdlet Set-CsTestUserCredential usuario.</span><span class="sxs-lookup"><span data-stu-id="57412-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="57412-132">Para validar que la detección automática del grupo de destino para iniciar sesión está configurada correctamente en lugar de dirigirse a un grupo directamente, siga estos pasos en su lugar:</span><span class="sxs-lookup"><span data-stu-id="57412-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="57412-133">Configurar pruebas extendidas</span><span class="sxs-lookup"><span data-stu-id="57412-133">Configuring Extended Tests</span></span>

<span data-ttu-id="57412-134">Si desea habilitar la prueba rtc, que comprueba la conectividad con la red telefónica conmutada, debe realizar una configuración adicional al configurar el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="57412-135">En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC ejecutando un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="57412-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="57412-136">Los resultados de este comando deben almacenarse en una variable.</span><span class="sxs-lookup"><span data-stu-id="57412-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="57412-137">En este ejemplo, la variable se denomina $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="57412-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="57412-138">A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57412-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="57412-139">Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo de servidores atl-cs-001.litwareinc.com, agregando los tres usuarios de prueba creados anteriormente y agregando el tipo de prueba RTC:</span><span class="sxs-lookup"><span data-stu-id="57412-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="57412-140">Se producirá un error en el comando anterior si no ha instalado los archivos principales de Skype Empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="57412-141">Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva mediante el cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="57412-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="57412-142">Los usuarios proporcionados deben configurarse con las directivas de voz deseadas.</span><span class="sxs-lookup"><span data-stu-id="57412-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="57412-143">Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** mediante delimitadores de coma, como:</span><span class="sxs-lookup"><span data-stu-id="57412-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="57412-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="57412-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="57412-145">Dado que se llamó al cmdlet **New-CsWatcherNodeConfiguration** sin usar el parámetro Tests, solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) para el nuevo nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="57412-146">Por lo tanto, el nodo de monitor probará los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="57412-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="57412-147">Registro</span><span class="sxs-lookup"><span data-stu-id="57412-147">Registration</span></span>
    
- <span data-ttu-id="57412-148">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="57412-148">IM</span></span>
    
- <span data-ttu-id="57412-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="57412-149">GroupIM</span></span>
    
- <span data-ttu-id="57412-150">P2PAV (sesiones de audio/vídeo punto a punto)</span><span class="sxs-lookup"><span data-stu-id="57412-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="57412-151">AvConference (audio/conferencia)</span><span class="sxs-lookup"><span data-stu-id="57412-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="57412-152">Presencia</span><span class="sxs-lookup"><span data-stu-id="57412-152">Presence</span></span>
    
- <span data-ttu-id="57412-153">ABS (servicio de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="57412-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="57412-154">ABWQ (servicio web de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="57412-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="57412-155">Los siguientes componentes no se probarán de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="57412-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="57412-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="57412-156">ASConference</span></span>
    
- <span data-ttu-id="57412-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="57412-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="57412-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="57412-158">DataConference</span></span>
    
- <span data-ttu-id="57412-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="57412-159">DialinConferencing</span></span>
    
- <span data-ttu-id="57412-160">ExumConnectivity (mensajería unificada de Exchange)</span><span class="sxs-lookup"><span data-stu-id="57412-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="57412-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="57412-161">JoinLauncher</span></span>
    
- <span data-ttu-id="57412-162">MCXP2PIM (mensajería instantánea de dispositivo móvil heredado)</span><span class="sxs-lookup"><span data-stu-id="57412-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="57412-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="57412-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="57412-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="57412-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="57412-165">RTC (llamadas de puerta de enlace RTC, especificadas como prueba extendida)</span><span class="sxs-lookup"><span data-stu-id="57412-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="57412-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="57412-166">UcwaConference</span></span>
    
- <span data-ttu-id="57412-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="57412-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="57412-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="57412-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="57412-169">Agregar y quitar transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="57412-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="57412-170">Una vez configurado el nodo de monitor, puede usar el cmdlet Set-CsWatcherNodeConfiguration para agregar o quitar transacciones sintéticas en el nodo.</span><span class="sxs-lookup"><span data-stu-id="57412-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="57412-171">Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="57412-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="57412-172">Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas.</span><span class="sxs-lookup"><span data-stu-id="57412-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="57412-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57412-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="57412-174">Se producirá un error si ya se ha habilitado una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="57412-175">En este caso, aparecerá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="57412-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="57412-176">Set-CsWatcherNodeConfiguration: hay una secuencia de claves duplicada "DataConference" para la clave "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" o restricción de identidad única.</span><span class="sxs-lookup"><span data-stu-id="57412-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="57412-177">Cuando se produce este error, no se aplica ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="57412-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="57412-178">El comando debe volver a ejecutarse sin la prueba duplicada.</span><span class="sxs-lookup"><span data-stu-id="57412-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="57412-179">Para quitar una transacción sintética de un nodo de monitor, utilice el método Remove.</span><span class="sxs-lookup"><span data-stu-id="57412-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="57412-180">Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:</span><span class="sxs-lookup"><span data-stu-id="57412-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="57412-181">Puedes usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o más pruebas nuevas.</span><span class="sxs-lookup"><span data-stu-id="57412-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="57412-182">Por ejemplo, si desea que un nodo de monitor solo ejecute la prueba de mensajería instantánea, puede configurarlo mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="57412-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="57412-183">Al ejecutar este comando, se deshabilitarán todas las transacciones sintéticas en el nodo de monitor especificado, excepto la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="57412-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="57412-184">Ver y probar la configuración de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="57412-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="57412-185">Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="57412-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="57412-186">Este comando devolverá información similar a esta, en función de las transacciones sintéticas asignadas al nodo:</span><span class="sxs-lookup"><span data-stu-id="57412-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="57412-187">Registro de conferencia de datos persistentChatMessage de presencia de conferencias de mensajería instantánea de Mensajería instantánea P2PAV</span><span class="sxs-lookup"><span data-stu-id="57412-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="57412-188">Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="57412-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="57412-189">Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="57412-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="57412-190">Recibirá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="57412-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="57412-191">Identidad : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="57412-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="57412-192">ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="57412-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="57412-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="57412-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="57412-194">Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="57412-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="57412-195">El rol de registrador necesario está instalado</span><span class="sxs-lookup"><span data-stu-id="57412-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="57412-196">Se crea la clave del Registro necesaria (completada al ejecutar el cmdlet Set-CsWatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="57412-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="57412-197">Los servidores ejecutan la versión correcta de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="57412-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="57412-198">Los puertos están configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="57412-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="57412-199">Los usuarios de prueba asignados tienen las credenciales necesarias</span><span class="sxs-lookup"><span data-stu-id="57412-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="57412-200">Administración de nodos de monitor</span><span class="sxs-lookup"><span data-stu-id="57412-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="57412-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="57412-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="57412-202">Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, también puede usar el cmdlet **Set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de monitor y configurar el nodo de monitor para que use direcciones URL web internas o externas al ejecutar sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="57412-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="57412-203">De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="57412-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="57412-204">En ocasiones, sin embargo, es posible que desee suspender esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="57412-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="57412-205">Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="57412-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="57412-206">Sin conectividad de red, se producirá un error en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="57412-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="57412-207">Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="57412-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="57412-208">Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor atl watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="57412-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="57412-209">Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="57412-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="57412-210">La propiedad Enabled sirve para activar y desactivar nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="57412-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="57412-211">En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="57412-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="57412-212">Ese comando quita todas las opciones de configuración del nodo de monitor del equipo especificado, lo que impide que ese equipo ejecute automáticamente transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="57412-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="57412-213">Sin embargo, el comando no desinstala los archivos de agente de System Center ni los archivos del sistema de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57412-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="57412-214">De forma predeterminada, los nodos de monitor usan las direcciones URL web externas de una organización al realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="57412-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="57412-215">Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL web internas de la organización.</span><span class="sxs-lookup"><span data-stu-id="57412-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="57412-216">Esto permite a los administradores comprobar el acceso a la dirección URL de los usuarios ubicados dentro de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="57412-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="57412-217">Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebURls en True ($True):</span><span class="sxs-lookup"><span data-stu-id="57412-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="57412-218">Restablecer esta propiedad al valor predeterminado de False ($False) hará que el monitor vuelva a usar las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="57412-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="57412-219">Instrucciones de configuración especiales para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="57412-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="57412-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="57412-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="57412-221">La mayoría de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal como está.</span><span class="sxs-lookup"><span data-stu-id="57412-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="57412-222">En la mayoría de los casos, tan pronto como la transacción sintética se agrega a las opciones de configuración del nodo de monitor, el nodo de monitor puede empezar a usar esa transacción sintética durante los pases de prueba.</span><span class="sxs-lookup"><span data-stu-id="57412-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="57412-223">Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="57412-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="57412-224">Transacción sintética de conferencia de datos</span><span class="sxs-lookup"><span data-stu-id="57412-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="57412-225">Si el equipo del nodo de monitor se encuentra fuera de la red perimetral, probablemente no podrá ejecutar la transacción sintética de conferencia de datos a menos que primero deshabilite la configuración de proxy de Explorador de Internet de Windows Internet Explorer® para la cuenta de servicio de red mediante los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="57412-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="57412-226">En el equipo del nodo de monitor, haga clic en Inicio **,** todos los **programas,** accesorios **,** haga clic con el botón secundario en Símbolo del sistema **y,** a continuación, haga clic **en Ejecutar como administrador.**</span><span class="sxs-lookup"><span data-stu-id="57412-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="57412-227">En la ventana de la consola, escriba el siguiente comando y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="57412-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="57412-228">Verá el siguiente mensaje en la ventana de comandos:</span><span class="sxs-lookup"><span data-stu-id="57412-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="57412-229">BITSAdmin está en desuso y no se garantiza que esté disponible en versiones futuras de Windows.</span><span class="sxs-lookup"><span data-stu-id="57412-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="57412-230">Las herramientas de administración para el servicio BITS ahora se proporcionan mediante cmdlets de PowerShell de BITS.</span><span class="sxs-lookup"><span data-stu-id="57412-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="57412-231">Configuración de proxy de Internet para la cuenta NetworkService establecida en NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="57412-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="57412-232">(conexión = predeterminada)</span><span class="sxs-lookup"><span data-stu-id="57412-232">(connection = default)</span></span>
  
<span data-ttu-id="57412-233">Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="57412-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="57412-234">Transacción sintética de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="57412-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="57412-235">La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba pueden conectarse a cuentas de correo de voz que están en Exchange.</span><span class="sxs-lookup"><span data-stu-id="57412-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="57412-236">Los usuarios de prueba tendrán que estar preconfigurados con cuentas de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="57412-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="57412-237">Transacción sintética de chat persistente</span><span class="sxs-lookup"><span data-stu-id="57412-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="57412-238">Para usar la transacción sintética de chat persistente, primero debe crear un canal y conceder a los usuarios de prueba permisos para usarlo.</span><span class="sxs-lookup"><span data-stu-id="57412-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="57412-239">Puede usar la transacción sintética de chat persistente para configurar este canal:</span><span class="sxs-lookup"><span data-stu-id="57412-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="57412-240">Debe ejecutar esta tarea de configuración desde dentro de la empresa:</span><span class="sxs-lookup"><span data-stu-id="57412-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="57412-241">Si se ejecuta desde un equipo que no es servidor, el usuario que ejecuta el cmdlet debe ser miembro del rol CsPersistentChatAdministrators para Role-Based Access Control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="57412-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="57412-242">Si se ejecuta desde el propio servidor, el usuario que ejecuta el cmdlet debe ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="57412-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="57412-243">Transacción sintética de llamada punto a punto rtc</span><span class="sxs-lookup"><span data-stu-id="57412-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="57412-244">La Test-CsPstnPeerToPeerCall sintética comprueba la capacidad de realizar y recibir llamadas a través de una red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="57412-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="57412-245">Para ejecutar esta transacción sintética, debe configurar:</span><span class="sxs-lookup"><span data-stu-id="57412-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="57412-246">Dos usuarios de prueba habilitados para UC (un autor de llamada y un receptor).</span><span class="sxs-lookup"><span data-stu-id="57412-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="57412-247">Números de llamada directa a la extensión (DID) de cada cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="57412-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="57412-248">Directivas VoIP y rutas de voz que permiten que las llamadas al número del receptor lleguen a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="57412-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="57412-249">Una puerta de enlace RTC que acepta llamadas y medios que enrutarán las llamadas de vuelta al grupo de servidores principal de un receptor, en función del número marcado.</span><span class="sxs-lookup"><span data-stu-id="57412-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="57412-250">Transacción sintética del almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="57412-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="57412-251">La transacción sintética del almacén de contactos unificado comprueba la capacidad de Skype Empresarial Server para recuperar contactos en nombre de un usuario de Exchange.</span><span class="sxs-lookup"><span data-stu-id="57412-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="57412-252">Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="57412-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="57412-253">Lyss-Exchange la autenticación de servidor a servidor debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="57412-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="57412-254">Los usuarios de prueba deben tener un buzón de Exchange válido.</span><span class="sxs-lookup"><span data-stu-id="57412-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="57412-255">Una vez que se cumplen estas condiciones, puede ejecutar el siguiente cmdlet Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:</span><span class="sxs-lookup"><span data-stu-id="57412-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="57412-256">Las listas de contactos de usuario de prueba pueden tardar algún tiempo en migrarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="57412-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="57412-257">Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca -Setup:</span><span class="sxs-lookup"><span data-stu-id="57412-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="57412-258">Esta línea de comandos se completará correctamente una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="57412-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="57412-259">Transacción sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="57412-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="57412-260">La transacción sintética de mensajería instantánea extensible de mensajería y presencia (XMPP) requiere que configure la característica XMPP con uno o más dominios federados.</span><span class="sxs-lookup"><span data-stu-id="57412-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="57412-261">Para habilitar la transacción sintética XMPP, debe proporcionar un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP enrutable.</span><span class="sxs-lookup"><span data-stu-id="57412-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="57412-262">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57412-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="57412-263">En este ejemplo, debe existir una regla de Skype Empresarial Server para enrutar mensajes litwareinc.com una puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="57412-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="57412-264">Las puertas de enlace XMPP y los servidores proxy estaban disponibles en Skype Empresarial Server 2015, pero ya no son compatibles con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57412-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="57412-265">Consulte [Migración de la federación XMPP](../migration/migrating-xmpp-federation.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="57412-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="57412-266">Transacción sintética del servidor de interoperabilidad de vídeo (VIS)</span><span class="sxs-lookup"><span data-stu-id="57412-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="57412-267">La transacción sintética del servidor de interoperabilidad de vídeo (VIS) requiere que descargue e instale los archivos de compatibilidad con[ transacciones ](https://www.microsoft.com/download/details.aspx?id=46921)sintéticas (VISSTSupportPackage.msi).</span><span class="sxs-lookup"><span data-stu-id="57412-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="57412-268">Para instalar VISSTSupportPackage.msi asegúrese de que las dependencias (en Requisitos del sistema) del msi ya están instaladas.</span><span class="sxs-lookup"><span data-stu-id="57412-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="57412-269">Ejecute VISSTSupportPackage.msi para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="57412-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="57412-270">El archivo .msi instala todos los archivos en la siguiente ruta de acceso: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span><span class="sxs-lookup"><span data-stu-id="57412-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="57412-271">Para obtener más información sobre cómo ejecutar la transacción sintética vis, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)</span><span class="sxs-lookup"><span data-stu-id="57412-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="57412-272">Cambio de la frecuencia de ejecución de las transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="57412-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="57412-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="57412-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="57412-274">De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="57412-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="57412-275">Las transacciones sintéticas se ejecutan secuencialmente dentro de un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="57412-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="57412-276">Se necesita un intervalo más largo para proporcionar tiempo para que se completen todas las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="57412-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="57412-277">Si es conveniente ejecutar transacciones sintéticas con más frecuencia, el número de transacciones sintéticas que se ejecutan con un conjunto determinado de usuarios debe reducirse para que las pruebas se puedan completar en el intervalo de tiempo deseado con algún búfer para retrasos ocasionales en la red.</span><span class="sxs-lookup"><span data-stu-id="57412-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="57412-278">Si es conveniente ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.</span><span class="sxs-lookup"><span data-stu-id="57412-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="57412-279">Para cambiar la frecuencia con la que se ejecutan las transacciones sintéticas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="57412-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="57412-280">Abra System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="57412-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="57412-281">Haga clic en la sección Creación.</span><span class="sxs-lookup"><span data-stu-id="57412-281">Click Authoring section.</span></span> <span data-ttu-id="57412-282">Sección Hacer clic en Reglas (en Creación)</span><span class="sxs-lookup"><span data-stu-id="57412-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="57412-283">En la sección Reglas, busque la regla con el nombre "Main Synthetic Transaction Runner Performance Collection Rule" (Regla de recopilación de rendimiento del ejecutor de transacciones sintéticas principal)</span><span class="sxs-lookup"><span data-stu-id="57412-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="57412-284">Haga clic con el botón secundario en la regla y, a continuación, seleccione Invalidar la regla y, a continuación, seleccione "Para todos los objetos de clase: Pool Watcher"</span><span class="sxs-lookup"><span data-stu-id="57412-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="57412-285">En la ventana Propiedades de reemplazo, seleccione El nombre del parámetro "Frecuencia" y establezca el valor de invalidación en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="57412-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="57412-286">En la misma ventana, seleccione el módulo de administración al que debe aplicarse este reemplazo.</span><span class="sxs-lookup"><span data-stu-id="57412-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="57412-287">Uso de registro enriquecido para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="57412-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="57412-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="57412-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="57412-289">Las transacciones sintéticas resultan extremadamente útiles para ayudar a identificar problemas con el sistema.</span><span class="sxs-lookup"><span data-stu-id="57412-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="57412-290">Por ejemplo, el cmdlet Test-CsRegistration podría alertar a los administradores sobre el hecho de que los usuarios tenían dificultades para registrarse en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57412-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="57412-291">Sin embargo, es posible que se necesiten detalles adicionales para determinar la causa real de un error.</span><span class="sxs-lookup"><span data-stu-id="57412-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="57412-292">Por este motivo, las transacciones sintéticas proporcionan un registro enriquecido.</span><span class="sxs-lookup"><span data-stu-id="57412-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="57412-293">Con el registro enriquecido, para cada actividad que realiza una transacción sintética, se registra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="57412-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="57412-294">Hora en que se inició la actividad.</span><span class="sxs-lookup"><span data-stu-id="57412-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="57412-295">Hora en que finalizó la actividad.</span><span class="sxs-lookup"><span data-stu-id="57412-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="57412-296">La acción que se realizó (por ejemplo, crear, unirse o salir de una conferencia, iniciar sesión en Skype Empresarial Server, enviar un mensaje instantáneo).</span><span class="sxs-lookup"><span data-stu-id="57412-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="57412-297">Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad</span><span class="sxs-lookup"><span data-stu-id="57412-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="57412-298">Mensajes de registro SIP.</span><span class="sxs-lookup"><span data-stu-id="57412-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="57412-299">Registros de excepción o códigos de diagnóstico generados cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="57412-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="57412-300">Resultado neto de la ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="57412-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="57412-301">Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="57412-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="57412-302">Si ejecuta manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar una variable Windows PowerShell en la que se almacenará la información.</span><span class="sxs-lookup"><span data-stu-id="57412-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="57412-303">Desde allí, tiene la opción de usar uno de los dos métodos para guardar o ver mensajes de error en el registro enriquecido en formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="57412-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="57412-304">Para recuperar la información de solución de problemas, especifique el parámetro OutLoggerVariable, seguido del nombre de variable que elija:</span><span class="sxs-lookup"><span data-stu-id="57412-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="57412-305">: no antefies el nombre de la variable con el carácter $.</span><span class="sxs-lookup"><span data-stu-id="57412-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="57412-306">Use un nombre de variable como RegistrationTest (no $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="57412-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="57412-307">Cuando ejecute este comando, verá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="57412-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="57412-308">Fqdn de destino : atl-cs-001.litwareinc.com resultado : latencia de error : 00:00:00 Mensaje de error : Esta máquina no tiene ningún certificado asignado.</span><span class="sxs-lookup"><span data-stu-id="57412-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="57412-309">Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="57412-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="57412-310">Para obtener acceso a esta información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:</span><span class="sxs-lookup"><span data-stu-id="57412-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="57412-311">Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="57412-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="57412-312">Puede ver estos archivos mediante Windows Internet Explorer, Microsoft Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="57412-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="57412-313">Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores.</span><span class="sxs-lookup"><span data-stu-id="57412-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="57412-314">Estos registros no se generarán si se produce un error en la ejecución antes de que PowerShell de Skype Empresarial Server pueda cargar y ejecutar la transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="57412-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="57412-315">De forma predeterminada, Skype Empresarial Server guarda los archivos de registro en una carpeta que no se comparte.</span><span class="sxs-lookup"><span data-stu-id="57412-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="57412-316">Para que estos registros estén accesibles fácilmente, debe compartir esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="57412-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="57412-317">Por ejemplo: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="57412-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
