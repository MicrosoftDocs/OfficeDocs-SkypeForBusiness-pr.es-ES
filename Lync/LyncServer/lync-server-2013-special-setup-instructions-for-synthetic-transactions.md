---
title: 'Lync Server 2013: instrucciones de configuración especiales para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92786b50bc0b29fe5bc7f6b5b8ac978a17085aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="a3adb-102">Instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3adb-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3adb-103">_**Última modificación del tema:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="a3adb-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="a3adb-p101">La mayoría de las transacciones sintéticas se puede ejecutar en un nodo de monitor tal cual; es decir, en cuanto la transacción se agregue a la configuración del nodo, este podrá utilizarla durante sus fases de prueba. Esto, sin embargo, no es aplicable a todas las transacciones sintéticas. En las siguientes secciones se detallan estas excepciones (transacciones sintéticas que requieren instrucciones especiales de configuración).</span><span class="sxs-lookup"><span data-stu-id="a3adb-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="a3adb-107">Tratar errores de tiempo de espera del servidor</span><span class="sxs-lookup"><span data-stu-id="a3adb-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="a3adb-108">En algunos casos, es posible que las transacciones sintéticas fallen con errores de tiempo de espera del servidor (código de error 504).</span><span class="sxs-lookup"><span data-stu-id="a3adb-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="a3adb-109">Estos errores suelen deberse a problemas del firewall.</span><span class="sxs-lookup"><span data-stu-id="a3adb-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="a3adb-110">Cuando se ejecuta una transacción sintética, esa transacción se ejecuta en el proceso MonitoringHost. exe; a su vez, MonitoringHost. exe inicia una instancia del proceso PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="a3adb-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="a3adb-111">Si el Firewall bloquea MonitoringHost. exe o PowerShell. exe, se producirá un error en la transacción sintética y se generará un error 504.</span><span class="sxs-lookup"><span data-stu-id="a3adb-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="a3adb-112">Para resolver este problema, debe crear manualmente reglas de Firewall de entrada para MonitoringHost. exe y PowerShell. exe en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a3adb-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="a3adb-113">Esto puede realizarse a través de Firewall de Windows o de un software de Firewall local de terceros, en función de la configuración preexistente del servidor.</span><span class="sxs-lookup"><span data-stu-id="a3adb-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="a3adb-114">Si va a usar un dispositivo de Firewall de red entre el equipo de host de transacción sintética y los servidores de Lync que está tratando de supervisar, debe tratar el host como un equipo cliente y todos los requisitos de puerto de Firewall de [puertos y protocolos para los servidores internos en Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a3adb-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="a3adb-115">Transacciones sintéticas de conferencia de datos</span><span class="sxs-lookup"><span data-stu-id="a3adb-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-116">Si el equipo de nodo de monitor está ubicado fuera de la red perimetral, es probable que no pueda ejecutar la transacción sintética de conferencia de datos a menos que primero deshabilite la configuración de proxy de Internet Explorer para la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="a3adb-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="a3adb-117">Haga lo siguiente para deshabilitarla:</span><span class="sxs-lookup"><span data-stu-id="a3adb-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="a3adb-118">En el equipo nodo de supervisor, haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a3adb-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="a3adb-119">Escriba el siguiente comando en la ventana de la consola y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a3adb-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="a3adb-120">Aparecerá el siguiente mensaje en la ventana Comandos:</span><span class="sxs-lookup"><span data-stu-id="a3adb-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="a3adb-121">Este mensaje significa que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="a3adb-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="a3adb-122">Transacciones sintéticas de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="a3adb-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-123">La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba se pueden conectar a cuentas de correo de voz hospedadas en Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3adb-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="a3adb-124">Estos usuarios de prueba deben estar configurados previamente con cuentas de correo de voz para poder usar pruebas de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3adb-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="a3adb-125">Transacciones sintéticas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a3adb-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-126">Para usar la transacción sintética de chat persistente, los administradores primero deben crear un canal y conceder a los usuarios de prueba permisos para usarlos.</span><span class="sxs-lookup"><span data-stu-id="a3adb-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="a3adb-127">El cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) se puede usar para configurar correctamente los usuarios de prueba:</span><span class="sxs-lookup"><span data-stu-id="a3adb-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="a3adb-128">Esta tarea de configuración debe realizarse desde la empresa:</span><span class="sxs-lookup"><span data-stu-id="a3adb-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="a3adb-129">Si se realiza en un equipo que no es servidor, el usuario que ejecute el cmdlet debe pertenecer al rol PersistentChatAdministrators de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a3adb-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="a3adb-130">Si se realiza desde el propio servidor, el usuario que ejecute el cmdlet debe pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a3adb-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a3adb-131">El comando anterior incluía el parámetro Setup establecido en True ($True).</span><span class="sxs-lookup"><span data-stu-id="a3adb-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="a3adb-132">Si incluye el parámetro Setup, test-CsPersistentChatMessage creará un salón de chat persistente especial y rellenará ese salón con los usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="a3adb-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="a3adb-133">Esto sirve para garantizar que existe realmente un salón de chat destinado a realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="a3adb-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="a3adb-134">Tenga en cuenta que el parámetro Setup solo debe ejecutarse desde un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a3adb-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="a3adb-135">Solo un administrador puede eliminar el salón de chat que Test-CsPersistentChatMessage crea.</span><span class="sxs-lookup"><span data-stu-id="a3adb-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="a3adb-136">Transacciones sintéticas de llamada punto a punto de RTC</span><span class="sxs-lookup"><span data-stu-id="a3adb-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-137">La transacción sintética [de test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) comprueba la capacidad de realizar y recibir llamadas a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="a3adb-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="a3adb-138">Para ejecutar esta transacción sintética, los administradores deben tener preparado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3adb-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="a3adb-139">Dos usuarios de prueba (un autor y un receptor) habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a3adb-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="a3adb-140">Números de llamada directa a la extensión (DID) de cada cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a3adb-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="a3adb-141">Directivas y rutas de voz que permitan efectuar llamadas al número del receptor para llegar a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="a3adb-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="a3adb-142">Una puerta de enlace RTC que acepte llamadas, además de medios que enruten llamadas de regreso al grupo de servidores principales de un receptor en función del número marcado.</span><span class="sxs-lookup"><span data-stu-id="a3adb-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="a3adb-143">Transacciones sintéticas de almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="a3adb-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-144">La transacción sintética de almacén de contactos unificados comprueba que Lync Server 2013 puede recuperar contactos en nombre de un usuario de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3adb-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="a3adb-145">Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="a3adb-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="a3adb-146">La [Administración de la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) debe estar configurada entre lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a3adb-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="a3adb-147">Los usuarios de prueba deben tener un buzón válido de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a3adb-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="a3adb-148">Si se cumplen, los administradores pueden ejecutar el siguiente comando a fin de constatar que el usuario con la dirección SIP kenmyer@litwareinc.com puede recuperar sus contactos del almacén de contactos unificados:</span><span class="sxs-lookup"><span data-stu-id="a3adb-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="a3adb-149">Tenga en cuenta el uso del parámetro de configuración usado en el comando anterior.</span><span class="sxs-lookup"><span data-stu-id="a3adb-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="a3adb-150">Si se incluye el parámetro setup cuando se ejecuta test-CsUnifiedContactStore, los contactos del usuario especificado (en este caso, sip:kenmyer@litwareinc.com) se moverán al almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="a3adb-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="a3adb-151">(Por supuesto, si los contactos del usuario ya están en el almacén de contactos unificados, no es necesario moverlos). El parámetro Setup se suele usar una sola vez (la primera vez que se ejecuta test-CsUnifiedContactStore) y solo debe usarse con usuarios de prueba; es decir, con las cuentas de usuario que nunca se iniciarán sesión en Lync Server en realidad.</span><span class="sxs-lookup"><span data-stu-id="a3adb-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="a3adb-152">Una vez que se ha migrado el usuario de prueba al almacén de contactos unificado, puede comprobar que los contactos del usuario se pueden recuperar llamando a test-CsUnifiedContactStore sin el parámetro Setup:</span><span class="sxs-lookup"><span data-stu-id="a3adb-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="a3adb-153">Transacciones sintéticas XMPP</span><span class="sxs-lookup"><span data-stu-id="a3adb-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="a3adb-154">La transacción sintética de mensajería instantánea XMPP (protocolo extensible de mensajería y presencia) requiere que la característica XMPP esté configurada con uno o más dominios federados.</span><span class="sxs-lookup"><span data-stu-id="a3adb-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="a3adb-155">Para habilitar la transacción sintética XMPP, se debe incluir un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP que pueda enrutarse.</span><span class="sxs-lookup"><span data-stu-id="a3adb-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="a3adb-156">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3adb-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="a3adb-157">En este ejemplo, debe existir una regla de Lync Server 2013 para enrutar mensajes para litwareinc.com a una puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="a3adb-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

