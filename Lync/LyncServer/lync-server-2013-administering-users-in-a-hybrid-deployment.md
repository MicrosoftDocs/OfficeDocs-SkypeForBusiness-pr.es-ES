---
title: 'Lync Server 2013: administración de usuarios en una implementación híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b09ca3c5a80215c0a2d63a018150361671df6859
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="3587d-102">Administración de usuarios en una implementación híbrida de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3587d-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3587d-103">_**Última modificación del tema:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="3587d-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="3587d-104">Puede administrar la configuración y las directivas de usuario para los usuarios migrados a Lync Online mediante las características de administración de usuarios disponibles en el portal de Microsoft Office 365 online.</span><span class="sxs-lookup"><span data-stu-id="3587d-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="3587d-105">Debe iniciar sesión con la cuenta de administrador de inquilinos para realizar tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="3587d-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="3587d-106">Mover a usuarios localmente</span><span class="sxs-lookup"><span data-stu-id="3587d-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="3587d-107">Esta sección solo se aplica a los usuarios que se crearon y habilitaron para Lync local y, a continuación, se movieron de una implementación local a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3587d-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="3587d-108">Si quiere mover usuarios que se crearon en Lync Online (y que nunca se habilitaron para Lync en una implementación local), vea <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3587d-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="3587d-109">Ejecute los siguientes cmdlets para mover un usuario de Lync Online de nuevo a Lync local:</span><span class="sxs-lookup"><span data-stu-id="3587d-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="3587d-110">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedado, en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="3587d-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="3587d-111">Https://\<FQDN\>del grupo de servidores de/HostedMigration/hostedmigrationService.SVC.</span><span class="sxs-lookup"><span data-stu-id="3587d-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="3587d-112">Para determinar la dirección URL del servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para la cuenta de su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3587d-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>

<span data-ttu-id="3587d-113">**Para determinar la dirección URL del servicio de migración hospedado para su organización de Office 365**</span><span class="sxs-lookup"><span data-stu-id="3587d-113">**To determine the Hosted Migration Service URL for your Office 365 organization**</span></span>

1.  <span data-ttu-id="3587d-114">Inicie sesión en su organización de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="3587d-114">Login to your Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="3587d-115">Abra el **centro de administración de Lync**.</span><span class="sxs-lookup"><span data-stu-id="3587d-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="3587d-116">Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="3587d-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="3587d-117">Una dirección URL de ejemplo tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3587d-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="3587d-118">Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3587d-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="3587d-119">Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.</span><span class="sxs-lookup"><span data-stu-id="3587d-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="3587d-120">La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3587d-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

