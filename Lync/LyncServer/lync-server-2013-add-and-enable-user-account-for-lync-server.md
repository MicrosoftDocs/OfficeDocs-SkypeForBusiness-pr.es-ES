---
title: 'Lync Server 2013: agregar y habilitar cuentas de usuario para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc52e76d480e323669b88c1ee461eeccf9aef38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="28a23-102">Agregar y habilitar una cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a23-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a23-103">_**Última modificación del tema:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="28a23-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="28a23-104">Después de habilitar una cuenta de usuario en usuarios y equipos de Active Directory, puede usar el panel de control de Lync Server para crear y habilitar nuevas cuentas de usuario de Lync Server 2013 agregando un usuario de Active Directory a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28a23-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="28a23-105">Para agregar y habilitar un nuevo usuario de Lync Server</span><span class="sxs-lookup"><span data-stu-id="28a23-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="28a23-106">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="28a23-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28a23-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28a23-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28a23-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28a23-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28a23-109">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="28a23-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="28a23-110">Haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="28a23-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="28a23-111">En el cuadro de diálogo **nuevo usuario de Lync Server** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="28a23-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="28a23-112">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre, nombre para mostrar, nombre, apellido, nombre de cuenta del administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre principal de usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="28a23-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="28a23-113">En la tabla, seleccione la cuenta que desea agregar a Lync Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28a23-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="28a23-114">Asigne el usuario a un grupo, especifique los detalles adicionales, asigne las directivas al usuario que desee y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="28a23-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28a23-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="28a23-115">See Also</span></span>


[<span data-ttu-id="28a23-116">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a23-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="28a23-117">Quitar una cuenta de usuario de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a23-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="28a23-118">Habilitar y deshabilitar usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a23-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

