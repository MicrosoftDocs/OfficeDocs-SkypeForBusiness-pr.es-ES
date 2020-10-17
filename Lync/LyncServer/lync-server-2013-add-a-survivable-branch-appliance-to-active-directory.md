---
title: 'Lync Server 2013: agregar una aplicación de sucursal con funciones de supervivencia a Active Directory'
description: 'Lync Server 2013: agregar una aplicación de sucursal con funciones de supervivencia a Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd06332679be0819cf3002f344a62a7ce1d5a9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567896"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="88672-103">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88672-103">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88672-104">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="88672-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="88672-105">Si tiene previsto implementar una aplicación de sucursal con funciones de supervivencia, debe agregar la aplicación de sucursal con funciones de supervivencia a los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="88672-105">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="88672-106">Realice este procedimiento en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="88672-106">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88672-107">Realice este procedimiento únicamente si va a implementar una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="88672-107">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="88672-108">No lo haga si va a implementar un servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="88672-108">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="88672-109">Para agregar una aplicación de sucursal con funciones de supervivencia a los Servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="88672-109">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="88672-110">Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="88672-110">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="88672-111">Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="88672-111">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="88672-112">En el menú **Acciones**, haga clic en **Nuevo** y, a continuación, en **Equipo**.</span><span class="sxs-lookup"><span data-stu-id="88672-112">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="88672-113">En el cuadro de diálogo **nuevo objeto-equipo** , escriba un nombre para el objeto de equipo de aplicación de sucursal con funciones de supervivencia (por ejemplo, BranchOffice1) y, a continuación, haga clic en **cambiar**.</span><span class="sxs-lookup"><span data-stu-id="88672-113">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="88672-114">En el cuadro de diálogo **Seleccionar usuario o grupo**, agregue el grupo RTCUniversalSBATechnicians y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88672-114">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88672-115">Más adelante, un miembro del grupo RTCUniversalSBATechnicians del sitio de sucursal agregará este dispositivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="88672-115">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="88672-116">Haga clic en **Aceptar** para guardar el objeto de equipo de aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="88672-116">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="88672-117">Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Editor ADSI**.</span><span class="sxs-lookup"><span data-stu-id="88672-117">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="88672-118">En el **Editor ADSI**, haga clic con el botón secundario en el objeto de equipo que creó en los pasos anteriores y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="88672-118">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="88672-119">En la lista de atributos, haga clic en **servicePrincipalName** y luego en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="88672-119">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="88672-120">En el campo **valor para agregar** , escriba host/ \<SBA FQDN\> donde \<SBA FQDN\> es el nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="88672-120">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="88672-121">Por ejemplo, escriba **HOST/BranchOffice1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="88672-121">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="88672-122">Haga clic en **Aceptar** para guardar la configuración de atributo **servicePrincipalName** y, a continuación, en **Aceptar** para guardar las propiedades del objeto de equipo.</span><span class="sxs-lookup"><span data-stu-id="88672-122">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="88672-123">En **Usuarios y equipos de Active Directory**, haga clic con el botón secundario en **Usuarios**, haga clic en **Nuevo** y, a continuación, en **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="88672-123">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="88672-124">Escriba información en el Asistente para crear una cuenta de usuario de dominio para un técnico de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="88672-124">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="88672-125">En **Usuarios y equipos de Active Directory**, haga clic en **Usuarios**, haga clic con el botón secundario en el objeto de equipo y luego haga clic **Agregar a un grupo**.</span><span class="sxs-lookup"><span data-stu-id="88672-125">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="88672-126">En **Escribir los nombres de objeto para seleccionar**, escriba **RTCUniversalSBATechnicians** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88672-126">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="88672-127">Repita los pasos 12-15 para cada técnico del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="88672-127">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="88672-128">**Siguiente paso**: [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="88672-128">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

