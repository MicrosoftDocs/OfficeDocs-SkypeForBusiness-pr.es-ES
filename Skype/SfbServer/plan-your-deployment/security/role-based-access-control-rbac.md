---
title: Control de acceso basado en roles (RBAC) para Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, vea Servicios de dominio de Active Directory para Skype Empresarial Server. Para obtener más información sobre los grupos específicos creados por la preparación del bosque, vea Changes made by forest preparation in Skype Empresarial Server en la documentación de implementación.
ms.openlocfilehash: 3b7bec4bc5a8bfcad0a75f2e1652fd00377fde13
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398714"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Control de acceso basado en roles (RBAC) para Skype Empresarial Server
 
Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información acerca de la preparación del bosque, vea [Active Directory Domain Services for Skype Empresarial Server](active-directory-domain-services.md). Para obtener más información sobre los grupos específicos creados por la preparación del bosque, vea [Changes made by forest preparation in Skype Empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, el privilegio administrativo se otorga asignando roles administrativos predefinidos a los usuarios, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets del Shell de administración Skype Empresarial Server que los usuarios de ese rol pueden ejecutar. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  
Puede encontrar más información sobre los roles RBAC en [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).