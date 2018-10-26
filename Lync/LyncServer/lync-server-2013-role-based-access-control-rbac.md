---
title: Control de acceso basado en roles (RBAC) para Lync Server 2013
TOCTitle: Control de acceso basado en roles (RBAC) para Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59679373
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control de acceso basado en roles (RBAC) para Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

Microsoft Lync Server 2013 incluye grupos de control de acceso basado en roles (RBAC) para permitirle delegar tareas administrativas y mantener al mismo tiempo altos estándares de seguridad. Estos grupos se crean durante la preparación del bosque. Para obtener información detallada acerca de la preparación del bosque, consulte [Servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md). Para más información detallada sobre los grupos específicos creados por la preparación del bosque, consulte [Cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.

Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales. Cada rol está asociado con una lista específica de cmdlets de Shell de administración de Lync Server que pueden usar los usuarios con dicho rol. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo. Para más información, consulte [Planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación sobre planeación.

