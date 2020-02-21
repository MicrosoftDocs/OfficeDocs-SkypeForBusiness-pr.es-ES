---
title: 'Lync Server 2013: crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3a1ea4ed8643daaecd2ef15b9cffb0c7b65bab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="945a7-102">Crear o modificar la configuración de PIN de conferencia de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="945a7-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="945a7-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="945a7-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="945a7-104">Siga los pasos a continuación para crear o modificar una directiva de número de identificación personal (PIN) de conferencias de acceso telefónico local a nivel de usuario o a nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="945a7-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="945a7-105">Para más información sobre cómo cambiar la Directiva de PIN global, vea [modificar la configuración del PIN de conferencias de acceso telefónico local predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="945a7-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="945a7-106">Para crear una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="945a7-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="945a7-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945a7-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="945a7-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="945a7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="945a7-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="945a7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="945a7-110">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="945a7-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="945a7-111">En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="945a7-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="945a7-p103">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="945a7-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="945a7-p104">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="945a7-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="945a7-117">En el campo **Descripción**, escriba una descripción de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="945a7-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="945a7-p105">En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que se va a admitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="945a7-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="945a7-p106">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="945a7-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="945a7-123">Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="945a7-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="945a7-p107">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="945a7-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="945a7-127">Si activa la casilla **Habilitar expiración de PIN**, en **el PIN expira después de (días)**; escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="945a7-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="945a7-p108">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="945a7-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="945a7-p109">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla de verificación **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="945a7-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="945a7-133">Se recomienda no permitir patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="945a7-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="945a7-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="945a7-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="945a7-135">Para modificar una directiva de PIN de usuario o sitio nueva</span><span class="sxs-lookup"><span data-stu-id="945a7-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="945a7-136">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945a7-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="945a7-137">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="945a7-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="945a7-138">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="945a7-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="945a7-139">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="945a7-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="945a7-140">En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="945a7-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="945a7-141">En **Editar directiva de PIN**, modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).</span><span class="sxs-lookup"><span data-stu-id="945a7-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="945a7-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="945a7-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

