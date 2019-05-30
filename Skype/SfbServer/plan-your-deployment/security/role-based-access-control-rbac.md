---
title: Control de acceso basado en roles (RBAC) para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype empresarial Server incluye grupos de control de acceso basado en roles (RBAC) que le permiten delegar tareas administrativas a la vez que se mantienen estándares altos de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, consulte servicios de dominio de Active Directory para Skype empresarial Server. Para obtener información sobre los grupos específicos creados por la preparación del bosque, consulte cambios hechos por la preparación del bosque en Skype empresarial Server en la documentación de implementación.
ms.openlocfilehash: a2c15766fd1b031247a5eb0f299e689bf075eb07
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548488"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="ac1da-106">Control de acceso basado en roles (RBAC) para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ac1da-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="ac1da-107">Skype empresarial Server incluye grupos de control de acceso basado en roles (RBAC) que le permiten delegar tareas administrativas a la vez que se mantienen estándares altos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ac1da-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="ac1da-108">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="ac1da-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="ac1da-109">Para obtener más información sobre la preparación del bosque, consulte [servicios de dominio de Active Directory para Skype empresarial Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="ac1da-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="ac1da-110">Para obtener información sobre los grupos específicos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Skype empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ac1da-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="ac1da-111">Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="ac1da-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="ac1da-112">Cada rol está asociado con una lista específica de cmdlets del shell de administración de Lync Server en los que se permite la ejecución de los usuarios de ese rol.</span><span class="sxs-lookup"><span data-stu-id="ac1da-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="ac1da-113">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac1da-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="ac1da-114">Puede encontrar más información sobre los roles RBAC en la [planeación de control de acceso basado en roles](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="ac1da-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
