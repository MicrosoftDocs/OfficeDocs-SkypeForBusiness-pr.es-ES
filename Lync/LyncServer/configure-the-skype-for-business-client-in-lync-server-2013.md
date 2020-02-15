---
title: Configurar el cliente de Skype empresarial en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd70d0f37dbed8a38994af6dc806556380484b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="77fc5-102">Configurar la experiencia de cliente con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77fc5-103">_**Última modificación del tema:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="77fc5-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="77fc5-104">**Resumen:** En este tema se describe cómo configurar la experiencia de cliente para los usuarios del cliente de Skype empresarial en un entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77fc5-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="77fc5-105">Puede configurar la experiencia de cliente solo si está ejecutando Lync Server 2013 con la actualización acumulativa de diciembre de 2014 (5.0.8308.857) o una versión posterior instalada.</span><span class="sxs-lookup"><span data-stu-id="77fc5-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="77fc5-106">Para obtener información acerca de la actualización de Lync Server 2013, consulte [actualizaciones para Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="77fc5-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="77fc5-107">Skype empresarial proporciona una nueva experiencia de usuario que se basa en la experiencia del producto de consumo de Skype.</span><span class="sxs-lookup"><span data-stu-id="77fc5-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="77fc5-108">Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados e iconos conocidos.</span><span class="sxs-lookup"><span data-stu-id="77fc5-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="77fc5-109">Para obtener información detallada sobre la nueva experiencia del cliente, consulte [Lync ahora es Skype empresarial: vea](http://go.microsoft.com/fwlink/?linkid=529022)las novedades.</span><span class="sxs-lookup"><span data-stu-id="77fc5-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="77fc5-110">Lync Server 2013 admite la nueva experiencia de cliente de Skype empresarial y la experiencia de cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="77fc5-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="77fc5-111">Como administrador, puede elegir la experiencia de cliente preferida para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="77fc5-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="77fc5-112">Por ejemplo, es posible que desee implementar la experiencia del cliente de Lync hasta que los usuarios de su organización se hayan entrenado completamente en la nueva experiencia de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="77fc5-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="77fc5-113">O bien, si aún no ha actualizado todos los usuarios a Skype empresarial Server 2015, es posible que quiera que todos los usuarios tengan la misma experiencia de cliente hasta que se actualicen todos al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="77fc5-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77fc5-114">Si su organización tiene implementado tanto Skype empresarial Server 2015 como Lync Server 2013, la experiencia de cliente predeterminada será distinta en función de las versiones del servidor y la configuración de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="77fc5-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="77fc5-115">Cuando los usuarios inicien Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la interfaz de usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="77fc5-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="77fc5-116">Después de varios minutos, se pide a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="77fc5-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="77fc5-117">Para obtener más información, vea <STRONG>comportamiento del cliente del primer inicio</STRONG> más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="77fc5-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="77fc5-118">La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016.</span><span class="sxs-lookup"><span data-stu-id="77fc5-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="77fc5-119">Antes de intentar configurar el entorno del cliente para usar el cliente Lync 2013, Compruebe la versión del cliente para asegurarse de que no empieza con el número 16; por ejemplo: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="77fc5-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="77fc5-120">Configurar la experiencia del cliente</span><span class="sxs-lookup"><span data-stu-id="77fc5-120">Configure the client experience</span></span>

<span data-ttu-id="77fc5-121">Puede especificar la experiencia de cliente que verán los usuarios de la organización mediante el cmdlet **set-CSClientPolicy** con el parámetro EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="77fc5-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="77fc5-122">El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios de la organización afectados por la directiva global (Recuerde que las directivas específicas de sitio o usuario invalidan la directiva global):</span><span class="sxs-lookup"><span data-stu-id="77fc5-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="77fc5-123">El siguiente comando selecciona la experiencia del cliente Lync para todos los usuarios de su organización afectados por la directiva global:</span><span class="sxs-lookup"><span data-stu-id="77fc5-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="77fc5-124">El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios del sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="77fc5-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="77fc5-125">Si desea configurar la experiencia de cliente para determinados usuarios de la organización, puede crear una nueva Directiva de usuario con el cmdlet **New-CsClientPolicy** y, a continuación, asignar la Directiva a usuarios específicos mediante el cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="77fc5-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="77fc5-126">Por ejemplo, el siguiente comando crea una nueva Directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="77fc5-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="77fc5-127">El comando siguiente asigna la Directiva, SalesClientUI, a todos los miembros del Departamento de ventas:</span><span class="sxs-lookup"><span data-stu-id="77fc5-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="77fc5-128">Comportamiento del primer inicio del cliente</span><span class="sxs-lookup"><span data-stu-id="77fc5-128">First launch client behaviors</span></span>

<span data-ttu-id="77fc5-129">De forma predeterminada, cuando los usuarios inician Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False como se describió anteriormente. .</span><span class="sxs-lookup"><span data-stu-id="77fc5-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="77fc5-130">Después de varios minutos, se le pedirá a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="77fc5-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="77fc5-131">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inicien el cliente de Skype empresarial por primera vez, siga estos pasos antes de que se inicie el cliente por primera vez tras la actualización:</span><span class="sxs-lookup"><span data-stu-id="77fc5-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="77fc5-132">Confirme que el valor de `EnableSkypeUI` se establece en $false en la Directiva que está usando como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="77fc5-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="77fc5-133">Actualice el registro del sistema en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="77fc5-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="77fc5-134">Debe hacer esto antes de la primera vez que los usuarios inicien el cliente de Skype empresarial y debe hacerlo solo una vez.</span><span class="sxs-lookup"><span data-stu-id="77fc5-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="77fc5-135">Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, vea la sección más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="77fc5-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="77fc5-136">En la clave del \*\* \[software\\\\de usuario\\actual\\\_\_de\] HKEY Microsoft Office Lync\*\* , cree un nuevo valor **binario** .</span><span class="sxs-lookup"><span data-stu-id="77fc5-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="77fc5-137">El **nombre del valor** debe ser **EnableSkypeUI**y los **datos del valor** deben establecerse en **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="77fc5-138">La clave debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="77fc5-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="77fc5-139">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente de Skype empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="77fc5-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="77fc5-140">Controlar la visualización del tutorial de la pantalla de bienvenida</span><span class="sxs-lookup"><span data-stu-id="77fc5-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="77fc5-141">Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 Sugerencias rápidas que la mayoría de las personas solicitan*.</span><span class="sxs-lookup"><span data-stu-id="77fc5-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="77fc5-142">Puede desactivar la pantalla de bienvenida pero seguir permitiendo a los usuarios obtener acceso al tutorial agregando el siguiente valor del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="77fc5-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="77fc5-143">En la clave de \*\* \[Microsoft\_\_\\\\Office\\\\15,0\\Lync\] del software HKEY current user\*\* , cree un nuevo **valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="77fc5-144">El **nombre del valor** debe ser **isbasictutorialseenbyusery**y los **datos del valor** deben establecerse en **1**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="77fc5-145">La clave debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="77fc5-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="77fc5-146">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="77fc5-146">Turn off the client tutorial</span></span>

<span data-ttu-id="77fc5-147">Si no desea que los usuarios puedan obtener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor del registro:</span><span class="sxs-lookup"><span data-stu-id="77fc5-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="77fc5-148">En la clave de \*\* \[Microsoft\_\_\\\\Office\\\\15,0\\Lync\] del software HKEY current user\*\* , cree un nuevo **valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="77fc5-149">El **nombre del valor** debe ser **tutorialfeatureenabledy**y los **datos del valor** deben establecerse en **0**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="77fc5-150">Puede volver a activar el tutorial si establece los **datos del valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="77fc5-151">Experiencias de cliente predeterminadas</span><span class="sxs-lookup"><span data-stu-id="77fc5-151">Default client experiences</span></span>

<span data-ttu-id="77fc5-152">Si su organización tiene instalado Skype empresarial Server 2015 y Lync Server, la experiencia del cliente será distinta en función de las versiones del servidor y de la configuración de la interfaz de usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="77fc5-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="77fc5-153">En la siguiente tabla se muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="77fc5-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="77fc5-154">Versión del servidor</span><span class="sxs-lookup"><span data-stu-id="77fc5-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="77fc5-155">Configuración de EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="77fc5-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="77fc5-156">Experiencia de cliente</span><span class="sxs-lookup"><span data-stu-id="77fc5-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-157">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="77fc5-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="77fc5-158">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77fc5-158">Default</span></span></p></td>
<td><p><span data-ttu-id="77fc5-159">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77fc5-160">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="77fc5-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="77fc5-161">True</span><span class="sxs-lookup"><span data-stu-id="77fc5-161">True</span></span></p></td>
<td><p><span data-ttu-id="77fc5-162">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-163">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="77fc5-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="77fc5-164">False</span><span class="sxs-lookup"><span data-stu-id="77fc5-164">False</span></span></p></td>
<td><p><span data-ttu-id="77fc5-165">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="77fc5-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77fc5-166">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="77fc5-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-167">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77fc5-167">Default</span></span></p></td>
<td><p><span data-ttu-id="77fc5-168">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="77fc5-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-169">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="77fc5-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-170">True</span><span class="sxs-lookup"><span data-stu-id="77fc5-170">True</span></span></p></td>
<td><p><span data-ttu-id="77fc5-171">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77fc5-172">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="77fc5-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-173">False</span><span class="sxs-lookup"><span data-stu-id="77fc5-173">False</span></span></p></td>
<td><p><span data-ttu-id="77fc5-174">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="77fc5-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-175">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="77fc5-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-176">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77fc5-176">Default</span></span></p></td>
<td><p><span data-ttu-id="77fc5-177">El usuario solicitó cambiar a la experiencia de cliente de Lync (el usuario no puede cambiar a Skype empresarial más adelante)</span><span class="sxs-lookup"><span data-stu-id="77fc5-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77fc5-178">La siguiente tabla muestra la experiencia de cliente cuando el administrador cambia la configuración inicial para la experiencia de la interfaz de usuario de Skype:</span><span class="sxs-lookup"><span data-stu-id="77fc5-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="77fc5-179">Versión del servidor</span><span class="sxs-lookup"><span data-stu-id="77fc5-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="77fc5-180">Configuración de UI de Skype</span><span class="sxs-lookup"><span data-stu-id="77fc5-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="77fc5-181">Interfaz de usuario de cliente = Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="77fc5-182">Interfaz de usuario de cliente = Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-183">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="77fc5-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="77fc5-184">True</span><span class="sxs-lookup"><span data-stu-id="77fc5-184">True</span></span></p></td>
<td><p><span data-ttu-id="77fc5-185">El usuario solicitó cambiar a Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="77fc5-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77fc5-187">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="77fc5-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="77fc5-188">False</span><span class="sxs-lookup"><span data-stu-id="77fc5-188">False</span></span></p></td>
<td><p><span data-ttu-id="77fc5-189">Interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="77fc5-190">El usuario solicitó cambiar a la interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-191">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="77fc5-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-192">True</span><span class="sxs-lookup"><span data-stu-id="77fc5-192">True</span></span></p></td>
<td><p><span data-ttu-id="77fc5-193">El usuario solicitó cambiar a Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="77fc5-194">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77fc5-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77fc5-195">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="77fc5-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-196">False</span><span class="sxs-lookup"><span data-stu-id="77fc5-196">False</span></span></p></td>
<td><p><span data-ttu-id="77fc5-197">Interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="77fc5-198">El usuario solicitó cambiar a la interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77fc5-199">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="77fc5-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-200">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77fc5-200">Default</span></span></p></td>
<td><p><span data-ttu-id="77fc5-201">Modo Lync (no se puede cambiar a Skype empresarial)</span><span class="sxs-lookup"><span data-stu-id="77fc5-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="77fc5-202">Interfaz de usuario de Lync (no se puede cambiar a Skype empresarial)</span><span class="sxs-lookup"><span data-stu-id="77fc5-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77fc5-203">Las versiones de revisión necesarias para administrar la configuración del cliente de Skype empresarial son:</span><span class="sxs-lookup"><span data-stu-id="77fc5-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="77fc5-204">Lync Server 2010-actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="77fc5-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="77fc5-205">Para obtener más información, consulte [actualizaciones para Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="77fc5-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="77fc5-206">Lync Server 2013-actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77fc5-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="77fc5-207">Para obtener más información, consulte [actualizaciones para Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="77fc5-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="77fc5-208">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="77fc5-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="77fc5-209">La actualización del registro para mostrar la experiencia del cliente de Lync la primera vez que un usuario inicia el cliente de Skype empresarial solo debe realizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="77fc5-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="77fc5-210">Si usa un objeto de directiva de grupo (GPO) para actualizar el registro, debe definir el objeto para crear un nuevo valor en lugar de actualizar los datos del valor.</span><span class="sxs-lookup"><span data-stu-id="77fc5-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="77fc5-211">Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="77fc5-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="77fc5-212">El siguiente procedimiento describe cómo modificar el registro para que la experiencia de cliente de Lync se muestre la primera vez que un usuario inicie Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="77fc5-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="77fc5-213">También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de bienvenida como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="77fc5-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="77fc5-214">**Para crear el GPO**</span><span class="sxs-lookup"><span data-stu-id="77fc5-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="77fc5-215">Inicie la **consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="77fc5-216">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [consola de administración de directivas de grupo](http://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="77fc5-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="77fc5-217">Haga clic con el botón secundario en el nodo **objetos de directiva de grupo** y seleccione **nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="77fc5-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="77fc5-218">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el GPO, por ejemplo, **makelyncdefaultuiy**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="77fc5-219">Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, a continuación, seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="77fc5-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="77fc5-220">En el **Editor de administración de directivas de grupo**, expanda **configuración de usuario**, **Opciones**, expanda **configuración de Windows**y, a continuación, seleccione el nodo **registro** .</span><span class="sxs-lookup"><span data-stu-id="77fc5-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="77fc5-221">Haga clic con el botón secundario en el nodo **registro** y seleccione **nuevo** \> **elemento del registro**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="77fc5-222">En el cuadro de diálogo **nuevas propiedades del registro** , actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77fc5-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="77fc5-223">Campo</span><span class="sxs-lookup"><span data-stu-id="77fc5-223">Field</span></span></th>
    <th><span data-ttu-id="77fc5-224">Valor para seleccionar o escribir</span><span class="sxs-lookup"><span data-stu-id="77fc5-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="77fc5-225"><strong>Acción</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-226"><strong>Crear</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="77fc5-227"><strong>Subárbol</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="77fc5-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="77fc5-229"><strong>Ruta de acceso de la clave</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="77fc5-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="77fc5-231"><strong>Nombre del valor</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="77fc5-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="77fc5-233"><strong>Tipo de valor</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="77fc5-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="77fc5-235"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="77fc5-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="77fc5-236">00000000</span><span class="sxs-lookup"><span data-stu-id="77fc5-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="77fc5-237">Haga clic en **Aceptar** para guardar los cambios y, a continuación, cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="77fc5-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="77fc5-238">A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la Directiva, como una unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="77fc5-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="77fc5-239">**Para usar el GPO para asignar la Directiva**</span><span class="sxs-lookup"><span data-stu-id="77fc5-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="77fc5-240">En la consola de administración de directivas de grupo, haga clic con el botón secundario en la unidad organizativa a la que desea asignar la Directiva y, a continuación, seleccione **vincular a un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="77fc5-241">En el cuadro de diálogo **seleccionar GPO** , seleccione el GPO que ha creado y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77fc5-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="77fc5-242">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="77fc5-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="77fc5-243">**GPUpdate/target: usuario**</span><span class="sxs-lookup"><span data-stu-id="77fc5-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="77fc5-244">El mensaje "actualizando la Directiva..." se muestra mientras se aplica el GPO.</span><span class="sxs-lookup"><span data-stu-id="77fc5-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="77fc5-245">Una vez completado, se muestra el mensaje "la actualización de la Directiva de usuario se ha completado correctamente".</span><span class="sxs-lookup"><span data-stu-id="77fc5-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="77fc5-246">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="77fc5-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="77fc5-247">**Gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="77fc5-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="77fc5-248">Debe ver "objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.</span><span class="sxs-lookup"><span data-stu-id="77fc5-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="77fc5-249">También puede comprobar que el GPO haya actualizado correctamente el registro en el equipo del usuario examinando el registro.</span><span class="sxs-lookup"><span data-stu-id="77fc5-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="77fc5-250">Abra el editor del registro y vaya a la clave de \*\* \[Microsoft\\Office\\Lync\] del software\_\_\\\\HKEY current user\*\* .</span><span class="sxs-lookup"><span data-stu-id="77fc5-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="77fc5-251">Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="77fc5-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

