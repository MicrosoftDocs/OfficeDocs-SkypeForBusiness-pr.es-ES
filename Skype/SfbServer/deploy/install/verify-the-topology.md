---
title: Comprobar la topología de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumen: Obtenga información sobre cómo comprobar la Skype para la topología de servidor empresarial y los servidores de Active Directory funcionan según lo previsto. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 03dfb45c03aa104cc5a9b265a37c347380590877
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210798"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="dc174-104">Comprobar la topología de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dc174-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="dc174-105">**Resumen:** Obtenga información sobre cómo comprobar la Skype para la topología de servidor empresarial y los servidores de Active Directory funcionan según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="dc174-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="dc174-106">Descargue una versión de prueba gratuita de Skype para Business Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="dc174-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="dc174-107">Una vez que tenga la topología publicada y el Skype para los componentes del sistema de Business Server instalado en cada uno de los servidores de la topología, está listo para comprobar que la topología funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="dc174-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="dc174-108">Esto incluye la comprobación de que la configuración se propaga a todos los servidores de Active Directory para que todo el dominio sepa que Skype para la empresa está disponible en el dominio.</span><span class="sxs-lookup"><span data-stu-id="dc174-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="dc174-109">Se pueden realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="dc174-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="dc174-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="dc174-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="dc174-111">Comprobar la topología es el paso 8 de 8.</span><span class="sxs-lookup"><span data-stu-id="dc174-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="dc174-113">Probar la implementación del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dc174-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="dc174-114">Es el paso final probar el grupo de servidores Front-End y confirme que Skype para los clientes empresariales puede comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="dc174-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="dc174-115">Agregar usuarios y comprobar la conectividad del cliente</span><span class="sxs-lookup"><span data-stu-id="dc174-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="dc174-116">Use usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory de la función de administrador para la Skype para la implementación de Business Server (en el que está instalado Skype para el Panel de Control de servidor empresarial) al grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="dc174-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc174-117">Si no agrega los usuarios y grupos al grupo CsAdministors, recibirá un error cuando se abre Skype para el Panel de Control de servidor empresarial que lee, "no autorizado: acceso denegado debido a un error de autorización de acceso basado en roles (RBAC) de control ."</span><span class="sxs-lookup"><span data-stu-id="dc174-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="dc174-118">Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="dc174-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc174-119">La cuenta de usuario no puede ser el administrador local de cualquier servidor que ejecute Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc174-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="dc174-120">Use la cuenta administrativa para iniciar sesión en el equipo donde está instalado Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc174-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="dc174-121">Inicie Skype para el Panel de Control de servidor empresarial y, a continuación, proporcione las credenciales, si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="dc174-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="dc174-122">Skype para el Panel de Control de servidor empresarial muestra información sobre la implementación.</span><span class="sxs-lookup"><span data-stu-id="dc174-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="dc174-123">En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que es una marca de verificación verde para el estado de la replicación junto a cada Skype para el rol de servidor de negocio que se ha implementado y poner en línea.</span><span class="sxs-lookup"><span data-stu-id="dc174-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="dc174-124">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc174-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="dc174-125">En la página **Nuevo Skype para usuarios del servidor de empresa** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dc174-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="dc174-p105">Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc174-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="dc174-129">En el panel de resultados de la búsqueda, seleccione los usuarios que desea agregar y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dc174-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="dc174-130">En la página **Nuevo Skype para usuarios del servidor de empresa** , los usuarios seleccionados se encuentran en la visualización de **los usuarios** .</span><span class="sxs-lookup"><span data-stu-id="dc174-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="dc174-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="dc174-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="dc174-132">Aquí presentamos una lista de opciones que puede usar para configurar los objetos.</span><span class="sxs-lookup"><span data-stu-id="dc174-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="dc174-133">**Generar el URI de SIP del usuario**</span><span class="sxs-lookup"><span data-stu-id="dc174-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="dc174-134">**Telefonía**</span><span class="sxs-lookup"><span data-stu-id="dc174-134">**Telephony**</span></span>
    
    - <span data-ttu-id="dc174-135">**URI de línea**</span><span class="sxs-lookup"><span data-stu-id="dc174-135">**Line URI**</span></span>
    
    - <span data-ttu-id="dc174-136">**Directiva de conferencia**</span><span class="sxs-lookup"><span data-stu-id="dc174-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="dc174-137">**Directiva de versión de cliente**</span><span class="sxs-lookup"><span data-stu-id="dc174-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="dc174-138">**Directiva de PIN**</span><span class="sxs-lookup"><span data-stu-id="dc174-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="dc174-139">**Directiva de acceso externo**</span><span class="sxs-lookup"><span data-stu-id="dc174-139">**External access policy**</span></span>
    
    - <span data-ttu-id="dc174-140">**Directiva de archivado**</span><span class="sxs-lookup"><span data-stu-id="dc174-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="dc174-141">**Directiva de ubicación**</span><span class="sxs-lookup"><span data-stu-id="dc174-141">**Location policy**</span></span>
    
    - <span data-ttu-id="dc174-142">**Directiva de cliente**</span><span class="sxs-lookup"><span data-stu-id="dc174-142">**Client policy**</span></span>
    
    <span data-ttu-id="dc174-143">Para probar la funcionalidad básica, seleccione la opción que prefiera para la configuración de **URI de SIP del usuario de generar** (las demás opciones en las configuraciones de uso predeterminado) y, a continuación, haga clic en **Habilitar**, tal como se muestra en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="dc174-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Habilita a los usuarios del Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="dc174-p107">Se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los usuarios están configurados. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="dc174-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Usuarios añadidos al Panel de control del servidor de Skype Empresarial.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="dc174-148">Es preciso que un usuario inicie sesión en un equipo integrado en el dominio y que otro usuario lo haga en otro equipo del dominio.</span><span class="sxs-lookup"><span data-stu-id="dc174-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="dc174-149">Instalar Skype para clientes empresariales en cada uno de los dos equipos cliente y, a continuación, compruebe que los dos usuarios pueden iniciar sesión en Skype para Business Server y pueden enviar mensajes instantáneos a los otros.</span><span class="sxs-lookup"><span data-stu-id="dc174-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

