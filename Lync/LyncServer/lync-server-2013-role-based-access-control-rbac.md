---
title: 'Lync Server 2013: control de acceso basado en roles (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577f9de82bfbd75ff85935de9acfb2b8b579a72f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="a3f93-102">Control de acceso basado en roles (RBAC) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3f93-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3f93-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a3f93-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="a3f93-104">Microsoft Lync Server 2013 incluye grupos de control de acceso basado en roles (RBAC) para permitirle delegar tareas administrativas y mantener altos estándares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3f93-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="a3f93-105">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="a3f93-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="a3f93-106">Para obtener más información sobre la preparación del bosque, consulte [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="a3f93-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="a3f93-107">Para obtener información detallada sobre los grupos específicos creados por la preparación del bosque, vea [cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="a3f93-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="a3f93-108">Con RBAC, el privilegio administrativo se otorga asignando roles administrativos predefinidos a los usuarios, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="a3f93-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="a3f93-109">Cada rol está asociado a una lista específica de cmdlets del shell de administración de Lync Server que los usuarios de ese rol pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a3f93-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="a3f93-110">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="a3f93-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="a3f93-111">Para obtener más información, consulte [planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="a3f93-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

