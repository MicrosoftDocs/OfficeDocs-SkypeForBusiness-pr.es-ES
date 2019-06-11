---
title: 'Lync Server 2013: Buscar usuarios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="e7070-102">Buscar usuarios de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7070-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7070-103">_**Última modificación del tema:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="e7070-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="e7070-104">Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7070-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="e7070-105">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="e7070-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="e7070-106">Puede buscar usuarios mediante el panel de control de Lync Server o el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e7070-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="e7070-107">En el procedimiento siguiente se describe cómo usar Lync Server panel de control para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="e7070-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7070-108">En un entorno con una topología de bosque central, los resultados de la búsqueda podrían no ser exactos al buscar un usuario por la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="e7070-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="e7070-109">En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, SIP: Name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial o usar el cmdlet <STRONG>Get-CSUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e7070-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="e7070-110">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="e7070-110">To search for one or more users</span></span>

1.  <span data-ttu-id="e7070-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e7070-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7070-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7070-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7070-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7070-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7070-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e7070-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e7070-115">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e7070-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="e7070-116">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="e7070-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="e7070-117">Haga clic en el botón de flecha Expandir situado en la esquina superior derecha de la pantalla, encima de resultados de la **búsqueda**, y haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="e7070-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="e7070-118">Escriba la propiedad de usuario escribiéndola o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.</span><span class="sxs-lookup"><span data-stu-id="e7070-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="e7070-119">En la lista **igual a** , haga clic en **igual a** o **no es igual a**.</span><span class="sxs-lookup"><span data-stu-id="e7070-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="e7070-120">En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de la búsqueda y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e7070-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="e7070-121">Los resultados de la búsqueda aparecen en resultados de la **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="e7070-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="e7070-122">Puede seleccionar cualquiera de los usuarios de la lista o todos ellos y realizar tareas de configuración en los usuarios que seleccione.</span><span class="sxs-lookup"><span data-stu-id="e7070-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7070-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7070-123">See Also</span></span>


[<span data-ttu-id="e7070-124">Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7070-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="e7070-125">Habilitar y deshabilitar usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7070-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

