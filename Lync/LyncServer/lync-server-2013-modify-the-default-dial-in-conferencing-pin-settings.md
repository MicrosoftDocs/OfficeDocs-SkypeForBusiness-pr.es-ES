---
title: 'Lync Server 2013: Modificar la configuración del PIN de la conferencia de acceso telefónico local predeterminada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee196fae24ba4a6b7bf8e0ede0bbc0b35a7b3fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="ecb71-102">Modificar la configuración del PIN de la conferencia de acceso telefónico local predeterminada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecb71-102">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecb71-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ecb71-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ecb71-104">La directiva de PIN global define las reglas de los PIN para conferencias de acceso telefónico local en el nivel de bosque.</span><span class="sxs-lookup"><span data-stu-id="ecb71-104">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="ecb71-105">Siga estos pasos para modificar la directiva global de PIN de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="ecb71-105">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="ecb71-106">Para obtener detalles sobre cómo crear o modificar una directiva de PIN de conferencias de acceso telefónico local en el nivel de usuario o de sitio, consulte [crear o modificar la configuración del PIN de conferencias de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="ecb71-106">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="ecb71-107">Para modificar la Directiva de PIN global</span><span class="sxs-lookup"><span data-stu-id="ecb71-107">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="ecb71-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecb71-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ecb71-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ecb71-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecb71-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ecb71-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecb71-111">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="ecb71-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="ecb71-112">En la página **Directiva de PIN**, haga clic en **Global**, en **Editar** y después en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ecb71-112">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ecb71-p103">En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="ecb71-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="ecb71-p104">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ecb71-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="ecb71-118">Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="ecb71-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="ecb71-p105">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="ecb71-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="ecb71-122">Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="ecb71-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="ecb71-p106">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="ecb71-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="ecb71-p107">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="ecb71-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ecb71-128">Se recomienda no permitir patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="ecb71-128">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="ecb71-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ecb71-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

