---
title: 'Lync Server 2013: mover usuarios a Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f490a50ade6c10d37a478729c46a5545970afb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="26fc0-102">Mover usuarios a Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26fc0-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26fc0-103">_**Última modificación del tema:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="26fc0-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="26fc0-104">Antes de iniciar la migración de usuarios a Lync Online, debe hacer una copia de seguridad de los datos de usuario asociados con las cuentas que se van a mover.</span><span class="sxs-lookup"><span data-stu-id="26fc0-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="26fc0-105">No todos los datos de usuario se mueven con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="26fc0-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="26fc0-106">Para obtener más información, vea [requisitos de copia de seguridad y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="26fc0-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="26fc0-107">Migrar la configuración del usuario a Lync Online</span><span class="sxs-lookup"><span data-stu-id="26fc0-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="26fc0-108">La configuración de usuario se mueve con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="26fc0-108">User settings are moved with the user account.</span></span> <span data-ttu-id="26fc0-109">Algunas configuraciones locales no se mueven con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="26fc0-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="26fc0-110">Mover usuarios piloto a Lync Online</span><span class="sxs-lookup"><span data-stu-id="26fc0-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="26fc0-111">Antes de empezar a mover usuarios a Lync Online, es posible que desee mover algunos usuarios piloto para confirmar que el entorno está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="26fc0-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="26fc0-112">A continuación, puede comprobar que las características y servicios de Lync funcionan como se esperaba antes de intentar mover otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="26fc0-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="26fc0-113">Para mover un usuario local a su inquilino de Lync Online, ejecute los siguientes cmdlets en el shell de administración de Lync Server, con las credenciales de administrador para su inquilino de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="26fc0-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="26fc0-114">Reemplace "username@contoso.com" por la información del usuario que desea mover.</span><span class="sxs-lookup"><span data-stu-id="26fc0-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="26fc0-115">El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedado,\<en el\>siguiente formato: https://Grupo de FQDN/HostedMigration/hostedmigrationService.SVC.</span><span class="sxs-lookup"><span data-stu-id="26fc0-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="26fc0-116">Para determinar la dirección URL del servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para su cuenta de inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="26fc0-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="26fc0-117">**Para determinar la dirección URL del servicio de migración hospedado de su inquilino de Office 365**</span><span class="sxs-lookup"><span data-stu-id="26fc0-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="26fc0-118">Inicie sesión en su inquilino de Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="26fc0-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="26fc0-119">Abra el **centro de administración de Lync**.</span><span class="sxs-lookup"><span data-stu-id="26fc0-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="26fc0-120">Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="26fc0-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="26fc0-121">Una dirección URL de ejemplo tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="26fc0-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="26fc0-122">Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26fc0-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="26fc0-123">Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.</span><span class="sxs-lookup"><span data-stu-id="26fc0-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="26fc0-124">La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="26fc0-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="26fc0-125">Mover usuarios a Lync Online</span><span class="sxs-lookup"><span data-stu-id="26fc0-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="26fc0-126">Puede mover varios usuarios mediante el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con el parámetro – filter para seleccionar los usuarios con una propiedad específica asignada a las cuentas de usuario, como RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="26fc0-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="26fc0-127">A continuación, puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26fc0-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="26fc0-128">También puede usar el parámetro – OU para recuperar todos los usuarios de la unidad organizativa especificada, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26fc0-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="26fc0-129">Compruebe las características y configuración de usuario de Lync Online</span><span class="sxs-lookup"><span data-stu-id="26fc0-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="26fc0-130">Puede comprobar que el usuario se ha movido con éxito de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="26fc0-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="26fc0-p107">Vea el estado del usuario en el Panel de Control de Lync Online. El indicador visual de los usuarios locales y los usuarios en línea es diferente.</span><span class="sxs-lookup"><span data-stu-id="26fc0-p107">View the status of the user in the Lync Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="26fc0-133">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="26fc0-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

