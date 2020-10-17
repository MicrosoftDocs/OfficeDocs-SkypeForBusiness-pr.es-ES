---
title: 'Lync Server 2013: Buscar usuarios de Lync Server'
description: 'Lync Server 2013: Buscar usuarios de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0c4860b7b89ad13b3a0003c5666a320172dad6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557086"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="fa112-103">Buscar usuarios de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa112-103">Search for Lync Server users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa112-104">_**Última modificación del tema:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="fa112-104">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="fa112-105">Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa112-105">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="fa112-106">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="fa112-106">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="fa112-107">Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fa112-107">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="fa112-108">El siguiente procedimiento describe cómo usar el panel de control de Lync Server para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="fa112-108">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa112-109">En un entorno con tipología de bosque central, los resultados de una búsqueda a veces no son muy precisos cuando se busca a un usuario por su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fa112-109">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="fa112-110">En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet <STRONG>Get-CSUser</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fa112-110">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="fa112-111">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="fa112-111">To search for one or more users</span></span>

1.  <span data-ttu-id="fa112-112">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fa112-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa112-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa112-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fa112-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fa112-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fa112-115">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="fa112-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fa112-116">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="fa112-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="fa112-117">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="fa112-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fa112-118">Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="fa112-118">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fa112-119">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa112-119">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="fa112-120">En la lista **Igual a**, haga clic en **Igual a** o **No igual a**.</span><span class="sxs-lookup"><span data-stu-id="fa112-120">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="fa112-121">En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="fa112-121">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="fa112-p105">Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda**. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fa112-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa112-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa112-124">See Also</span></span>


[<span data-ttu-id="fa112-125">Visualización de la información sobre las cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa112-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="fa112-126">Habilitación y deshabilitación de usuarios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa112-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

