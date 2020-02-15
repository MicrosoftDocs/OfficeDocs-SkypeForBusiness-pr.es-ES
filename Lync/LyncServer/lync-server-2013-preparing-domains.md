---
title: 'Lync Server 2013: preparación de dominios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173b1293fb4bf0353b4e6d9038d05c1480697d17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="9602f-102">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9602f-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9602f-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9602f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9602f-104">La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9602f-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="9602f-105">El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="9602f-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="9602f-106">La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="9602f-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="9602f-107">Puede ejecutar la preparación del dominio en cualquier equipo del dominio donde vaya a implementar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9602f-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="9602f-108">Debe preparar cada dominio que hospede Lync Server o los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9602f-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="9602f-109">Si la herencia de permisos está deshabilitada o los permisos de usuarios autenticados están deshabilitados en su organización, hay pasos adicionales que debe realizar durante la preparación de los dominios.</span><span class="sxs-lookup"><span data-stu-id="9602f-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="9602f-110">Para obtener más información, consulte [preparar los servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="9602f-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="9602f-111">Si en su organización se usan unidades organizativas (OU) en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de las OU al grupo Usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="9602f-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="9602f-112">El acceso de lectura de los contenedores se necesita para preparar dominios.</span><span class="sxs-lookup"><span data-stu-id="9602f-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="9602f-113">Si el grupo Usuarios autenticados no tiene acceso de lectura de la OU, ejecute el cmdlet **Grant-CsOuPermission** según se indica en los siguientes códigos de ejemplo, para conceder permisos de lectura a cada OU.</span><span class="sxs-lookup"><span data-stu-id="9602f-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="9602f-114">Para obtener más información sobre el cmdlet **Grant-CsOuPermission** , consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9602f-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="9602f-115">Para obtener más información sobre las ACE creadas en la raíz del dominio y en los contenedores usuarios, equipos y controladores de dominio, vea <A href="lync-server-2013-changes-made-by-domain-preparation.md">cambios realizados por la preparación del dominio en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9602f-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9602f-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9602f-116">In This Section</span></span>

  - [<span data-ttu-id="9602f-117">Ejecutar la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9602f-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="9602f-118">Uso de cmdlets para invertir la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9602f-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

