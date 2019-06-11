---
title: 'Lync Server 2013: pruebas de notificaciones de Exchange a Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="419e9-102">Prueba de las notificaciones de Exchange para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="419e9-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="419e9-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="419e9-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="419e9-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="419e9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="419e9-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="419e9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419e9-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="419e9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="419e9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="419e9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419e9-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="419e9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="419e9-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="419e9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="419e9-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="419e9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="419e9-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="419e9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="419e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="419e9-112">Description</span></span>

<span data-ttu-id="419e9-113">El cmdlet **Test-CsExStorageNotification** se usa para comprobar que el servicio de notificación de Microsoft Exchange Server 2013 puede notificar a Lync Server 2013 en cualquier momento en que se realicen actualizaciones en la lista de contactos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="419e9-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="419e9-114">Este cmdlet solo es válido si usa el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="419e9-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="419e9-115">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="419e9-115">Running the test</span></span>

<span data-ttu-id="419e9-116">El comando que se muestra en el ejemplo 1 prueba si el servicio de almacenamiento de Lync Server puede conectarse al servicio de notificación de buzón de Microsoft Exchange Server para el usuario sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="419e9-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="419e9-117">En este ejemplo, NetNamedPipe se usa como enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="419e9-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="419e9-118">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="419e9-118">Determining success or failure</span></span>

<span data-ttu-id="419e9-119">Si la integración de Exchange está configurada correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="419e9-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="419e9-120">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="419e9-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="419e9-121">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="419e9-121">Result : Success</span></span>

<span data-ttu-id="419e9-122">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="419e9-122">Latency : 00:00:00</span></span>

<span data-ttu-id="419e9-123">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="419e9-123">Error Message :</span></span>

<span data-ttu-id="419e9-124">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="419e9-124">Diagnosis :</span></span>

<span data-ttu-id="419e9-125">Si el usuario especificado no puede recibir notificaciones, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="419e9-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="419e9-126">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="419e9-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="419e9-127">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="419e9-127">Result : Failure</span></span>

<span data-ttu-id="419e9-128">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="419e9-128">Latency : 00:00:00</span></span>

<span data-ttu-id="419e9-129">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="419e9-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="419e9-130">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="419e9-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="419e9-131">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="419e9-131">established connection failed because connected host has</span></span>

<span data-ttu-id="419e9-132">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="419e9-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="419e9-133">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="419e9-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="419e9-134">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="419e9-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="419e9-135">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="419e9-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="419e9-136">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="419e9-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="419e9-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="419e9-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="419e9-138">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="419e9-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="419e9-139">Estas son algunas de las razones comunes por las que **Test-CsExStorageNotification** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="419e9-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="419e9-140">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="419e9-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="419e9-141">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="419e9-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="419e9-142">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="419e9-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="419e9-143">Este comando fallará si Microsoft Exchange Server está mal configurado o aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="419e9-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="419e9-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="419e9-144">See Also</span></span>


[<span data-ttu-id="419e9-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="419e9-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

