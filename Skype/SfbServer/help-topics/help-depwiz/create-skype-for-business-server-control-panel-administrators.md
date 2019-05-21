---
title: Crear administradores del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Para conceder acceso a Skype empresarial Server 2015, haga lo siguiente:'
ms.openlocfilehash: 6fe5fee80921121c71ccdc4bb6e6de29ac4302fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301879"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="9d371-103">Crear administradores del Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9d371-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="9d371-104">Para conceder acceso a Skype empresarial Server 2015, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d371-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="9d371-105">Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9d371-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9d371-106">Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic con el botón secundario en el contenedor **Usuarios** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9d371-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="9d371-107">En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="9d371-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="9d371-p101">En la pestaña Miembros, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d371-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="9d371-p102">En la pestaña Miembros, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d371-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="9d371-114">El panel de control de Skype empresarial Server es una herramienta de control de acceso basada en roles.</span><span class="sxs-lookup"><span data-stu-id="9d371-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="9d371-115">La pertenencia al grupo CsAdministrator ofrece a un usuario que usa el control total del panel de control de Skype empresarial Server para todas las funciones de configuración disponibles.</span><span class="sxs-lookup"><span data-stu-id="9d371-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="9d371-116">Hay otros roles disponibles diseñados para funciones específicas.</span><span class="sxs-lookup"><span data-stu-id="9d371-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="9d371-117">Los usuarios no tienen que estar habilitados para Skype empresarial Server a fin de que se hagan miembros de los grupos de administración.</span><span class="sxs-lookup"><span data-stu-id="9d371-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="9d371-118">Otros roles son:</span><span class="sxs-lookup"><span data-stu-id="9d371-118">Other roles include:</span></span>
  
- <span data-ttu-id="9d371-119">**CsArchiving:** Los miembros de este grupo pueden realizar todas las funciones de archivado, como la configuración y la administración del rol de servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="9d371-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="9d371-p104">**CsHelpDesk:** los miembros de este grupo pueden ver la configuración e implementar, incluidas las directivas y las propiedades de usuario. Asimismo, los miembros pueden llevar a cabo determinadas tareas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="9d371-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="9d371-p105">**CsLocationAdministrator:** los miembros de este grupo son los que tienen el nivel más bajo de derechos asociados con la administración de 9-1-1 mejorado (E9-1-1). Pueden crear ubicaciones e identificadores de red de E9-1-1, y asociarlos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="9d371-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="9d371-124">**CsResponseGroupAdministrator:** los miembros pueden administrar y configurar el Servicio de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9d371-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="9d371-125">**CsServerAdministrator:** Los miembros pueden administrar, supervisar y solucionar problemas en todos los servidores que ejecutan Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9d371-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="9d371-126">**CsUserAdministrator:** los miembros pueden administrar, habilitar y deshabilitar usuarios, y asignar directivas existentes a usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d371-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="9d371-127">**CsViewOnlyAdministrator:** Los miembros pueden ver la implementación y la configuración de la información del servidor.</span><span class="sxs-lookup"><span data-stu-id="9d371-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="9d371-128">Esta pertenencia permite a un miembro supervisar el estado de los servidores que ejecutan Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d371-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="9d371-129">**CsVoiceAdministrator:** Los miembros pueden crear, configurar y administrar la configuración relacionada con la voz en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9d371-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="9d371-130">Para ayudar a retener la seguridad y la integridad de control de acceso basada en roles, agregue usuarios a los grupos que definen qué función realiza el usuario en la administración de la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9d371-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

