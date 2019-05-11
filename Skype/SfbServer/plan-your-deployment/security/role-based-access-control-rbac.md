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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Control de acceso basado en roles (RBAC) para Skype para Business Server
 
Skype para Business Server incluye los grupos de Control de acceso basado en roles (RBAC) para poder delegar tareas administrativas a la vez mantener altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener información detallada sobre la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype para Business Server](active-directory-domain-services.md). Para obtener información detallada acerca de los grupos específicos creados por la preparación del bosque, vea [cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets de Lync Server Management Shell que se permiten la ejecución de los usuarios de esa función. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  
Obtener más detalles sobre las funciones RBAC pueden encontrarse en:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
