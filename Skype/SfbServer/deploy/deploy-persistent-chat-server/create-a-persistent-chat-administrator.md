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
description: 'Resumen: Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de Chat persistente para habilitar la configuración inicial y la administración de servicios de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: df2c62964d6c1d315f6fda04132c829d235e6038
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966118"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="75ae3-103">Crear un administrador de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="75ae3-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75ae3-104">**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de Chat persistente para habilitar la configuración inicial y la administración de servicios de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75ae3-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75ae3-105">En Skype para Business Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o varios grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="75ae3-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="75ae3-106">Control de acceso basado en roles (RBAC) se usa para conceder privilegios mediante la asignación de usuarios a Skype predefinido para las funciones administrativas de Business Server.</span><span class="sxs-lookup"><span data-stu-id="75ae3-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="75ae3-107">Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75ae3-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="75ae3-108">Los miembros del grupo de seguridad Persistent Chat Administrator, CsPersistentChatAdministrator, se les concede acceso a los cmdlets de servidor de Chat persistente, que se pueden ejecutar mediante el Skype para Shell de administración de servidor empresarial o el Skype para la empresa Panel de Control de servidor.</span><span class="sxs-lookup"><span data-stu-id="75ae3-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="75ae3-109">Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="75ae3-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="75ae3-110">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="75ae3-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="75ae3-111">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="75ae3-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="75ae3-112">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="75ae3-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="75ae3-113">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75ae3-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="75ae3-114">Crear un administrador de chat persistente</span><span class="sxs-lookup"><span data-stu-id="75ae3-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="75ae3-115">Para agregar un usuario al grupo de seguridad Persistent Chat Administrator, CsPersistentChatAdministrator, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="75ae3-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="75ae3-116">Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75ae3-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="75ae3-117">Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75ae3-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="75ae3-118">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.</span><span class="sxs-lookup"><span data-stu-id="75ae3-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="75ae3-119">Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="75ae3-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="75ae3-120">En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="75ae3-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="75ae3-121">En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="75ae3-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="75ae3-122">En el cuadro de diálogo Propiedades, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="75ae3-122">In the Properties dialog box, click OK.</span></span>
    

