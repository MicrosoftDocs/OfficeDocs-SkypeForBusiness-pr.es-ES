---
title: 'Lync Server 2013: administración de usuarios en una implementación híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="9c79e-102">Administración de usuarios en una implementación híbrida de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c79e-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c79e-103">_**Última modificación del tema:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="9c79e-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="9c79e-104">Puede administrar la configuración y las directivas de usuario para los usuarios migrados a Lync Online mediante las características de administración de usuarios disponibles en el portal en línea de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c79e-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="9c79e-105">Necesita iniciar sesión con una cuenta de administrador de inquilinos para realizar tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="9c79e-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="9c79e-106">Mover usuarios a local</span><span class="sxs-lookup"><span data-stu-id="9c79e-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="9c79e-107">Esta sección solo se aplica a los usuarios que se han creado y habilitado para Lync local y después se han movido de una implementación local a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9c79e-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="9c79e-108">Si quiere mover los usuarios que se crearon en Lync Online (y nunca se habilitaron para Lync en una implementación local), vea <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c79e-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="9c79e-109">Ejecute los siguientes cmdlets para mover un usuario de Lync Online de nuevo a Lync local:</span><span class="sxs-lookup"><span data-stu-id="9c79e-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="9c79e-110">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** necesita ser la dirección URL al grupo donde se ejecuta el servicio de migración hospedado, con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="9c79e-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="9c79e-111">Https://\<FQDN\>del grupo de/HostedMigration/hostedmigrationService.SVC.</span><span class="sxs-lookup"><span data-stu-id="9c79e-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="9c79e-112">Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c79e-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="9c79e-113">**Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365**</span><span class="sxs-lookup"><span data-stu-id="9c79e-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="9c79e-114">Inicie sesión en el inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="9c79e-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="9c79e-115">Abra el **centro de administración de Lync**.</span><span class="sxs-lookup"><span data-stu-id="9c79e-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="9c79e-116">Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="9c79e-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="9c79e-117">Una dirección URL de ejemplo es muy similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c79e-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="9c79e-118">Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:</span><span class="sxs-lookup"><span data-stu-id="9c79e-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="9c79e-119">Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.</span><span class="sxs-lookup"><span data-stu-id="9c79e-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="9c79e-120">La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, necesita ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c79e-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

