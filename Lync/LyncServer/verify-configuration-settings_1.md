---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="f1616-102">Comprobación de los parámetros de configuración</span><span class="sxs-lookup"><span data-stu-id="f1616-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1616-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f1616-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f1616-104">Después de combinar la topología y ejecutar el cmdlet **Import-CsLegacyConfiguration** , compruebe que las directivas y la configuración de Office Communications Server 2007 R2 se han importado a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1616-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="f1616-105">En la tabla siguiente se enumeran las directivas y la configuración que debe comprobar.</span><span class="sxs-lookup"><span data-stu-id="f1616-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="f1616-106">Directivas y configuración para comprobar después de la migración</span><span class="sxs-lookup"><span data-stu-id="f1616-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1616-107">Si usa esta carga de trabajo:</span><span class="sxs-lookup"><span data-stu-id="f1616-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="f1616-108">Compruebe estas directivas y la configuración:</span><span class="sxs-lookup"><span data-stu-id="f1616-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1616-109">Mensajería instantánea (mi) y Conferencia</span><span class="sxs-lookup"><span data-stu-id="f1616-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="f1616-110">Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="f1616-110">Presence policy</span></span></p>
<p><span data-ttu-id="f1616-111">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="f1616-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-112">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="f1616-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f1616-113">Números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="f1616-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="f1616-114">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="f1616-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-115">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="f1616-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f1616-116">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f1616-116">Voice policy</span></span></p>
<p><span data-ttu-id="f1616-117">Rutas de voz</span><span class="sxs-lookup"><span data-stu-id="f1616-117">Voice routes</span></span></p>
<p><span data-ttu-id="f1616-118">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="f1616-118">Dial plans</span></span></p>
<p><span data-ttu-id="f1616-119">Configuración de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="f1616-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="f1616-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="f1616-121">Direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="f1616-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-122">Usuarios externos</span><span class="sxs-lookup"><span data-stu-id="f1616-122">External users</span></span></p></td>
<td><p><span data-ttu-id="f1616-123">Directivas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="f1616-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-124">Archivado</span><span class="sxs-lookup"><span data-stu-id="f1616-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="f1616-125">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="f1616-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="f1616-126">Para comprobar las directivas y la configuración</span><span class="sxs-lookup"><span data-stu-id="f1616-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="f1616-127">En el entorno de Office Communications Server 2007 R2, tome nota de los nombres de los planes de marcado (anteriormente conocidos como perfiles de ubicación), números de acceso telefónico local (números de teléfono y regiones de acceso al operador de conferencias), rutas de voz y las directivas que aparecen en la lista tabla anterior, además de las direcciones URL que se usan para Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="f1616-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="f1616-128">En el servidor front-end de Lync Server 2013, abra el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1616-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f1616-129">Para comprobar las directivas de conferencia importadas, en el panel izquierdo, haga clic en **conferencias**, en **Directiva de conferencia**y, a continuación, compruebe que todas las directivas de conferencia del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1616-130">La Directiva de <STRONG>reunión</STRONG> de las versiones anteriores de Office Communications Server ahora se conoce como la Directiva de conferencia en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1616-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="f1616-131">Además, la configuración <STRONG>Particpants anónima</STRONG> de versiones anteriores de Office Communications Server es ahora una configuración de la Directiva de conferencia de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1616-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1616-132">En Office Communications Server 2007 R2, si la Directiva de conferencia no está configurada para <STRONG>usarse por usuario</STRONG>, solo se importa la configuración de directiva global.</span><span class="sxs-lookup"><span data-stu-id="f1616-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="f1616-133">En esta situación no se importa ninguna otra política de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f1616-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1616-134">Si los <STRONG>participantes anónimos</STRONG> están configurados para <STRONG>exigir el cumplimiento de cada usuario</STRONG> en su Directiva de conferencia de Office Communications Server 2007 R2, durante la migración se crean dos directivas de Conferencia: una con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecido en <STRONG>true</STRONG> y otra con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecido en <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f1616-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="f1616-135">Para comprobar los planes de marcado importados, haga clic en **enrutamiento de voz**, haga clic en **plan de marcado**y compruebe que todos los planes de marcado en el entorno de Office Communicator 2007 R2 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1616-136">En Lync Server 2013, los <STRONG>perfiles de ubicación</STRONG> se conocen ahora como <STRONG>planes de marcado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f1616-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="f1616-137">Para comprobar las directivas de voz importadas, haga clic en **enrutamiento de voz**, en **Directiva de voz**y, a continuación, compruebe que todas las directivas de voz del entorno de Office Communicator 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1616-138">Si la Directiva de voz no está configurada para <STRONG>usarse por usuario</STRONG> en el entorno de Office Communications Server 2007 R2, solo se importan las opciones de directiva global.</span><span class="sxs-lookup"><span data-stu-id="f1616-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="f1616-139">No se importa ninguna otra política de voz en esta situación.</span><span class="sxs-lookup"><span data-stu-id="f1616-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="f1616-140">Para comprobar las rutas de voz importadas, haga clic en **enrutamiento de voz**, en **ruta**y, a continuación, compruebe que todas las rutas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="f1616-141">Para comprobar la configuración de uso de RTC importada, haga clic en **enrutamiento de voz**, haga clic en **uso de RTC**y compruebe que la configuración de uso de RTC del entorno de Office Communicator 2007 R2 esté incluida en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="f1616-142">Para comprobar las directivas de acceso externo importadas, haga clic en **Federación y acceso externo**, haga clic en **Directiva de acceso externo**y compruebe que todas las directivas de acceso externas de su entorno de Office Communicator 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="f1616-143">Para comprobar las directivas de archivado, haga clic en **supervisión y archivado**, haga clic en **Directiva de archivado**y compruebe que todas las directivas de archivado del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f1616-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="f1616-144">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1616-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="f1616-145">Para comprobar las directivas de presencia, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1616-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="f1616-146">Al mirar el nombre en el parámetro **Identity** , compruebe que se han importado todas las directivas de presencia en el entorno de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f1616-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="f1616-147">Para comprobar las directivas y la configuración mediante cmdlets</span><span class="sxs-lookup"><span data-stu-id="f1616-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="f1616-148">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1616-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f1616-149">Ejecute los cmdlets de la tabla siguiente para comprobar las directivas y la configuración.</span><span class="sxs-lookup"><span data-stu-id="f1616-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="f1616-150">La sintaxis de estos cmdlets es como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1616-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="f1616-151">Para obtener más información sobre estos cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f1616-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1616-152">Para esta Directiva o configuración:</span><span class="sxs-lookup"><span data-stu-id="f1616-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="f1616-153">Use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1616-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1616-154">Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="f1616-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="f1616-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-156">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="f1616-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="f1616-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-158">Números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="f1616-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="f1616-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-160">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="f1616-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="f1616-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-162">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="f1616-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="f1616-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-164">Rutas de voz</span><span class="sxs-lookup"><span data-stu-id="f1616-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="f1616-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-166">Uso de RTC</span><span class="sxs-lookup"><span data-stu-id="f1616-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="f1616-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-168">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="f1616-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="f1616-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1616-170">Directivas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="f1616-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="f1616-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1616-172">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="f1616-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="f1616-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f1616-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

