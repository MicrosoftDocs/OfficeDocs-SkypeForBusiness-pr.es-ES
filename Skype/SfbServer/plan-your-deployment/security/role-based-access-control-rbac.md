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
description: Skype para Business Server 2015 incluye grupos de Control de acceso basado en roles (RBAC) para poder delegar tareas administrativas a la vez mantener altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener información detallada sobre la preparación del bosque, vea Servicios de dominio de Active Directory para Skype for Business Server 2015. Para obtener información detallada acerca de los grupos específicos creados por la preparación del bosque, vea cambios realizados por la preparación del bosque en Skype para Business Server en la documentación de implementación.
ms.openlocfilehash: 68c47119d200ed4a5db0c8e70992707a0b5c3084
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546588"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Control de acceso basado en roles (RBAC) para Skype Empresarial Server 2015
 
Skype para Business Server 2015 incluye grupos de Control de acceso basado en roles (RBAC) para poder delegar tareas administrativas a la vez mantener altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener información detallada sobre la preparación del bosque, vea [Servicios de dominio de Active Directory para Skype para Business Server 2015](active-directory-domain-services.md). Para obtener información detallada acerca de los grupos específicos creados por la preparación del bosque, vea [cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets de Lync Server Management Shell que se permiten la ejecución de los usuarios de esa función. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. 
  
Obtener más detalles sobre las funciones RBAC pueden encontrarse en la documentación de 2013 en:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
