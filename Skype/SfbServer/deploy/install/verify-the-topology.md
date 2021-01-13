---
title: Comprobar la topología en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumen: obtenga información sobre cómo comprobar que la topología de Skype Empresarial Server y los servidores de Active Directory funcionan según lo esperado. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833840"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="ad673-104">Comprobar la topología en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ad673-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="ad673-105">**Resumen:** Obtenga información sobre cómo comprobar que la topología de Skype Empresarial Server y los servidores de Active Directory funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="ad673-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="ad673-106">Descargue una versión de prueba gratuita de Skype Empresarial Server desde el Centro [de evaluación de Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="ad673-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ad673-107">Una vez que haya publicado la topología y los componentes del sistema de Skype Empresarial Server instalados en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="ad673-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="ad673-108">Esto incluye comprobar que la configuración se ha propagado a todos los servidores de Active Directory para que todo el dominio sepa que Skype Empresarial está disponible en el dominio.</span><span class="sxs-lookup"><span data-stu-id="ad673-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="ad673-109">Puede realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="ad673-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ad673-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos 1 a 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="ad673-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="ad673-111">La comprobación de la topología es el paso 8 de 8.</span><span class="sxs-lookup"><span data-stu-id="ad673-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="ad673-113">Probar la implementación del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="ad673-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="ad673-114">El último paso es probar el grupo de servidores front-end y confirmar que los clientes de Skype Empresarial se pueden comunicar entre sí.</span><span class="sxs-lookup"><span data-stu-id="ad673-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="ad673-115">Agregar usuarios y comprobar la conectividad del cliente</span><span class="sxs-lookup"><span data-stu-id="ad673-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="ad673-116">Use los equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Skype Empresarial Server (en la que está instalado el Panel de control de Skype Empresarial Server) al grupo **CSAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="ad673-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ad673-117">Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el Panel de control de Skype Empresarial Server que dice: "No autorizado: Se deniega el acceso debido a un error de autorización de control de acceso basado en roles (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="ad673-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="ad673-118">Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="ad673-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad673-119">La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ad673-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="ad673-120">Use la cuenta administrativa para iniciar sesión en el equipo donde está instalado el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ad673-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="ad673-121">Inicie el Panel de control de Skype Empresarial Server y, a continuación, proporcione las credenciales, si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="ad673-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="ad673-122">El Panel de control de Skype Empresarial Server muestra información de implementación.</span><span class="sxs-lookup"><span data-stu-id="ad673-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="ad673-123">En la barra de navegación izquierda, haga clic en Topología y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que hay una marca de verificación verde para el estado de replicación junto a cada rol de Skype Empresarial Server que se ha implementado y puesto en línea.</span><span class="sxs-lookup"><span data-stu-id="ad673-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="ad673-124">En la barra de navegación izquierda, haga clic en **Usuarios** y haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ad673-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="ad673-125">En la **página Nuevo usuario de Skype Empresarial Server,** haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad673-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="ad673-126">Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory** seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="ad673-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="ad673-127">También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán.</span><span class="sxs-lookup"><span data-stu-id="ad673-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="ad673-128">Una vez que haya decidido las opciones de búsqueda, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="ad673-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="ad673-129">En el panel de resultados de búsqueda, seleccione los usuarios que desea agregar y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="ad673-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="ad673-130">En la **página Nuevo usuario de Skype Empresarial Server,** los usuarios seleccionados se muestran en la **pantalla** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad673-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="ad673-131">En la **lista Asignar usuarios a un grupo** de servidores, seleccione el servidor donde deben residir los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad673-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="ad673-132">A continuación se muestra una lista de opciones que puede usar para configurar los objetos.</span><span class="sxs-lookup"><span data-stu-id="ad673-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="ad673-133">**Generar el URI del SIP del usuario**</span><span class="sxs-lookup"><span data-stu-id="ad673-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="ad673-134">**Telefonía**</span><span class="sxs-lookup"><span data-stu-id="ad673-134">**Telephony**</span></span>
    
    - <span data-ttu-id="ad673-135">**URI de línea**</span><span class="sxs-lookup"><span data-stu-id="ad673-135">**Line URI**</span></span>
    
    - <span data-ttu-id="ad673-136">**Directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="ad673-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="ad673-137">**Directiva de versión de clientes**</span><span class="sxs-lookup"><span data-stu-id="ad673-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="ad673-138">**Directiva de PIN**</span><span class="sxs-lookup"><span data-stu-id="ad673-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="ad673-139">**Directiva de acceso externo**</span><span class="sxs-lookup"><span data-stu-id="ad673-139">**External access policy**</span></span>
    
    - <span data-ttu-id="ad673-140">**Directiva de archivado**</span><span class="sxs-lookup"><span data-stu-id="ad673-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="ad673-141">**Directiva de ubicación**</span><span class="sxs-lookup"><span data-stu-id="ad673-141">**Location policy**</span></span>
    
    - <span data-ttu-id="ad673-142">**Directiva de cliente**</span><span class="sxs-lookup"><span data-stu-id="ad673-142">**Client policy**</span></span>
    
    <span data-ttu-id="ad673-143">Para probar la funcionalidad básica, seleccione la opción que prefiera para la opción Generar **URI** de SIP del usuario (las otras opciones de la configuración usan la configuración predeterminada) y, a continuación, haga clic en **Habilitar,** como se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="ad673-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Habilitar usuarios en el Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="ad673-145">Se muestra una página de resumen que muestra una marca de verificación en la **columna Habilitado** para indicar que los usuarios están configurados.</span><span class="sxs-lookup"><span data-stu-id="ad673-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="ad673-146">En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="ad673-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Usuarios agregados al Panel de control de Skype Empresarial Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="ad673-148">Inicie sesión en un equipo que esté unido al dominio y otro usuario en otro equipo del dominio.</span><span class="sxs-lookup"><span data-stu-id="ad673-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="ad673-149">Instale el cliente de Skype Empresarial en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios puedan iniciar sesión en Skype Empresarial Server y puedan enviarse mensajes instantáneos entre sí.</span><span class="sxs-lookup"><span data-stu-id="ad673-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

