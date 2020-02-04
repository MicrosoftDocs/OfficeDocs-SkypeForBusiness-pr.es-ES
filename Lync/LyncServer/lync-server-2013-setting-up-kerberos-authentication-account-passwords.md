---
title: 'Lync Server 2013: Configurar las contraseñas de cuenta de autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c156e26a54e9762b1b57d1513f37cb7d7088cee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="140dd-102">Configurar las contraseñas de cuenta de autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140dd-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="140dd-103">_**Última modificación del tema:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="140dd-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="140dd-104">Después de crear el objeto de equipo para la cuenta de autenticación Kerberos, puede configurar la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="140dd-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="140dd-105">Ejecute el cmdlet de Windows PowerShell para establecer la contraseña de la cuenta Kerberos en un servidor.</span><span class="sxs-lookup"><span data-stu-id="140dd-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="140dd-106">Puede establecer la contraseña en el objeto que ha creado para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="140dd-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="140dd-107">La contraseña puede establecerse en un valor conocido pero, de forma predeterminada, es una contraseña aleatoria.</span><span class="sxs-lookup"><span data-stu-id="140dd-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="140dd-108">La contraseña está disponible para todos los orígenes de autenticación Kerberos que usan la cuenta.</span><span class="sxs-lookup"><span data-stu-id="140dd-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="140dd-109">Use los cmdlets de Windows PowerShell para configurar y administrar las contraseñas de las cuentas de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="140dd-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="140dd-110">El objeto de cuenta Kerberos es un objeto de equipo, pero usa el parámetro Cuentadeusuario para las operaciones de los cmdlets de Windows PowerShell a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="140dd-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="140dd-111">Tenga en cuenta que no se trata de un error, pero el comportamiento previsto para el cmdlet cuando se usa con la creación y el mantenimiento de la cuenta de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="140dd-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="140dd-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="140dd-112">In This Section</span></span>

  - [<span data-ttu-id="140dd-113">Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140dd-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="140dd-114">Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140dd-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

