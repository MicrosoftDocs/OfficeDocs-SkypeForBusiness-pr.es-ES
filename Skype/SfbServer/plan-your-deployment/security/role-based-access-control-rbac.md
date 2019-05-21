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
ms.openlocfilehash: 493af102ae42658d51cfcb5d65fde6c26596d82d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296843"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Control de acceso basado en roles (RBAC) para Skype empresarial Server
 
Skype empresarial Server incluye grupos de control de acceso basado en roles (RBAC) que le permiten delegar tareas administrativas a la vez que se mantienen estándares altos de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener más información sobre la preparación del bosque, consulte [servicios de dominio de Active Directory para Skype empresarial Server](active-directory-domain-services.md). Para obtener información sobre los grupos específicos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Skype empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets del shell de administración de Lync Server en los que se permite la ejecución de los usuarios de ese rol. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  
Para obtener más información sobre los roles RBAC, visite:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
