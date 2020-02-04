---
title: 'Lync Server 2013: Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="69f4b-102">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f4b-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f4b-103">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="69f4b-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="69f4b-104">Si tiene previsto implementar un dispositivo de sucursal que sea reviviente, debe agregar la aplicación de la rama que es reviviente a los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="69f4b-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="69f4b-105">Realice este procedimiento en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="69f4b-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69f4b-106">Realice este procedimiento solo si está implementando un dispositivo de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="69f4b-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="69f4b-107">No lo lleve a cabo si está implementando un servidor de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="69f4b-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="69f4b-108">Para agregar un dispositivo de rama con la que los servicios de dominio de Active Directory son supervivientes</span><span class="sxs-lookup"><span data-stu-id="69f4b-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="69f4b-109">Inicie sesión en un servidor miembro como miembro del grupo administradores de la empresa.</span><span class="sxs-lookup"><span data-stu-id="69f4b-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="69f4b-110">Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="69f4b-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="69f4b-111">En el menú **acciones** , haga clic en **nuevo** y, a continuación, en **equipo**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="69f4b-112">En el cuadro de diálogo **nuevo objeto-equipo** , escriba un nombre para el objeto de equipo de la aplicación de sucursal que sea sobreviviente (por ejemplo, BranchOffice1) y, a continuación, haga clic en **cambiar**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="69f4b-113">En el cuadro de diálogo **Seleccionar usuario o grupo** , agregue el grupo RTCUniversalSBATechnicians y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69f4b-114">Un miembro del grupo RTCUniversalSBATechnicians en el sitio de la sucursal agregará este dispositivo al dominio más adelante.</span><span class="sxs-lookup"><span data-stu-id="69f4b-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="69f4b-115">Haga clic en **Aceptar** para guardar el objeto de equipo de la aplicación de sucursal superviviente.</span><span class="sxs-lookup"><span data-stu-id="69f4b-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="69f4b-116">Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="69f4b-117">En el editor **ADSI**, haga clic con el botón secundario en el objeto de equipo que creó en los pasos anteriores y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="69f4b-118">En la lista de atributos, haga clic en **ServicePrincipalName**y, a continuación, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="69f4b-119">En el **campo valor para agregar** ,\<escriba FQDN\> /SBA de SBA \<donde el\> FQDN de SBA es el nombre de dominio completo (FQDN) de su equipo de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="69f4b-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="69f4b-120">Por ejemplo, escriba **host/BranchOffice1. contoso. com**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="69f4b-121">Haga clic en **Aceptar** para guardar la configuración del atributo **ServicePrincipalName** y, a continuación, haga clic en **Aceptar** para guardar las propiedades del objeto de equipo.</span><span class="sxs-lookup"><span data-stu-id="69f4b-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="69f4b-122">En **usuarios y equipos de Active**Directory, haga clic con el botón secundario en **usuarios**, seleccione **nuevo**y, a continuación, haga clic en **usuario**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="69f4b-123">Escriba información en el Asistente para crear una cuenta de usuario de dominio para un técnico de la aplicación de rama superviviente.</span><span class="sxs-lookup"><span data-stu-id="69f4b-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="69f4b-124">En **usuarios y equipos de Active**Directory, haga clic en **usuarios**, haga clic con el botón derecho en el objeto de usuario y, después, haga clic en **Agregar a un grupo**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="69f4b-125">En **Escriba los nombres de objeto que desea seleccionar**, escriba **RTCUniversalSBATechnicians**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69f4b-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="69f4b-126">Repita los pasos 12-15 para cada técnico del sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="69f4b-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="69f4b-127">**Siguiente paso**: [Agregar sitios de sucursales a la topología de Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="69f4b-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

