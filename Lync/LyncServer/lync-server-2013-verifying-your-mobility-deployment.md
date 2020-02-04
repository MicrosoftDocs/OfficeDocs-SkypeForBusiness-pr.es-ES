---
title: 'Lync Server 2013: Comprobar la implementación de la movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6c82478fffe2815e9d69b870b3b434eadb3cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="1aba5-102">Comprobar la implementación de la movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aba5-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aba5-103">_**Última modificación del tema:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="1aba5-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="1aba5-104">Después de implementar el servicio de movilidad de Lync Server y el servicio Detección automática de Lync Server, ejecute una transacción de prueba para comprobar que su implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="1aba5-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="1aba5-105">Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios que usan clientes móviles de Lync 2013 para crear, unirse a y comunicarse en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="1aba5-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="1aba5-106">Para usar esta transacción de prueba, necesita dos usuarios reales o usuarios de prueba, así como sus credenciales completas.</span><span class="sxs-lookup"><span data-stu-id="1aba5-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="1aba5-107">Use **Test-CsMcxP2PIM** para probar el envío de un mensaje instantáneo entre dos usuarios que usan Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="1aba5-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="1aba5-108">De forma similar a **Test-CsUcwaConference**, se usan dos usuarios reales o dos usuarios de prueba predefinidos.</span><span class="sxs-lookup"><span data-stu-id="1aba5-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="1aba5-109">Para probar las conferencias de los clientes móviles de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1aba5-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="1aba5-110">Inicie sesión como miembro del rol CsAdministrator en cualquier equipo que tenga instalado el Shell de administración de Lync Server y Ocscore.</span><span class="sxs-lookup"><span data-stu-id="1aba5-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="1aba5-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1aba5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1aba5-112">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="1aba5-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="1aba5-113">Puede establecer las credenciales en un script y pasarlas al cmdlet de prueba.</span><span class="sxs-lookup"><span data-stu-id="1aba5-113">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="1aba5-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1aba5-114">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="1aba5-115">Para probar la mensajería instantánea de persona a persona (mi) para Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="1aba5-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="1aba5-116">Inicie sesión como miembro del rol CsAdministrator en cualquier equipo que tenga instalado el Shell de administración de Lync Server y Ocscore.</span><span class="sxs-lookup"><span data-stu-id="1aba5-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="1aba5-117">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1aba5-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1aba5-118">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="1aba5-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="1aba5-119">Puede establecer las credenciales en un script y pasarlas al cmdlet de prueba.</span><span class="sxs-lookup"><span data-stu-id="1aba5-119">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="1aba5-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1aba5-120">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1aba5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aba5-121">See Also</span></span>


[<span data-ttu-id="1aba5-122">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="1aba5-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="1aba5-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="1aba5-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

