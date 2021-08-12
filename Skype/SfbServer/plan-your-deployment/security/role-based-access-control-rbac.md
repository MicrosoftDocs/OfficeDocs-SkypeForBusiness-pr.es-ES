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
description: Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, vea Servicios de dominio de Active Directory para Skype Empresarial Server. Para obtener más información sobre los grupos específicos creados por la preparación del bosque, vea Changes made by forest preparation in Skype Empresarial Server en la documentación de implementación.
ms.openlocfilehash: 8b4dbfc85a92063bff7e5c57ee18ccc9b80bb4e08b0716fd1cac0666f1862fb0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337728"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Control de acceso basado en roles (RBAC) para Skype Empresarial Server
 
Skype Empresarial Server incluye Role-Based de control de acceso (RBAC) para permitirle delegar tareas administrativas al mismo tiempo que mantiene altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, vea Servicios de dominio [de Active Directory para Skype Empresarial Server](active-directory-domain-services.md). Para obtener más información sobre los grupos específicos creados por la preparación del bosque, vea [Changes made by forest preparation in Skype Empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, el privilegio administrativo se otorga asignando roles administrativos predefinidos a los usuarios, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets del Shell de administración Skype Empresarial Server que los usuarios de ese rol pueden ejecutar. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  
Puede encontrar más detalles sobre los roles RBAC en [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).