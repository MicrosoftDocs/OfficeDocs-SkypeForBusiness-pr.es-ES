---
title: Configurar las reglas de número de identificación personal (PIN) de conferencia de acceso telefónico local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16b56e1809f9ffefa37065a208340e1143e38487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="f1fb6-102">Configurar reglas de número de identificación personal (PIN) de conferencia de acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1fb6-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1fb6-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="f1fb6-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="f1fb6-104">Lync Server 2013 los usuarios que tienen credenciales de servicios de dominio de Active Directory (AD DS) en su organización pueden unirse a conferencias de acceso telefónico local como usuarios autenticados mediante un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="f1fb6-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="f1fb6-105">La directiva de PIN define las reglas de funcionamiento de los PIN de conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="f1fb6-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="f1fb6-p102">Puede crear una nueva directiva de PIN si desea aplicar una directiva específica a un sitio a un grupo de usuarios determinado. Si desea usar la misma directiva de PIN para toda la organización, puede usar la directiva de PIN global y modificarla según sea necesario. Las directivas de PIN se aplican a usuarios que van del ámbito más limitado al ámbito más extenso. Si asigna una directiva de PIN de usuario a un usuario, dicha configuración tendrá preferencia. Si no asigna una directiva de usuario, se aplica la directiva de PIN de sitio, si existe. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva de PIN global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f1fb6-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1fb6-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f1fb6-112">In This Section</span></span>

  - [<span data-ttu-id="f1fb6-113">Modificar la configuración de PIN de conferencia de acceso telefónico local predeterminada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1fb6-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="f1fb6-114">Crear o modificar la configuración de PIN de conferencia de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="f1fb6-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="f1fb6-115">Eliminar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1fb6-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

