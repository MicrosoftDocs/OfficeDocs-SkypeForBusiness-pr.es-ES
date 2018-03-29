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
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Control de acceso basado en roles (RBAC) para Skype Empresarial Server 2015
 
Skype para Business Server 2015 incluye grupos de Control de acceso basado en roles (RBAC) para que pueda delegar tareas administrativas manteniendo los altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información acerca de la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype para Business Server 2015](active-directory-domain-services.md). Para obtener más información acerca de los grupos específicos creados por la preparación del bosque, vea [los cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol se asocia con una lista de los cmdlets del Shell de administración de Lync Server que se pueden ejecutar los usuarios de esa función específica. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  

