---
title: Configurar el cliente de Skype empresarial en Lync Server 2013
description: Configure el cliente de Skype empresarial en Lync Server 2013.
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
ms.openlocfilehash: c7f75ae0fa61d9048991934a0ecce7a886079961
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542976"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="5d89e-103">Configurar la experiencia de cliente con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-103">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d89e-104">_**Última modificación del tema:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="5d89e-104">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="5d89e-105">**Resumen:** En este tema se describe cómo configurar la experiencia de cliente para los usuarios del cliente de Skype empresarial en un entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d89e-105">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="5d89e-106">Puede configurar la experiencia de cliente solo si está ejecutando Lync Server 2013 con la actualización acumulativa de diciembre de 2014 (5.0.8308.857) o una versión posterior instalada.</span><span class="sxs-lookup"><span data-stu-id="5d89e-106">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="5d89e-107">Para obtener información acerca de la actualización de Lync Server 2013, consulte [actualizaciones para Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="5d89e-107">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="5d89e-108">Skype empresarial proporciona una nueva experiencia de usuario que se basa en la experiencia del producto de consumo de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d89e-108">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="5d89e-109">Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados e iconos conocidos.</span><span class="sxs-lookup"><span data-stu-id="5d89e-109">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="5d89e-110">Para obtener información detallada sobre la nueva experiencia del cliente, consulte [Lync ahora es Skype empresarial: vea](https://go.microsoft.com/fwlink/?linkid=529022)las novedades.</span><span class="sxs-lookup"><span data-stu-id="5d89e-110">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="5d89e-111">Lync Server 2013 admite la nueva experiencia de cliente de Skype empresarial y la experiencia de cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="5d89e-111">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="5d89e-112">Como administrador, puede elegir la experiencia de cliente preferida para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5d89e-112">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="5d89e-113">Por ejemplo, es posible que desee implementar la experiencia del cliente de Lync hasta que los usuarios de su organización se hayan entrenado completamente en la nueva experiencia de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d89e-113">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="5d89e-114">O bien, si aún no ha actualizado todos los usuarios a Skype empresarial Server 2015, es posible que quiera que todos los usuarios tengan la misma experiencia de cliente hasta que se actualicen todos al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="5d89e-114">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5d89e-115">Si su organización tiene implementado tanto Skype empresarial Server 2015 como Lync Server 2013, la experiencia de cliente predeterminada será distinta en función de las versiones del servidor y la configuración de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5d89e-115">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="5d89e-116">Cuando los usuarios inicien Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la interfaz de usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="5d89e-116">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="5d89e-117">Después de varios minutos, se pide a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="5d89e-117">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="5d89e-118">Para obtener más información, vea <STRONG>comportamiento del cliente del primer inicio</STRONG> más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="5d89e-118">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5d89e-119">La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016.</span><span class="sxs-lookup"><span data-stu-id="5d89e-119">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="5d89e-120">Antes de intentar configurar el entorno del cliente para usar el cliente Lync 2013, Compruebe la versión del cliente para asegurarse de que no empieza con el número 16; por ejemplo: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="5d89e-120">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="5d89e-121">Configurar la experiencia del cliente</span><span class="sxs-lookup"><span data-stu-id="5d89e-121">Configure the client experience</span></span>

<span data-ttu-id="5d89e-122">Puede especificar la experiencia de cliente que verán los usuarios de la organización mediante el cmdlet **set-CSClientPolicy** con el parámetro EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="5d89e-122">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="5d89e-123">El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios de la organización afectados por la directiva global (Recuerde que las directivas específicas de sitio o usuario invalidan la directiva global):</span><span class="sxs-lookup"><span data-stu-id="5d89e-123">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="5d89e-124">El siguiente comando selecciona la experiencia del cliente Lync para todos los usuarios de su organización afectados por la directiva global:</span><span class="sxs-lookup"><span data-stu-id="5d89e-124">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="5d89e-125">El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios del sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="5d89e-125">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="5d89e-126">Si desea configurar la experiencia de cliente para determinados usuarios de la organización, puede crear una nueva Directiva de usuario con el cmdlet **New-CsClientPolicy** y, a continuación, asignar la Directiva a usuarios específicos mediante el cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5d89e-126">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="5d89e-127">Por ejemplo, el siguiente comando crea una nueva Directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="5d89e-127">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="5d89e-128">El comando siguiente asigna la Directiva, SalesClientUI, a todos los miembros del Departamento de ventas:</span><span class="sxs-lookup"><span data-stu-id="5d89e-128">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="5d89e-129">Comportamiento del primer inicio del cliente</span><span class="sxs-lookup"><span data-stu-id="5d89e-129">First launch client behaviors</span></span>

<span data-ttu-id="5d89e-130">De forma predeterminada, cuando los usuarios inician Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d89e-130">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="5d89e-131">Después de varios minutos, se le pedirá a los usuarios que cambien al modo Lync.</span><span class="sxs-lookup"><span data-stu-id="5d89e-131">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="5d89e-132">Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inicien el cliente de Skype empresarial por primera vez, siga estos pasos antes de que se inicie el cliente por primera vez tras la actualización:</span><span class="sxs-lookup"><span data-stu-id="5d89e-132">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="5d89e-133">Confirme que el valor de `EnableSkypeUI` se establece en $false en la Directiva que está usando como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d89e-133">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="5d89e-134">Actualice el registro del sistema en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="5d89e-134">Update the system registry on the user's computer.</span></span> <span data-ttu-id="5d89e-135">Debe hacer esto antes de la primera vez que los usuarios inicien el cliente de Skype empresarial y debe hacerlo solo una vez.</span><span class="sxs-lookup"><span data-stu-id="5d89e-135">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="5d89e-136">Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, vea la sección más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="5d89e-136">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="5d89e-137">En la clave del \*\* \[ \_ software de usuario actual de HKEY \_ \\ \\ Microsoft \\ Office \\ Lync \] \*\* , cree un nuevo valor **binario** .</span><span class="sxs-lookup"><span data-stu-id="5d89e-137">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="5d89e-138">El **nombre del valor** debe ser **EnableSkypeUI**y los **datos del valor** deben establecerse en **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-138">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="5d89e-139">La clave debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d89e-139">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="5d89e-140">La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente de Skype empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5d89e-140">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="5d89e-141">Controlar la visualización del tutorial de la pantalla de bienvenida</span><span class="sxs-lookup"><span data-stu-id="5d89e-141">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="5d89e-142">Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 Sugerencias rápidas que la mayoría de las personas solicitan*.</span><span class="sxs-lookup"><span data-stu-id="5d89e-142">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="5d89e-143">Puede desactivar la pantalla de bienvenida pero seguir permitiendo a los usuarios obtener acceso al tutorial agregando el siguiente valor del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="5d89e-143">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="5d89e-144">En la clave de \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] del software HKEY current user\*\* , cree un nuevo **valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-144">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5d89e-145">El **nombre del valor** debe ser **isbasictutorialseenbyusery**y los **datos del valor** deben establecerse en **1**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-145">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="5d89e-146">La clave debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d89e-146">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="5d89e-147">Desactivar el tutorial del cliente</span><span class="sxs-lookup"><span data-stu-id="5d89e-147">Turn off the client tutorial</span></span>

<span data-ttu-id="5d89e-148">Si no desea que los usuarios puedan obtener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor del registro:</span><span class="sxs-lookup"><span data-stu-id="5d89e-148">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="5d89e-149">En la clave de \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] del software HKEY current user\*\* , cree un nuevo **valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-149">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="5d89e-150">El **nombre del valor** debe ser **tutorialfeatureenabledy**y los **datos del valor** deben establecerse en **0**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-150">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="5d89e-151">Puede volver a activar el tutorial si establece los **datos del valor** en **1**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-151">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="5d89e-152">Experiencias de cliente predeterminadas</span><span class="sxs-lookup"><span data-stu-id="5d89e-152">Default client experiences</span></span>

<span data-ttu-id="5d89e-153">Si su organización tiene instalado Skype empresarial Server 2015 y Lync Server, la experiencia del cliente será distinta en función de las versiones del servidor y de la configuración de la interfaz de usuario de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d89e-153">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="5d89e-154">En la siguiente tabla se muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="5d89e-154">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5d89e-155">Versión del servidor</span><span class="sxs-lookup"><span data-stu-id="5d89e-155">Server version</span></span></p></th>
<th><p><span data-ttu-id="5d89e-156">Configuración de EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5d89e-156">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="5d89e-157">Experiencia de cliente</span><span class="sxs-lookup"><span data-stu-id="5d89e-157">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-158">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d89e-158">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5d89e-159">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5d89e-159">Default</span></span></p></td>
<td><p><span data-ttu-id="5d89e-160">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-160">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d89e-161">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d89e-161">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5d89e-162">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5d89e-162">True</span></span></p></td>
<td><p><span data-ttu-id="5d89e-163">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-163">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-164">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d89e-164">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5d89e-165">False</span><span class="sxs-lookup"><span data-stu-id="5d89e-165">False</span></span></p></td>
<td><p><span data-ttu-id="5d89e-166">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5d89e-166">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d89e-167">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5d89e-167">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-168">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5d89e-168">Default</span></span></p></td>
<td><p><span data-ttu-id="5d89e-169">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5d89e-169">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-170">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5d89e-170">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-171">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5d89e-171">True</span></span></p></td>
<td><p><span data-ttu-id="5d89e-172">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-172">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d89e-173">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5d89e-173">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-174">False</span><span class="sxs-lookup"><span data-stu-id="5d89e-174">False</span></span></p></td>
<td><p><span data-ttu-id="5d89e-175">El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</span><span class="sxs-lookup"><span data-stu-id="5d89e-175">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-176">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="5d89e-176">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-177">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5d89e-177">Default</span></span></p></td>
<td><p><span data-ttu-id="5d89e-178">El usuario solicitó cambiar a la experiencia de cliente de Lync (el usuario no puede cambiar a Skype empresarial más adelante)</span><span class="sxs-lookup"><span data-stu-id="5d89e-178">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5d89e-179">La siguiente tabla muestra la experiencia de cliente cuando el administrador cambia la configuración inicial para la experiencia de la interfaz de usuario de Skype:</span><span class="sxs-lookup"><span data-stu-id="5d89e-179">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5d89e-180">Versión del servidor</span><span class="sxs-lookup"><span data-stu-id="5d89e-180">Server version</span></span></p></th>
<th><p><span data-ttu-id="5d89e-181">Configuración de UI de Skype</span><span class="sxs-lookup"><span data-stu-id="5d89e-181">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="5d89e-182">Interfaz de usuario de cliente = Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-182">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="5d89e-183">Interfaz de usuario de cliente = Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-183">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-184">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d89e-184">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5d89e-185">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5d89e-185">True</span></span></p></td>
<td><p><span data-ttu-id="5d89e-186">El usuario solicitó cambiar a Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-186">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5d89e-187">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-187">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d89e-188">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d89e-188">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="5d89e-189">False</span><span class="sxs-lookup"><span data-stu-id="5d89e-189">False</span></span></p></td>
<td><p><span data-ttu-id="5d89e-190">Interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-190">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5d89e-191">El usuario solicitó cambiar a la interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-191">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-192">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5d89e-192">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-193">Verdadero</span><span class="sxs-lookup"><span data-stu-id="5d89e-193">True</span></span></p></td>
<td><p><span data-ttu-id="5d89e-194">El usuario solicitó cambiar a Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-194">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="5d89e-195">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5d89e-195">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d89e-196">Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</span><span class="sxs-lookup"><span data-stu-id="5d89e-196">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-197">False</span><span class="sxs-lookup"><span data-stu-id="5d89e-197">False</span></span></p></td>
<td><p><span data-ttu-id="5d89e-198">Interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-198">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="5d89e-199">El usuario solicitó cambiar a la interfaz de usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-199">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d89e-200">Lync Server 2010 o Lync Server 2013 (sin revisiones)</span><span class="sxs-lookup"><span data-stu-id="5d89e-200">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-201">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="5d89e-201">Default</span></span></p></td>
<td><p><span data-ttu-id="5d89e-202">Modo Lync (no se puede cambiar a Skype empresarial)</span><span class="sxs-lookup"><span data-stu-id="5d89e-202">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="5d89e-203">Interfaz de usuario de Lync (no se puede cambiar a Skype empresarial)</span><span class="sxs-lookup"><span data-stu-id="5d89e-203">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5d89e-204">Las versiones de revisión necesarias para administrar la configuración del cliente de Skype empresarial son:</span><span class="sxs-lookup"><span data-stu-id="5d89e-204">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="5d89e-205">Lync Server 2010-actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5d89e-205">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="5d89e-206">Para obtener más información, consulte [actualizaciones para Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="5d89e-206">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="5d89e-207">Lync Server 2013-actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d89e-207">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="5d89e-208">Para obtener más información, consulte [actualizaciones para Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="5d89e-208">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="5d89e-209">Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio</span><span class="sxs-lookup"><span data-stu-id="5d89e-209">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="5d89e-210">La actualización del registro para mostrar la experiencia del cliente de Lync la primera vez que un usuario inicia el cliente de Skype empresarial solo debe realizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="5d89e-210">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="5d89e-211">Si usa un objeto de directiva de grupo (GPO) para actualizar el registro, debe definir el objeto para crear un nuevo valor en lugar de actualizar los datos del valor.</span><span class="sxs-lookup"><span data-stu-id="5d89e-211">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="5d89e-212">Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.</span><span class="sxs-lookup"><span data-stu-id="5d89e-212">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="5d89e-213">El siguiente procedimiento describe cómo modificar el registro para que la experiencia de cliente de Lync se muestre la primera vez que un usuario inicie Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d89e-213">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="5d89e-214">También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de bienvenida como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d89e-214">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="5d89e-215">**Para crear el GPO**</span><span class="sxs-lookup"><span data-stu-id="5d89e-215">**To create the GPO**</span></span>

1.  <span data-ttu-id="5d89e-216">Inicie la **consola de administración de directivas de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-216">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="5d89e-217">Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="5d89e-217">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="5d89e-218">Haga clic con el botón secundario en el nodo **objetos de directiva de grupo** y seleccione **nuevo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="5d89e-218">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="5d89e-219">En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el GPO, por ejemplo, **makelyncdefaultuiy**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-219">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5d89e-220">Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, a continuación, seleccione **Editar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="5d89e-220">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="5d89e-221">En el **Editor de administración de directivas de grupo**, expanda **configuración de usuario**, **Opciones**, expanda **configuración de Windows**y, a continuación, seleccione el nodo **registro** .</span><span class="sxs-lookup"><span data-stu-id="5d89e-221">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="5d89e-222">Haga clic con el botón secundario en el nodo **registro** y seleccione **nuevo** \> **elemento del registro**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-222">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="5d89e-223">En el cuadro de diálogo **nuevas propiedades del registro** , actualice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d89e-223">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5d89e-224">Field</span><span class="sxs-lookup"><span data-stu-id="5d89e-224">Field</span></span></th>
    <th><span data-ttu-id="5d89e-225">Valor para seleccionar o escribir</span><span class="sxs-lookup"><span data-stu-id="5d89e-225">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5d89e-226"><strong>Acción</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-226"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-227"><strong>Crear</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-227"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5d89e-228"><strong>Subárbol</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-228"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-229">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="5d89e-229">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5d89e-230"><strong>Ruta de acceso de la clave</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-230"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-231">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="5d89e-231">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5d89e-232"><strong>Nombre del valor</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-232"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-233">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="5d89e-233">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5d89e-234"><strong>Tipo de valor</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-234"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-235">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="5d89e-235">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5d89e-236"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="5d89e-236"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="5d89e-237">00000000</span><span class="sxs-lookup"><span data-stu-id="5d89e-237">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="5d89e-238">Haga clic en **Aceptar** para guardar los cambios y, a continuación, cierre el GPO.</span><span class="sxs-lookup"><span data-stu-id="5d89e-238">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="5d89e-239">A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la Directiva, como una unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="5d89e-239">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="5d89e-240">**Para usar el GPO para asignar la Directiva**</span><span class="sxs-lookup"><span data-stu-id="5d89e-240">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="5d89e-241">En la consola de administración de directivas de grupo, haga clic con el botón secundario en la unidad organizativa a la que desea asignar la Directiva y, a continuación, seleccione **vincular a un GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-241">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="5d89e-242">En el cuadro de diálogo **seleccionar GPO** , seleccione el GPO que ha creado y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d89e-242">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="5d89e-243">En el equipo del usuario de destino, abra un símbolo del sistema y escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5d89e-243">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="5d89e-244">**GPUpdate/target: usuario**</span><span class="sxs-lookup"><span data-stu-id="5d89e-244">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="5d89e-245">El mensaje "actualizando la Directiva..." se muestra mientras se aplica el GPO.</span><span class="sxs-lookup"><span data-stu-id="5d89e-245">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="5d89e-246">Una vez completado, se muestra el mensaje "la actualización de la Directiva de usuario se ha completado correctamente".</span><span class="sxs-lookup"><span data-stu-id="5d89e-246">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="5d89e-247">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5d89e-247">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="5d89e-248">**Gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="5d89e-248">**gpresult /r**</span></span>
    
    <span data-ttu-id="5d89e-249">Debe ver "objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d89e-249">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="5d89e-250">También puede comprobar que el GPO haya actualizado correctamente el registro en el equipo del usuario examinando el registro.</span><span class="sxs-lookup"><span data-stu-id="5d89e-250">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="5d89e-251">Abra el editor del registro y vaya a la clave de \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ Lync \] del software HKEY current user\*\* .</span><span class="sxs-lookup"><span data-stu-id="5d89e-251">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="5d89e-252">Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="5d89e-252">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

