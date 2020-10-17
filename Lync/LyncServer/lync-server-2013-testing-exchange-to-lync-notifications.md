---
title: 'Lync Server 2013: pruebas de Exchange a las notificaciones de Lync'
description: 'Lync Server 2013: pruebas de Exchange a las notificaciones de Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560626"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="efb3f-103">Prueba de las notificaciones de Exchange para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb3f-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efb3f-104">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="efb3f-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efb3f-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="efb3f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="efb3f-106">Diario</span><span class="sxs-lookup"><span data-stu-id="efb3f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb3f-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="efb3f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="efb3f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efb3f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb3f-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="efb3f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="efb3f-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="efb3f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="efb3f-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="efb3f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="efb3f-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="efb3f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="efb3f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb3f-113">Description</span></span>

<span data-ttu-id="efb3f-114">El cmdlet **Test-CsExStorageNotification** se usa para comprobar que el servicio de notificación de Microsoft Exchange Server 2013 puede notificar a Lync Server 2013 en cualquier momento en que se realicen actualizaciones en la lista de contactos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="efb3f-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="efb3f-115">Este cmdlet solo es válido si usa el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="efb3f-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="efb3f-116">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="efb3f-116">Running the test</span></span>

<span data-ttu-id="efb3f-117">El comando que se muestra en el ejemplo 1 comprueba si el servicio de almacenamiento de Lync Server puede conectarse al servicio de notificación de buzones de Microsoft Exchange Server para el usuario sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="efb3f-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="efb3f-118">En este ejemplo, se utiliza NetNamedPipe como vínculo WCF.</span><span class="sxs-lookup"><span data-stu-id="efb3f-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="efb3f-119">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="efb3f-119">Determining success or failure</span></span>

<span data-ttu-id="efb3f-120">Si la integración de Exchange está configurada correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:</span><span class="sxs-lookup"><span data-stu-id="efb3f-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="efb3f-121">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efb3f-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efb3f-122">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="efb3f-122">Result : Success</span></span>

<span data-ttu-id="efb3f-123">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="efb3f-123">Latency : 00:00:00</span></span>

<span data-ttu-id="efb3f-124">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="efb3f-124">Error Message :</span></span>

<span data-ttu-id="efb3f-125">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="efb3f-125">Diagnosis :</span></span>

<span data-ttu-id="efb3f-126">Si el usuario especificado no puede recibir notificaciones, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="efb3f-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="efb3f-127">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efb3f-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efb3f-128">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="efb3f-128">Result : Failure</span></span>

<span data-ttu-id="efb3f-129">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="efb3f-129">Latency : 00:00:00</span></span>

<span data-ttu-id="efb3f-130">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="efb3f-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="efb3f-131">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="efb3f-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="efb3f-132">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="efb3f-132">established connection failed because connected host has</span></span>

<span data-ttu-id="efb3f-133">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="efb3f-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="efb3f-134">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="efb3f-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="efb3f-135">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="efb3f-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="efb3f-136">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="efb3f-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="efb3f-137">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="efb3f-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="efb3f-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="efb3f-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="efb3f-139">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="efb3f-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="efb3f-140">Estas son algunas de las razones comunes por las que **Test-CsExStorageNotification** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="efb3f-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="efb3f-141">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="efb3f-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="efb3f-142">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="efb3f-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="efb3f-143">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="efb3f-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="efb3f-144">Este comando producirá un error si Microsoft Exchange Server está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="efb3f-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efb3f-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efb3f-145">See Also</span></span>


[<span data-ttu-id="efb3f-146">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="efb3f-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

