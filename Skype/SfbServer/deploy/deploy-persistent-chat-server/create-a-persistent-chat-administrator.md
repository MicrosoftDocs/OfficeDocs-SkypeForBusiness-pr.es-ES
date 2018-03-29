---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: Leer este tema para aprender a crear una función de administrador de servidor de charla persistente para habilitar la configuración inicial y la administración de servicios de Chat persistentes en Skype para Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="9f01d-103">Crear un administrador de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f01d-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f01d-104">**Resumen:** Lea este tema para aprender a crear una función de administrador de servidor de charla persistente para habilitar la configuración inicial y la administración de servicios de Chat persistentes en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9f01d-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9f01d-105">En Skype para Business Server, los usuarios que realizan tareas específicas deben asignarse como miembros de grupos específicos de uno o más.</span><span class="sxs-lookup"><span data-stu-id="9f01d-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="9f01d-106">Control de acceso basado en roles (RBAC) se utiliza para conceder privilegios asignando usuarios a Skype predefinido para las funciones administrativas de Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f01d-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="9f01d-107">Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f01d-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="9f01d-108">Los miembros del grupo de seguridad Administrador de Chat persistentes, CsPersistentChatAdministrator, se conceden acceso a los cmdlets persistente Chat Server, que se pueden ejecutar usando el Skype para el Shell de administración de servidor de negocios o el Skype para empresas Panel de Control de servidor.</span><span class="sxs-lookup"><span data-stu-id="9f01d-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="9f01d-109">Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9f01d-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="9f01d-110">Crear un administrador de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9f01d-110">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="9f01d-111">Para agregar un usuario al grupo de seguridad Administrador de Chat persistentes, CsPersistentChatAdministrator, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9f01d-111">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="9f01d-112">Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f01d-112">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="9f01d-113">Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f01d-113">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="9f01d-114">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.</span><span class="sxs-lookup"><span data-stu-id="9f01d-114">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="9f01d-115">Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="9f01d-115">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="9f01d-116">En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9f01d-116">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="9f01d-117">En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="9f01d-117">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="9f01d-118">En el cuadro de diálogo Propiedades, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="9f01d-118">In the Properties dialog box, click OK.</span></span>
    

