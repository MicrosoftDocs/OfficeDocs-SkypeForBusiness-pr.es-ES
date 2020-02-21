---
title: 'Lync Server 2013: probar la implementación del grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="7cde0-102">Probar la implementación del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cde0-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cde0-103">_**Última modificación del tema:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="7cde0-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="7cde0-104">El siguiente procedimiento describe cómo probar la implementación del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7cde0-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="7cde0-105">Para probar la implementación del grupo</span><span class="sxs-lookup"><span data-stu-id="7cde0-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="7cde0-106">Use usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Lync Server 2013 (en el que está instalado el panel de control de Lync Server 2013) al grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="7cde0-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7cde0-107">Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el panel de control de Lync Server, lo que indica que "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="7cde0-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="7cde0-108">Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="7cde0-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7cde0-109">La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cde0-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="7cde0-110">Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7cde0-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="7cde0-111">Inicie el panel de control de Lync Server y, si se le pide, proporcione las credenciales.</span><span class="sxs-lookup"><span data-stu-id="7cde0-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="7cde0-112">El panel de control de Lync Server muestra la información de implementación.</span><span class="sxs-lookup"><span data-stu-id="7cde0-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="7cde0-113">En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación es junto a cada rol de servidor de Lync Server que se ha implementado y se ha puesto en línea.</span><span class="sxs-lookup"><span data-stu-id="7cde0-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="7cde0-114">En la barra de navegación izquierda, haga clic en **Usuarios** y haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7cde0-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="7cde0-115">En la página **Nuevo usuario de Lync Server**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7cde0-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="7cde0-p102">Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory** seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="7cde0-p102">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="7cde0-119">En en el panel de resultados de la búsqueda, seleccione todos los objetos de esta sesión de búsqueda y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7cde0-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="7cde0-p103">En la página **Nuevo usuario de Lync Server** el objeto o los objetos seleccionados están en la pantalla **Usuarios**. En la lista **Asignar usuarios a un grupo**, seleccione el servidor en el que se deben hospedar los objetos.</span><span class="sxs-lookup"><span data-stu-id="7cde0-p103">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display. In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="7cde0-122">A continuación se presentan una serie de opciones para configurar los objetos.</span><span class="sxs-lookup"><span data-stu-id="7cde0-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="7cde0-123">**Generar el URI del SIP del usuario**</span><span class="sxs-lookup"><span data-stu-id="7cde0-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="7cde0-124">**Telefonía**</span><span class="sxs-lookup"><span data-stu-id="7cde0-124">**Telephony**</span></span>
    
      - <span data-ttu-id="7cde0-125">**URI de línea**</span><span class="sxs-lookup"><span data-stu-id="7cde0-125">**Line URI**</span></span>
    
      - <span data-ttu-id="7cde0-126">**Directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="7cde0-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="7cde0-127">**Directiva de versión de clientes**</span><span class="sxs-lookup"><span data-stu-id="7cde0-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="7cde0-128">**Directiva de PIN**</span><span class="sxs-lookup"><span data-stu-id="7cde0-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="7cde0-129">**Directiva de acceso externo**</span><span class="sxs-lookup"><span data-stu-id="7cde0-129">**External access policy**</span></span>
    
      - <span data-ttu-id="7cde0-130">**Directiva de archivado**</span><span class="sxs-lookup"><span data-stu-id="7cde0-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="7cde0-131">**Directiva de ubicación**</span><span class="sxs-lookup"><span data-stu-id="7cde0-131">**Location policy**</span></span>
    
      - <span data-ttu-id="7cde0-132">**Directiva de cliente**</span><span class="sxs-lookup"><span data-stu-id="7cde0-132">**Client policy**</span></span>
    
    <span data-ttu-id="7cde0-133">Para probar la funcionalidad básica, seleccione la opción que prefiera para el parámetro **Generar el URI del SIP de usuario** (las otras opciones de la configuración usan los valores predeterminados) y haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="7cde0-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="7cde0-p104">En pantalla se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los objetos ya están listos para usarse. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="7cde0-p104">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="7cde0-136">Un usuario debe iniciar sesión en un equipo integrado en el dominio y otro usuario, en otro equipo del dominio.</span><span class="sxs-lookup"><span data-stu-id="7cde0-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="7cde0-137">Instale Lync 2013 en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios puedan iniciar sesión en Lync Server 2013 y que puedan enviar mensajes instantáneos entre sí.</span><span class="sxs-lookup"><span data-stu-id="7cde0-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7cde0-138">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7cde0-138">See Also</span></span>


[<span data-ttu-id="7cde0-139">Implementación de clientes y dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cde0-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

