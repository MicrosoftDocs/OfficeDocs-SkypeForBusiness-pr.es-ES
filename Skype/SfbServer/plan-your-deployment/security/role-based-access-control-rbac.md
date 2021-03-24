---
title: Control de acceso basado en roles (RBAC) para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, vea Servicios de dominio de Active Directory para Skype Empresarial Server. Para obtener más información sobre los grupos específicos creados por la preparación de bosques, vea Changes made by forest preparation in Skype for Business Server en la documentación sobre implementación.
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104216"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="fb590-106">Control de acceso basado en roles (RBAC) para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fb590-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="fb590-107">Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb590-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="fb590-108">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="fb590-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="fb590-109">Para obtener más información sobre la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype Empresarial Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb590-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="fb590-110">Para obtener más información sobre los grupos específicos creados por la preparación de bosques, vea [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="fb590-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="fb590-111">Con RBAC, el privilegio administrativo se otorga asignando roles administrativos predefinidos a los usuarios, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="fb590-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="fb590-112">Cada rol está asociado con una lista específica de cmdlets del Shell de administración de Skype Empresarial Server que los usuarios de ese rol pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="fb590-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="fb590-113">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="fb590-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="fb590-114">Puede encontrar más detalles sobre los roles RBAC en [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="fb590-114">More details on RBAC roles can be found at [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>