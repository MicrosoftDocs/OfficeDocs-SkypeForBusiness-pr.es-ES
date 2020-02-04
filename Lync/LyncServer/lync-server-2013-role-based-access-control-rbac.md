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
ms.openlocfilehash: 2fc2da0c832ded3c0241d3e50197f98f07c2a96a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="76746-102">Control de acceso basado en roles (RBAC) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76746-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76746-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="76746-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="76746-104">Microsoft Lync Server 2013 incluye grupos de control de acceso basado en roles (RBAC) que le permiten delegar tareas administrativas a la vez que se mantienen estándares altos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="76746-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="76746-105">Estos grupos se crean durante la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="76746-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="76746-106">Para obtener más información sobre la preparación del bosque, vea [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="76746-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="76746-107">Para obtener información sobre los grupos específicos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="76746-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="76746-108">Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos, incluidos los 11 roles predefinidos que cubren muchas de las tareas administrativas más habituales.</span><span class="sxs-lookup"><span data-stu-id="76746-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="76746-109">Cada rol está asociado con una lista específica de cmdlets del shell de administración de Lync Server en los que se permite la ejecución de los usuarios de ese rol.</span><span class="sxs-lookup"><span data-stu-id="76746-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="76746-110">Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben las capacidades administrativas que requiere su trabajo.</span><span class="sxs-lookup"><span data-stu-id="76746-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="76746-111">Para obtener más información, vea [planificación de control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="76746-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

