---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: lea este tema para obtener información sobre cómo crear un rol de administrador de servidor de chat persistente para habilitar la configuración inicial y la administración de servicios de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802100"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="8fff9-103">Crear un administrador de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8fff9-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8fff9-104">**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador de servidor de chat persistente para habilitar la configuración inicial y la administración de servicios de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8fff9-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8fff9-105">En Skype Empresarial Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o más grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="8fff9-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="8fff9-106">Role-Based access control de acceso (RBAC) se usa para conceder privilegios asignando usuarios a roles administrativos predefinidos de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8fff9-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="8fff9-107">Estos roles corresponden a grupos de seguridad universales en los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fff9-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="8fff9-108">A los miembros del grupo de seguridad administrador de chat persistente, CsPersistentChatAdministrator, se les concede acceso a los cmdlets del servidor de chat persistente, que se pueden ejecutar mediante el Shell de administración de Skype Empresarial Server o el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8fff9-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8fff9-109">Antes de configurar y administrar el servidor de chat persistente, asegúrese de que se han concedido los permisos y derechos de usuario adecuados y de que todos los usuarios que actuarán como administradores de chat persistente se agregarán al grupo de seguridad administrador de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8fff9-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="8fff9-110">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8fff9-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8fff9-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="8fff9-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="8fff9-112">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="8fff9-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="8fff9-113">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8fff9-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="8fff9-114">Crear un administrador de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8fff9-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="8fff9-115">Para agregar un usuario al grupo de seguridad de administrador de chat persistente, CsPersistentChatAdministrator, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8fff9-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="8fff9-116">Con una cuenta que tenga permiso para modificar la pertenencia a un grupo de Active Directory, inicie sesión en un equipo donde se hayan instalado usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fff9-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="8fff9-117">Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y después en Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fff9-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="8fff9-118">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.</span><span class="sxs-lookup"><span data-stu-id="8fff9-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="8fff9-119">Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="8fff9-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="8fff9-120">En el cuadro de diálogo Propiedades, en la pestaña Miembros, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8fff9-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="8fff9-121">En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre de usuario o el nombre para mostrar del usuario que se agregará al grupo en el cuadro Escribir los nombres de objeto que desea seleccionar y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8fff9-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="8fff9-122">En el cuadro de diálogo Propiedades, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8fff9-122">In the Properties dialog box, click OK.</span></span>
    

