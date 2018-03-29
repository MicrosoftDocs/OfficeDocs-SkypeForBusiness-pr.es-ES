---
title: Control de acceso basado en roles (RBAC) para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype para Business Server 2015 incluye grupos de Control de acceso basado en roles (RBAC) para que pueda delegar tareas administrativas manteniendo los altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información acerca de la preparación del bosque, vea Servicios de dominio de Active Directory para Skype para Business Server 2015. Para obtener más información acerca de los grupos específicos creados por la preparación del bosque, ver los cambios realizados por la preparación del bosque en Skype para Business Server en la documentación de implementación.
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a><span data-ttu-id="898df-106">Control de acceso basado en roles (RBAC) para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="898df-106">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="898df-107">Skype para Business Server 2015 incluye grupos de Control de acceso basado en roles (RBAC) para que pueda delegar tareas administrativas manteniendo los altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="898df-107">Skype for Business Server 2015 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="898df-108">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="898df-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="898df-109">Para obtener más información acerca de la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype para Business Server 2015](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="898df-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server 2015](active-directory-domain-services.md).</span></span> <span data-ttu-id="898df-110">Para obtener más información acerca de los grupos específicos creados por la preparación del bosque, vea [los cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="898df-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="898df-111">Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="898df-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="898df-112">Cada rol se asocia con una lista de los cmdlets del Shell de administración de Lync Server que se pueden ejecutar los usuarios de esa función específica.</span><span class="sxs-lookup"><span data-stu-id="898df-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="898df-113">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="898df-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  

