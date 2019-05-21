---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de chat persistente para habilitar la configuración inicial y la administración de los servicios de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273885"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="44d54-103">Crear un administrador de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="44d54-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="44d54-104">**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de chat persistente para habilitar la configuración inicial y la administración de los servicios de chat persistentes en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="44d54-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="44d54-105">En Skype empresarial Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o varios grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="44d54-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="44d54-106">El control de acceso basado en roles (RBAC) se usa para conceder privilegios asignando a los usuarios a roles administrativos predefinidos de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="44d54-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="44d54-107">Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44d54-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="44d54-108">Los miembros del grupo de seguridad de administrador de chat persistente, CsPersistentChatAdministrator, tienen acceso a los cmdlets del servidor de chat persistentes, que se pueden ejecutar con el shell de administración de Skype empresarial Server o Skype empresarial. Panel de control del servidor.</span><span class="sxs-lookup"><span data-stu-id="44d54-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="44d54-109">Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="44d54-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="44d54-110">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="44d54-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="44d54-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="44d54-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="44d54-112">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="44d54-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="44d54-113">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="44d54-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="44d54-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="44d54-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="44d54-115">Para agregar un usuario al grupo de seguridad del administrador de chat persistente, CsPersistentChatAdministrator, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="44d54-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="44d54-116">Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44d54-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="44d54-117">Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44d54-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="44d54-118">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.</span><span class="sxs-lookup"><span data-stu-id="44d54-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="44d54-119">Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="44d54-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="44d54-120">En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="44d54-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="44d54-121">En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="44d54-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="44d54-122">En el cuadro de diálogo Propiedades, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="44d54-122">In the Properties dialog box, click OK.</span></span>
    

