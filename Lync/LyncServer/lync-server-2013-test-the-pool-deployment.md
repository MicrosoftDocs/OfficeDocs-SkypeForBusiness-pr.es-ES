---
title: 'Lync Server 2013: Probar la implementación del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="d4f0c-102">Probar la implementación del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f0c-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f0c-103">_**Última modificación del tema:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="d4f0c-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="d4f0c-104">En el procedimiento siguiente se describe cómo probar la implementación del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="d4f0c-105">Para probar la implementación de la agrupación</span><span class="sxs-lookup"><span data-stu-id="d4f0c-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="d4f0c-106">Use equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory de la función Administrador de la implementación de Lync Server 2013 (en la que está instalado el panel de control de Lync Server 2013) en el grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="d4f0c-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4f0c-107">Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el panel de control de Lync Server, que indica "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="d4f0c-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="d4f0c-108">Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4f0c-109">La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="d4f0c-110">Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="d4f0c-111">Inicie el panel de control de Lync Server y, si se le solicita, proporcione las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="d4f0c-112">El panel de control de Lync Server muestra información de implementación.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="d4f0c-113">En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación está junto a cada rol de servidor de Lync Server que se ha implementado y se ha puesto en conexión.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="d4f0c-114">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="d4f0c-115">En la página **nuevo usuario de Lync Server** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="d4f0c-116">Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="d4f0c-117">También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="d4f0c-118">Una vez que haya decidido las opciones de búsqueda, **Busque**vínculos de vínculos.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="d4f0c-119">En el panel Resultados de la búsqueda, seleccione todos los objetos de esta sesión de búsqueda y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="d4f0c-120">En la página **nuevo usuario de Lync Server** , el objeto o los objetos que haya seleccionado aparecerán en la pantalla **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="d4f0c-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="d4f0c-121">En la lista **asignar usuarios a un grupo** , seleccione el servidor en el que se deben alojar los objetos.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="d4f0c-122">A continuación se muestran varias opciones para configurar los objetos.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="d4f0c-123">**Generar el URI de SIP del usuario**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="d4f0c-124">**Telefonía**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-124">**Telephony**</span></span>
    
      - <span data-ttu-id="d4f0c-125">**URI de línea**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-125">**Line URI**</span></span>
    
      - <span data-ttu-id="d4f0c-126">**Directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="d4f0c-127">**Directiva de versión de cliente**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="d4f0c-128">**Directiva de PIN**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="d4f0c-129">**Directiva de acceso externo**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-129">**External access policy**</span></span>
    
      - <span data-ttu-id="d4f0c-130">**Directiva de archivado**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="d4f0c-131">**Directiva de ubicación**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-131">**Location policy**</span></span>
    
      - <span data-ttu-id="d4f0c-132">**Directiva de cliente**</span><span class="sxs-lookup"><span data-stu-id="d4f0c-132">**Client policy**</span></span>
    
    <span data-ttu-id="d4f0c-133">A fin de probar la funcionalidad básica, seleccione la opción que prefiera para la configuración de **URI de SIP del usuario** (las demás opciones de la configuración usarán la configuración predeterminada) y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="d4f0c-134">Se muestra una página de resumen que muestra una marca de verificación \*\*\*\* en la columna habilitada para indicar que los objetos ya están listos para su uso.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="d4f0c-135">En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="d4f0c-136">Iniciar sesión de un usuario en un equipo que se une al dominio y otro usuario en otro equipo del dominio.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="d4f0c-137">Instale Lync 2013 en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios pueden iniciar sesión en Lync Server 2013 y pueden enviar mensajes instantáneos entre sí.</span><span class="sxs-lookup"><span data-stu-id="d4f0c-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4f0c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f0c-138">See Also</span></span>


[<span data-ttu-id="d4f0c-139">Implementación de clientes y dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f0c-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

