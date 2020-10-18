---
title: 'Lync Server 2013: configuración de contraseñas de cuentas de autenticación Kerberos'
description: 'Lync Server 2013: configuración de contraseñas de cuentas de autenticación Kerberos.'
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
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577226"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="84b4a-103">Configuración de contraseñas de cuentas de autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b4a-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84b4a-104">_**Última modificación del tema:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="84b4a-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="84b4a-105">Una vez creado el objeto de equipo para la cuenta de autenticación Kerberos, puede configurar la contraseña para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="84b4a-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="84b4a-106">Ejecute el cmdlet de Windows PowerShell para establecer la contraseña de la cuenta Kerberos en un servidor.</span><span class="sxs-lookup"><span data-stu-id="84b4a-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="84b4a-107">Puede definir la contraseña en el objeto que ha creado para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84b4a-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="84b4a-108">La contraseña puede tener un valor conocido, pero de forma predeterminada es una contraseña aleatoria.</span><span class="sxs-lookup"><span data-stu-id="84b4a-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="84b4a-109">La contraseña está disponible para todas las fuentes de autenticación Kerberos que usan la cuenta.</span><span class="sxs-lookup"><span data-stu-id="84b4a-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="84b4a-110">Use los cmdlets de Windows PowerShell para configurar y administrar las contraseñas de las cuentas Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84b4a-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84b4a-111">El objeto de cuenta Kerberos es un objeto de equipo, pero usa el parámetro Cuentadeusuario para las operaciones en los cmdlets de Windows PowerShell a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="84b4a-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="84b4a-112">Tenga en cuenta que esto no es un error, sino el comportamiento previsto del cmdlet cuando se usa con la creación y el mantenimiento de la cuenta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84b4a-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84b4a-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="84b4a-113">In This Section</span></span>

  - [<span data-ttu-id="84b4a-114">Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b4a-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="84b4a-115">Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b4a-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

