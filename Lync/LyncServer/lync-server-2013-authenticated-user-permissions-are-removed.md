---
title: 'Lync Server 2013: se quitan los permisos de usuario autenticados'
description: 'Lync Server 2013: se quitan los permisos de usuario autenticados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59da0ec893395405010afdd0263bd6be5d646881
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573026"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="f3b47-103">Los permisos de usuarios autenticados se quitan en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3b47-103">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3b47-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f3b47-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f3b47-105">En un entorno de Active Directory bloqueado, las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores de Active Directory predeterminados, incluidos el de usuarios, el de configuración y el de sistema, y de las unidades organizativas (OU) donde se almacenan los objetos de usuario y de equipo.</span><span class="sxs-lookup"><span data-stu-id="f3b47-105">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="f3b47-106">Al eliminar las ACE de los usuarios autenticados se evita el acceso de lectura a la información de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3b47-106">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="f3b47-107">Sin embargo, la eliminación de las ACE crea problemas en Lync Server 2013 porque depende de los permisos de lectura de estos contenedores para permitir que los usuarios ejecuten la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="f3b47-107">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="f3b47-p102">En esta situación, la pertenencia al grupo Admins. del dominio, necesaria para ejecutar la preparación del dominio, la activación de los servidores y la creación de grupos de servidores, ya no concede acceso de lectura a la información de Active Directory almacenada en los contenedores predeterminados. Debe conceder manualmente permisos de acceso de lectura en diversos contenedores del dominio raíz del bosque para comprobar si se ha realizado correctamente el requisito previo de preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="f3b47-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="f3b47-110">Para permitir que los usuarios ejecuten la preparación del dominio, la activación de los servidores o la creación de grupos de servidores en cualquier dominio que no pertenezca a la raíz del bosque, dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f3b47-110">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="f3b47-111">Use una cuenta que sea miembro del grupo administradores de organización para ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="f3b47-111">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="f3b47-112">Usar una cuenta que sea miembro del grupo Admins. del dominio y conceder permisos de acceso de lectura a esta cuenta en cada uno de los contenedores siguientes del dominio raíz del bosque:</span><span class="sxs-lookup"><span data-stu-id="f3b47-112">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="f3b47-113">Dominio</span><span class="sxs-lookup"><span data-stu-id="f3b47-113">Domain</span></span>
    
      - <span data-ttu-id="f3b47-114">Configuración o sistema</span><span class="sxs-lookup"><span data-stu-id="f3b47-114">Configuration or System</span></span>

<span data-ttu-id="f3b47-115">Si no desea usar una cuenta que sea miembro del grupo Administradores de organización para ejecutar la preparación del dominio o realizar otras tareas de configuración, conceda explícitamente a la cuenta que desea utilizar acceso de lectura en los contenedores pertinentes de la raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="f3b47-115">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="f3b47-116">Para conceder a los usuarios permisos de acceso de lectura en los contenedores del dominio raíz del bosque</span><span class="sxs-lookup"><span data-stu-id="f3b47-116">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="f3b47-117">Inicie sesión en el equipo que pertenece al dominio raíz del bosque con una cuenta que sea miembro del grupo Admins. del dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="f3b47-117">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="f3b47-118">Ejecute adsiedit.msc para el dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="f3b47-118">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="f3b47-119">Si se han quitado las ACE de los usuarios autenticados de los contenedores de dominio, configuración o sistema, debe conceder permisos de solo lectura al contenedor, tal y como se describe en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="f3b47-119">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="f3b47-120">Haga clic con el botón secundario en el contenedor y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-120">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="f3b47-121">Haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-121">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="f3b47-122">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-122">Click **Advanced**.</span></span>

6.  <span data-ttu-id="f3b47-123">En la pestaña **Permisos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-123">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="f3b47-124">Escriba el nombre del usuario o grupo que recibe permisos con el siguiente formato: `domain\account name` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-124">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="f3b47-125">En la pestaña **Objetos**, en **Se aplica a**, haga clic en **Solo este objeto**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-125">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="f3b47-126">En **Permisos**, seleccione las siguientes ACE de permiso haciendo clic en la columna **Permitir**: **Mostrar contenido**, **Leer todas las propiedades** y **Permisos de lectura**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-126">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="f3b47-127">Haga clic dos veces en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3b47-127">Click **OK** twice.</span></span>

11. <span data-ttu-id="f3b47-128">Repita estos pasos para cualquiera de los contenedores relevantes enumerados en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f3b47-128">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

