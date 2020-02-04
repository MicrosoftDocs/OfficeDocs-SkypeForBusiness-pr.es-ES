---
title: 'Lync Server 2013: Se quitan los permisos de usuario autenticado'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="8232b-102">Se quitan los permisos de usuario autenticado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8232b-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8232b-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8232b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8232b-104">En un entorno de Active Directory bloqueado, las entradas de control de acceso (ACE) de usuarios autenticados se quitan de los contenedores predeterminados de Active Directory, incluidos los usuarios, la configuración o el sistema y las unidades organizativas en las que el usuario y el equipo se almacenan los objetos.</span><span class="sxs-lookup"><span data-stu-id="8232b-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="8232b-105">Quitar las entradas de acceso de los usuarios autenticadas impide el acceso de lectura a la información de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8232b-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="8232b-106">Sin embargo, al quitar las ACE se crean problemas para Lync Server 2013 porque depende de los permisos de lectura de estos contenedores para permitir que los usuarios ejecuten la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="8232b-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="8232b-107">En esta situación, la pertenencia al grupo de administradores de dominio, que es necesaria para ejecutar la preparación del dominio, la activación del servidor y la creación de grupos, ya no concede acceso de lectura a la información de Active Directory almacenada en los contenedores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8232b-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="8232b-108">Debe conceder manualmente permisos de acceso de lectura en varios contenedores del dominio raíz del bosque para comprobar que se ha completado el procedimiento de preparación del bosque con requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="8232b-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="8232b-109">Para permitir que un usuario ejecute la preparación del dominio, la activación de servidor o la creación de grupos en cualquier dominio raíz que no sea de bosque, tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8232b-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="8232b-110">Use una cuenta que sea miembro del grupo administradores de organización para ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="8232b-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="8232b-111">Use una cuenta que sea miembro del grupo administradores de dominio y otorgue a esta cuenta permisos de acceso de lectura en cada uno de los siguientes contenedores del dominio raíz del bosque:</span><span class="sxs-lookup"><span data-stu-id="8232b-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="8232b-112">Admin</span><span class="sxs-lookup"><span data-stu-id="8232b-112">Domain</span></span>
    
      - <span data-ttu-id="8232b-113">Configuración o sistema</span><span class="sxs-lookup"><span data-stu-id="8232b-113">Configuration or System</span></span>

<span data-ttu-id="8232b-114">Si no desea usar una cuenta que sea miembro del grupo administradores de la organización para ejecutar la preparación del dominio u otras tareas de configuración, conceda explícitamente a la cuenta que desea usar acceso de lectura en los contenedores relevantes de la raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="8232b-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="8232b-115">Para conceder a los usuarios permisos de acceso de lectura en los contenedores del dominio raíz del bosque</span><span class="sxs-lookup"><span data-stu-id="8232b-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="8232b-116">Inicie sesión en el equipo unido al dominio raíz del bosque con una cuenta que sea miembro del grupo administradores de dominio para el dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="8232b-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="8232b-117">Ejecute ADSIEdit. msc para el dominio raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="8232b-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="8232b-118">Si se quitaron las ACE de usuarios autenticados del contenedor del dominio, de la configuración o del sistema, debe conceder permisos de solo lectura para el contenedor, como se describe en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="8232b-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="8232b-119">Haga clic con el botón secundario en el contenedor y después haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8232b-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="8232b-120">Haga clic en la pestaña **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="8232b-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="8232b-121">Haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="8232b-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="8232b-122">En la pestaña **permisos** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8232b-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="8232b-123">Escriba el nombre del usuario o grupo que recibe permisos con el siguiente formato: `domain\account name`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8232b-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="8232b-124">En la pestaña **objetos** , en **se aplica a**, haga clic en **solo este objeto**.</span><span class="sxs-lookup"><span data-stu-id="8232b-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="8232b-125">En **permisos**, seleccione la siguiente opción permitir entradas ACE haciendo clic en la columna **permitir** : **contenido**de la lista, **leer todas las propiedades**y **permisos de lectura**.</span><span class="sxs-lookup"><span data-stu-id="8232b-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="8232b-126">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="8232b-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="8232b-127">Repita estos pasos para cualquiera de los contenedores relevantes enumerados en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="8232b-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

