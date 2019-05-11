---
title: Control de acceso basado en roles (RBAC) para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype para Business Server incluye los grupos de Control de acceso basado en roles (RBAC) para poder delegar tareas administrativas a la vez mantener altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener información detallada sobre la preparación del bosque, vea Servicios de dominio de Active Directory para Skype for Business Server. Para obtener información detallada acerca de los grupos específicos creados por la preparación del bosque, vea cambios realizados por la preparación del bosque en Skype para Business Server en la documentación de implementación.
ms.openlocfilehash: 34f5fa455b865e40ba2ad21298e37d0948d2a810
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914208"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="14d17-106">Control de acceso basado en roles (RBAC) para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14d17-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="14d17-107">Skype para Business Server incluye los grupos de Control de acceso basado en roles (RBAC) para poder delegar tareas administrativas a la vez mantener altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14d17-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="14d17-108">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="14d17-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="14d17-109">Para obtener información detallada sobre la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype para Business Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="14d17-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="14d17-110">Para obtener información detallada acerca de los grupos específicos creados por la preparación del bosque, vea [cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="14d17-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="14d17-111">Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="14d17-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="14d17-112">Cada rol está asociado con una lista específica de cmdlets de Lync Server Management Shell que se permiten la ejecución de los usuarios de esa función.</span><span class="sxs-lookup"><span data-stu-id="14d17-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="14d17-113">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="14d17-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="14d17-114">Obtener más detalles sobre las funciones RBAC pueden encontrarse en:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span><span class="sxs-lookup"><span data-stu-id="14d17-114">More details on RBAC roles can be found at: https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span></span>
