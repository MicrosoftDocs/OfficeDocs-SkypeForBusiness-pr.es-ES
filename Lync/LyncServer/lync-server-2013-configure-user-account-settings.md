---
title: 'Lync Server 2013: configurar las opciones de la cuenta de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71628f056298965f4033dc6bbecbe75b47b678a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520207"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="be4ef-102">Configurar las opciones de cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be4ef-102">Configure user account settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be4ef-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="be4ef-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="be4ef-104">Los usuarios de acceso telefónico escriben su número de teléfono o extensión y un PIN para participar en conferencias como usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="be4ef-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="be4ef-105">El URI de **línea** de telefonía especificado en las cuentas de usuario de Lync Server es necesario para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="be4ef-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="be4ef-106">En el procedimiento de este tema se explica cómo asignar un **URI de línea** para una sola cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="be4ef-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="be4ef-107">Si desea asignar un **URI de línea** para varias cuentas de usuario, puede crear un script que use el cmdlet **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="be4ef-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="be4ef-108">Para obtener información detallada sobre cómo usar un script de ejemplo para asignar un **URI de línea** a varias cuentas de usuario, consulte "asignar URI de línea a varios usuarios" en [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) .</span><span class="sxs-lookup"><span data-stu-id="be4ef-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="be4ef-109">Para configurar las opciones de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="be4ef-109">To configure user account settings</span></span>

1.  <span data-ttu-id="be4ef-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="be4ef-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="be4ef-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be4ef-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="be4ef-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="be4ef-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="be4ef-113">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="be4ef-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="be4ef-114">En el campo de búsqueda, escriba el nombre del usuario que desea configurar para las conferencias de acceso telefónico local o haga clic en **Agregar filtro** para especificar campos de búsqueda y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="be4ef-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="be4ef-115">Haga doble clic en el nombre de usuario para abrir el cuadro de diálogo **Editar usuario de Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="be4ef-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="be4ef-116">En **Telefonía**, en el campo **URI de línea**, escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="be4ef-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be4ef-117">Puede especificar el <STRONG>URI de línea</STRONG> solo si la <STRONG>telefonía</STRONG> está establecida en <STRONG>solo de PC a PC</STRONG>, telefonía <STRONG>IP empresarial</STRONG>, <STRONG>control remoto de llamadas</STRONG> o <STRONG>control remoto de llamadas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="be4ef-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="be4ef-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="be4ef-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

