---
title: Configurar los usuarios y la configuración de prueba de nodos de monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Resumen: configurar las cuentas de usuario de prueba y la configuración de nodo de monitor para las transacciones sintéticas de Skype empresarial Server.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005955"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="c93f4-103">Configurar los usuarios y la configuración de prueba de nodos de monitor</span><span class="sxs-lookup"><span data-stu-id="c93f4-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="c93f4-104">**Resumen:** Configurar las cuentas de usuario de prueba y la configuración de nodo de monitor para las transacciones sintéticas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="c93f4-105">Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="c93f4-106">[Configure las cuentas de usuario de prueba](test-users-and-settings.md#testuser) que deben usar estos nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="c93f4-107">Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="c93f4-108">Actualizar las opciones de configuración del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="c93f4-109">Configurar cuentas de usuario de prueba</span><span class="sxs-lookup"><span data-stu-id="c93f4-109">Configure Test User Accounts</span></span>
<span data-ttu-id="c93f4-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="c93f4-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="c93f4-111">Las cuentas de prueba no necesitan representar a personas reales, pero deben ser cuentas de Active Directory válidas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="c93f4-112">Además, estas cuentas deben estar habilitadas para Skype empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="c93f4-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="c93f4-113">Si usa el método de autenticación TrustedServer, todo lo que debe hacer es asegurarse de que existen estas cuentas y configurarlas tal y como se indica.</span><span class="sxs-lookup"><span data-stu-id="c93f4-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="c93f4-114">Debe asignar al menos dos usuarios de prueba para cada grupo de servidores que quiera probar.</span><span class="sxs-lookup"><span data-stu-id="c93f4-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="c93f4-115">Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el shell de administración de Skype empresarial Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="c93f4-116">Para ello, ejecute un comando similar al siguiente (estos comandos suponen que las dos cuentas de usuario de Active Directory se han creado y que estas cuentas están habilitadas para Skype empresarial Server):</span><span class="sxs-lookup"><span data-stu-id="c93f4-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="c93f4-117">Debe incluir no solo la dirección SIP, sino también el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c93f4-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="c93f4-118">Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que escriba la información.</span><span class="sxs-lookup"><span data-stu-id="c93f4-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="c93f4-119">El nombre de usuario se puede especificar mediante el formato de nombre de dominio\nombre de usuario que se muestra en el bloque de código anterior.</span><span class="sxs-lookup"><span data-stu-id="c93f4-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="c93f4-120">Para comprobar que se han creado las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="c93f4-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="c93f4-121">Se devolverá información similar a la siguiente para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="c93f4-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="c93f4-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="c93f4-122">**UserName**</span></span>|<span data-ttu-id="c93f4-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="c93f4-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c93f4-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="c93f4-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="c93f4-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="c93f4-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="c93f4-126">Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="c93f4-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="c93f4-127">Una vez creados los usuarios de prueba, puede crear un nodo de monitor con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="c93f4-128">Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="c93f4-129">El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com y watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c93f4-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="c93f4-130">Si el nodo de monitor usa la autenticación TrustedServer, las dos cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="c93f4-131">Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor mediante el cmdlet Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="c93f4-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="c93f4-132">Para validar que la detección automática del grupo de servidores de destino en el que iniciar sesión está correctamente configurada en lugar de dirigirse directamente a un grupo de servidores, siga estos pasos en su lugar:</span><span class="sxs-lookup"><span data-stu-id="c93f4-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="c93f4-133">Configurar pruebas extendidas</span><span class="sxs-lookup"><span data-stu-id="c93f4-133">Configuring Extended Tests</span></span>

<span data-ttu-id="c93f4-134">Si desea habilitar la prueba de RTC, que comprueba la conectividad con la red telefónica pública conmutada, debe realizar una configuración adicional al configurar el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="c93f4-135">En primer lugar, debe asociar los usuarios de prueba al tipo de prueba RTC ejecutando un comando similar al siguiente desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="c93f4-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="c93f4-136">Los resultados de este comando deben almacenarse en una variable.</span><span class="sxs-lookup"><span data-stu-id="c93f4-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="c93f4-137">En este ejemplo, la variable se denomina $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="c93f4-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="c93f4-138">A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="c93f4-139">Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, agregando los dos usuarios de prueba creados anteriormente y agregando el tipo de prueba de RTC:</span><span class="sxs-lookup"><span data-stu-id="c93f4-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="c93f4-140">Se producirá un error en el comando anterior si no ha instalado los archivos principales de Skype empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="c93f4-141">Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="c93f4-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="c93f4-142">Los usuarios proporcionados deben configurarse con las directivas de voz deseadas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="c93f4-143">Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** mediante delimitadores de coma, como:</span><span class="sxs-lookup"><span data-stu-id="c93f4-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="c93f4-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="c93f4-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="c93f4-145">Debido a que se ha llamado al cmdlet **New-CsWatcherNodeConfiguration** sin usar el parámetro tests, solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) para el nuevo nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="c93f4-146">Por lo tanto, el nodo de monitor probará los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="c93f4-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="c93f4-147">Registro</span><span class="sxs-lookup"><span data-stu-id="c93f4-147">Registration</span></span>
    
- <span data-ttu-id="c93f4-148">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="c93f4-148">IM</span></span>
    
- <span data-ttu-id="c93f4-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="c93f4-149">GroupIM</span></span>
    
- <span data-ttu-id="c93f4-150">P2PAV (sesiones de audio/vídeo punto a punto)</span><span class="sxs-lookup"><span data-stu-id="c93f4-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="c93f4-151">AvConference (audio/conferencia)</span><span class="sxs-lookup"><span data-stu-id="c93f4-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="c93f4-152">Presencia</span><span class="sxs-lookup"><span data-stu-id="c93f4-152">Presence</span></span>
    
- <span data-ttu-id="c93f4-153">ABS (servicio de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="c93f4-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="c93f4-154">ABWQ (servicio web de libreta de direcciones)</span><span class="sxs-lookup"><span data-stu-id="c93f4-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="c93f4-155">Los siguientes componentes no se probarán de manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c93f4-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="c93f4-156">Asconferencia</span><span class="sxs-lookup"><span data-stu-id="c93f4-156">ASConference</span></span>
    
- <span data-ttu-id="c93f4-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="c93f4-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="c93f4-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="c93f4-158">DataConference</span></span>
    
- <span data-ttu-id="c93f4-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="c93f4-159">DialinConferencing</span></span>
    
- <span data-ttu-id="c93f4-160">ExumConnectivity (mensajería unificada de Exchange)</span><span class="sxs-lookup"><span data-stu-id="c93f4-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="c93f4-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="c93f4-161">JoinLauncher</span></span>
    
- <span data-ttu-id="c93f4-162">MCXP2PIM (mensajería instantánea de dispositivos móviles heredados)</span><span class="sxs-lookup"><span data-stu-id="c93f4-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="c93f4-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="c93f4-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="c93f4-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="c93f4-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="c93f4-165">RTC (llamadas de puerta de enlace RTC, especificadas como una prueba extendida)</span><span class="sxs-lookup"><span data-stu-id="c93f4-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="c93f4-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="c93f4-166">UcwaConference</span></span>
    
- <span data-ttu-id="c93f4-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="c93f4-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="c93f4-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="c93f4-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="c93f4-169">Agregar y quitar transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="c93f4-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="c93f4-170">Una vez configurado el nodo de monitor, puede usar el cmdlet Set-CsWatcherNodeConfiguration para agregar o quitar transacciones sintéticas en el nodo.</span><span class="sxs-lookup"><span data-stu-id="c93f4-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="c93f4-171">Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="c93f4-172">Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="c93f4-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c93f4-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="c93f4-174">Se producirá un error si ya se ha habilitado una o varias de estas pruebas (por ejemplo, Conference) en el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="c93f4-175">En este caso, aparecerá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="c93f4-176">Set-CsWatcherNodeConfiguration: hay una secuencia de teclas duplicada ' Conference ' para la clave ' urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: nombrePrueba ' o la restricción de identidad única.</span><span class="sxs-lookup"><span data-stu-id="c93f4-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="c93f4-177">Cuando se produce este error, no se aplica ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="c93f4-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="c93f4-178">El comando debe volver a ejecutarse con la prueba duplicada quitada.</span><span class="sxs-lookup"><span data-stu-id="c93f4-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="c93f4-179">Para quitar una transacción sintética de un nodo de monitor, use el método Remove.</span><span class="sxs-lookup"><span data-stu-id="c93f4-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="c93f4-180">Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:</span><span class="sxs-lookup"><span data-stu-id="c93f4-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="c93f4-181">Puede usar el método replace para reemplazar todas las pruebas habilitadas actualmente con una o más pruebas nuevas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="c93f4-182">Por ejemplo, si desea que un nodo de monitor solo ejecute la prueba de mi, puede configurarlo con este comando:</span><span class="sxs-lookup"><span data-stu-id="c93f4-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="c93f4-183">Al ejecutar este comando, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="c93f4-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="c93f4-184">Ver y probar la configuración de nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="c93f4-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="c93f4-185">Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="c93f4-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="c93f4-186">Este comando devolverá información similar a la siguiente, según las transacciones sintéticas que se hayan asignado al nodo:</span><span class="sxs-lookup"><span data-stu-id="c93f4-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="c93f4-187">Inscripción de mensajería instantánea GroupIM P2PAV AvConference de presencia PersistentChatMessage de la Conferencia</span><span class="sxs-lookup"><span data-stu-id="c93f4-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="c93f4-188">Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="c93f4-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="c93f4-189">Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="c93f4-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="c93f4-190">Obtendrá una información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="c93f4-191">Identidad: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c93f4-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="c93f4-192">TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="c93f4-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="c93f4-193">ExtendedTests: {TestUsers = IList<System. String>; Name = prueba RTC; Te...}</span><span class="sxs-lookup"><span data-stu-id="c93f4-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="c93f4-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c93f4-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="c93f4-195">PortNumber: 5061</span><span class="sxs-lookup"><span data-stu-id="c93f4-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="c93f4-196">Para comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="c93f4-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="c93f4-197">Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c93f4-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="c93f4-198">El rol de registrador necesario está instalado.</span><span class="sxs-lookup"><span data-stu-id="c93f4-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="c93f4-199">Se crea la clave del registro necesaria (se completa cuando se ejecutó el cmdlet Set-CsWatcherNodeConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c93f4-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="c93f4-200">Los servidores ejecutan la versión correcta de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="c93f4-201">Los puertos están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="c93f4-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="c93f4-202">Los usuarios de prueba asignados tienen las credenciales necesarias.</span><span class="sxs-lookup"><span data-stu-id="c93f4-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="c93f4-203">Administración de nodos de monitor</span><span class="sxs-lookup"><span data-stu-id="c93f4-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="c93f4-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="c93f4-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="c93f4-205">Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, también puede usar el cmdlet **set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de monitor y configurar el nodo de monitor para usar direcciones URL web internas o direcciones URL web externas al ejecutar sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="c93f4-206">De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="c93f4-207">Sin embargo, en ocasiones, es posible que desee suspender esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="c93f4-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="c93f4-208">Por ejemplo, si el nodo de monitor se desconecta temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="c93f4-209">Sin la conectividad de red, se producirá un error en esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="c93f4-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="c93f4-210">Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="c93f4-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="c93f4-211">Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor ATL Watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c93f4-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="c93f4-212">Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="c93f4-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="c93f4-213">La propiedad Enabled sirve para activar y desactivar nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="c93f4-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="c93f4-214">En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="c93f4-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="c93f4-215">Este comando quita todas las opciones de configuración de nodo de monitor del equipo especificado, lo que impide que el equipo ejecute automáticamente transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="c93f4-216">Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos del sistema de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="c93f4-217">De forma predeterminada, los nodos de monitor usan direcciones URL de web externas de la organización al realizar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="c93f4-218">Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL web internas de la organización.</span><span class="sxs-lookup"><span data-stu-id="c93f4-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="c93f4-219">Esto permite a los administradores comprobar el acceso a direcciones URL para los usuarios que se encuentran dentro de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="c93f4-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="c93f4-220">Para configurar un nodo de monitor para que use direcciones URL internas en lugar de direcciones URL externas, establezca la propiedad UseInternalWebURls en true ($True):</span><span class="sxs-lookup"><span data-stu-id="c93f4-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="c93f4-221">Restablecer esta propiedad en el valor predeterminado de false ($False) hará que el monitor vuelva a usar las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="c93f4-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="c93f4-222">Instrucciones de configuración especiales para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="c93f4-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="c93f4-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c93f4-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c93f4-224">La mayoría de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal cual.</span><span class="sxs-lookup"><span data-stu-id="c93f4-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="c93f4-225">En la mayoría de los casos, en cuanto la transacción sintética se agrega a las opciones de configuración de nodo de monitor, el nodo de monitor puede empezar a usar esa transacción sintética durante la prueba.</span><span class="sxs-lookup"><span data-stu-id="c93f4-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="c93f4-226">Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c93f4-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="c93f4-227">Transacción sintética de conferencia de datos</span><span class="sxs-lookup"><span data-stu-id="c93f4-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-228">Si el equipo de nodo de monitor está ubicado fuera de la red perimetral, es probable que no pueda ejecutar la transacción sintética de conferencia de datos a menos que deshabilite primero la configuración de Windows Internet Explorer® el proxy de explorador de Internet de la red. Cuenta de servicio; para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c93f4-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="c93f4-229">En el equipo nodo de monitor, haga clic en **Inicio**, en **todos los programas**, en **accesorios**, haga clic con el botón secundario en **símbolo del sistema**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="c93f4-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="c93f4-230">En la ventana de la consola, escriba el siguiente comando y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="c93f4-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="c93f4-231">Verá el siguiente mensaje mostrado en la ventana de comandos:</span><span class="sxs-lookup"><span data-stu-id="c93f4-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="c93f4-232">Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="c93f4-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="c93f4-233">Transacción sintética de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="c93f4-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-234">La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba se pueden conectar a cuentas de correo de voz hospedadas en Exchange.</span><span class="sxs-lookup"><span data-stu-id="c93f4-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="c93f4-235">Los usuarios de prueba deberán preconfigurarse con cuentas de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="c93f4-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="c93f4-236">Transacción sintética de chat persistente</span><span class="sxs-lookup"><span data-stu-id="c93f4-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-237">Para usar la transacción sintética de chat persistente, primero debe crear un canal y conceder a los usuarios de prueba permisos para usarlos.</span><span class="sxs-lookup"><span data-stu-id="c93f4-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="c93f4-238">Puede usar la transacción sintética de chat persistente para configurar este canal:</span><span class="sxs-lookup"><span data-stu-id="c93f4-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="c93f4-239">Debe ejecutar esta tarea de configuración debe ejecutarse desde dentro de la empresa:</span><span class="sxs-lookup"><span data-stu-id="c93f4-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="c93f4-240">Si se ejecuta desde un equipo que no sea un servidor, el usuario que ejecuta el cmdlet debe ser miembro del rol CsPersistentChatAdministrators para el control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c93f4-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="c93f4-241">Si se ejecuta desde el propio servidor, el usuario que ejecuta el cmdlet debe ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c93f4-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="c93f4-242">Transacción sintética de llamada punto a punto de RTC</span><span class="sxs-lookup"><span data-stu-id="c93f4-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-243">La transacción sintética de test-CsPstnPeerToPeerCall comprueba la capacidad de realizar y recibir llamadas a través de una red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="c93f4-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="c93f4-244">Para ejecutar esta transacción sintética, debe configurar:</span><span class="sxs-lookup"><span data-stu-id="c93f4-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="c93f4-245">Dos usuarios de prueba habilitados para UC (una persona que llama y un receptor).</span><span class="sxs-lookup"><span data-stu-id="c93f4-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="c93f4-246">Números de llamada directa a la extensión (DID) de cada cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c93f4-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="c93f4-247">Directivas de VoIP y rutas de voz que permiten llamadas al número del receptor para llegar a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c93f4-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="c93f4-248">Una puerta de enlace RTC que acepta llamadas y medios que redirigen las llamadas de vuelta al grupo de servidores principales de un receptor, en función del número marcado.</span><span class="sxs-lookup"><span data-stu-id="c93f4-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="c93f4-249">Transacción sintética de almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="c93f4-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-250">La transacción sintética de almacén de contactos unificado comprueba la capacidad de Skype empresarial Server para recuperar los contactos en nombre de un usuario de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c93f4-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="c93f4-251">Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="c93f4-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="c93f4-252">Se debe configurar la autenticación de Lyss-Exchange Server a Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="c93f4-253">Los usuarios de prueba deben tener un buzón de Exchange válido.</span><span class="sxs-lookup"><span data-stu-id="c93f4-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="c93f4-254">Una vez que se cumplen estas condiciones, puede ejecutar el siguiente cmdlet de Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:</span><span class="sxs-lookup"><span data-stu-id="c93f4-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="c93f4-255">La migración de las listas de contactos de los usuarios de prueba a Exchange puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="c93f4-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="c93f4-256">Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca-Setup:</span><span class="sxs-lookup"><span data-stu-id="c93f4-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="c93f4-257">Esta línea de comandos se realizará correctamente una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="c93f4-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="c93f4-258">Transacción sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="c93f4-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-259">La transacción sintética IM del protocolo extensible de mensajería y presencia (XMPP) requiere que configure la característica XMPP con uno o más dominios federados.</span><span class="sxs-lookup"><span data-stu-id="c93f4-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="c93f4-260">Para habilitar la transacción sintética XMPP, debe proporcionar un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP enrutable.</span><span class="sxs-lookup"><span data-stu-id="c93f4-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="c93f4-261">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c93f4-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="c93f4-262">En este ejemplo, tendrá que existir una regla de Skype empresarial Server para enrutar los mensajes de litwareinc.com a una puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="c93f4-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="c93f4-263">Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c93f4-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c93f4-264">Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c93f4-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="c93f4-265">Transacción sintética del servidor de interoperabilidad de vídeo (VIS)</span><span class="sxs-lookup"><span data-stu-id="c93f4-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="c93f4-266">La transacción sintética del servidor de interoperabilidad de vídeo (VIS) requiere que descargue e instale los archivos de compatibilidad de transacción sintética ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="c93f4-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="c93f4-267">Para instalar VISSTSupportPackage. msi, asegúrese de que las dependencias (en requisitos del sistema) para el MSI ya están instaladas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="c93f4-268">Ejecute VISSTSupportPackage. msi para realizar una instalación sencilla.</span><span class="sxs-lookup"><span data-stu-id="c93f4-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="c93f4-269">El archivo. msi instala todos los archivos en la siguiente ruta de acceso: "paquete de compatibilidad con transacción sintética de%ProgramFiles%\VIS".</span><span class="sxs-lookup"><span data-stu-id="c93f4-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="c93f4-270">Para obtener más información sobre cómo ejecutar la transacción sintética VIS, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c93f4-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="c93f4-271">Cambio de la frecuencia de ejecución para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="c93f4-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="c93f4-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c93f4-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c93f4-273">De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="c93f4-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="c93f4-274">Las transacciones sintéticas se ejecutan secuencialmente en un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto entre sí.</span><span class="sxs-lookup"><span data-stu-id="c93f4-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="c93f4-275">Se necesita un intervalo más largo para proporcionar tiempo para completar todas las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="c93f4-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="c93f4-276">Si es deseable ejecutar transacciones sintéticas con más frecuencia, se debe reducir el número de transacciones sintéticas que se ejecutan con un conjunto determinado de usuarios, de modo que las pruebas puedan completarse en el intervalo de tiempo deseado con un búfer para retrasos en la red ocasionados.</span><span class="sxs-lookup"><span data-stu-id="c93f4-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="c93f4-277">Si es conveniente ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.</span><span class="sxs-lookup"><span data-stu-id="c93f4-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="c93f4-278">Para cambiar la frecuencia con la que se ejecutan las transacciones sintéticas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c93f4-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="c93f4-279">Abra System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c93f4-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="c93f4-280">Haga clic en sección de creación.</span><span class="sxs-lookup"><span data-stu-id="c93f4-280">Click Authoring section.</span></span> <span data-ttu-id="c93f4-281">Haga clic en la sección reglas (en creación).</span><span class="sxs-lookup"><span data-stu-id="c93f4-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="c93f4-282">En la sección reglas, busque la regla con el nombre "regla de recopilación de rendimiento del Ejecutor de transacciones sintéticas principales".</span><span class="sxs-lookup"><span data-stu-id="c93f4-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="c93f4-283">Haga clic con el botón secundario en la regla y seleccione reemplazos, seleccione invalidar la regla y, a continuación, seleccione "para todos los objetos de la clase: monitor de grupo".</span><span class="sxs-lookup"><span data-stu-id="c93f4-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="c93f4-284">En la ventana Propiedades de reemplazo, seleccione el nombre de parámetro "Frequency" y establezca el valor de invalidación en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="c93f4-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="c93f4-285">En la misma ventana, seleccione el módulo de administración en el que se debe aplicar esta invalidación.</span><span class="sxs-lookup"><span data-stu-id="c93f4-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="c93f4-286">Uso de registro enriquecido para transacciones sintéticas</span><span class="sxs-lookup"><span data-stu-id="c93f4-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="c93f4-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c93f4-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c93f4-288">Las transacciones sintéticas resultan muy útiles para ayudar a identificar problemas con el sistema.</span><span class="sxs-lookup"><span data-stu-id="c93f4-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="c93f4-289">Por ejemplo, el cmdlet test-CsRegistration podría avisar a los administradores del hecho de que los usuarios tenían problemas para registrarse con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c93f4-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="c93f4-290">Sin embargo, es posible que se necesiten más detalles para determinar la causa real de un error.</span><span class="sxs-lookup"><span data-stu-id="c93f4-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="c93f4-291">Por este motivo, las transacciones sintéticas proporcionan un registro enriquecido.</span><span class="sxs-lookup"><span data-stu-id="c93f4-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="c93f4-292">Con el registro enriquecido, para cada actividad que se consiga con una transacción sintética, se registra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c93f4-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="c93f4-293">Hora a la que se inició la actividad.</span><span class="sxs-lookup"><span data-stu-id="c93f4-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="c93f4-294">Hora a la que finalizó la actividad.</span><span class="sxs-lookup"><span data-stu-id="c93f4-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="c93f4-295">La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia; iniciar sesión en Skype empresarial Server; enviar un mensaje instantáneo).</span><span class="sxs-lookup"><span data-stu-id="c93f4-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="c93f4-296">Mensajes informativos, detallados, de advertencia o de error generados cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="c93f4-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="c93f4-297">Mensajes de registro SIP.</span><span class="sxs-lookup"><span data-stu-id="c93f4-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="c93f4-298">Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="c93f4-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="c93f4-299">El resultado neto de la ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c93f4-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="c93f4-300">Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="c93f4-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="c93f4-301">Si ejecuta manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información.</span><span class="sxs-lookup"><span data-stu-id="c93f4-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="c93f4-302">Desde allí, tiene la opción de usar uno de estos dos métodos para guardar o ver los mensajes de error en el registro enriquecido, en formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="c93f4-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="c93f4-303">Para recuperar la información de solución de problemas, especifique el parámetro OutLoggerVariable seguido de un nombre de variable que elija:</span><span class="sxs-lookup"><span data-stu-id="c93f4-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="c93f4-304">Asegúrese de no anteponer el carácter $ al nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="c93f4-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="c93f4-305">Use un nombre de variable como el (no $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="c93f4-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="c93f4-306">Cuando ejecute este comando, verá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c93f4-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="c93f4-307">FQDN de destino: resultado de atl-cs-001.litwareinc.com: latencia de error: 00:00:00 mensaje de error: este equipo no tiene ningún certificado asignado.</span><span class="sxs-lookup"><span data-stu-id="c93f4-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="c93f4-308">Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="c93f4-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="c93f4-309">Para tener acceso a esta información en formato HTML, use un comando similar al siguiente para guardar la información almacenada en la variable el en un archivo HTML:</span><span class="sxs-lookup"><span data-stu-id="c93f4-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="c93f4-310">Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="c93f4-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="c93f4-311">Puede ver estos archivos con Windows Internet Explorer, Microsoft Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="c93f4-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="c93f4-312">Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores.</span><span class="sxs-lookup"><span data-stu-id="c93f4-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="c93f4-313">Estos registros no se generarán si se produce un error en la ejecución antes de que Skype empresarial Server PowerShell pueda cargar y ejecutar la transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="c93f4-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c93f4-314">De forma predeterminada, Skype empresarial Server guarda los archivos de registro en una carpeta que no está compartida.</span><span class="sxs-lookup"><span data-stu-id="c93f4-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="c93f4-315">Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="c93f4-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="c93f4-316">Por ejemplo: \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="c93f4-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
