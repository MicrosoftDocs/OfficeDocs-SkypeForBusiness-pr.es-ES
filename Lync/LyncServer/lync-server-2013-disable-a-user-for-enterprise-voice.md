---
title: 'Lync Server 2013: deshabilitar a un usuario para telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586f0e699d0cb0cea09b423f25beffd3efe5afdf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="35ebe-102">Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebe-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ebe-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="35ebe-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="35ebe-104">Use el siguiente procedimiento para deshabilitar Enterprise Voice para una cuenta de usuario que esté habilitada para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35ebe-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="35ebe-105">Para deshabilitar una cuenta de usuario para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="35ebe-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="35ebe-106">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="35ebe-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="35ebe-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35ebe-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35ebe-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35ebe-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35ebe-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="35ebe-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="35ebe-110">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="35ebe-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="35ebe-111">En la tabla, haga clic en la cuenta de usuario que desee habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="35ebe-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="35ebe-112">En el menú \*\*Editar \*\*, haga clic en \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="35ebe-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="35ebe-113">En la página \*\*Editar usuario de Lync Server \*\*, en \*\*Telefonía \*\*, haga clic en cualquier opción excepto \*\*Telefonía IP empresarial \*\*.</span><span class="sxs-lookup"><span data-stu-id="35ebe-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35ebe-114">Para impedir que un usuario realice llamadas de audio o vídeo mediante Lync, en <STRONG>telefonía</STRONG>, haga clic en <STRONG>audio y vídeo deshabilitado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="35ebe-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="35ebe-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="35ebe-115">Click **Commit**.</span></span>

<span data-ttu-id="35ebe-116">El usuario ahora no puede usar la característica Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="35ebe-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35ebe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="35ebe-117">See Also</span></span>


[<span data-ttu-id="35ebe-118">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebe-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="35ebe-119">Administración de la telefonía IP empresarial para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebe-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="35ebe-120">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebe-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

