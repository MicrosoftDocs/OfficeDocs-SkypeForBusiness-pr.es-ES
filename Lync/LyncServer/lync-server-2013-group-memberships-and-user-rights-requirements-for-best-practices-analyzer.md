---
title: Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="02ff7-102">Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02ff7-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02ff7-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="02ff7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="02ff7-104">Para ejecutar correctamente el analizador de procedimientos recomendados, la cuenta de usuario que usa para iniciar sesión debe ser miembro del grupo administradores en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="02ff7-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="02ff7-105">Además, para analizar su entorno, la cuenta de usuario debe ser miembro de los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="02ff7-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="02ff7-106">**Administradores de dominio**   para enumerar la información de los servicios de dominio de Active Directory y para llamar a los proveedores de instrumental de administración de Windows (WMI) en controladores de dominio y servidores de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="02ff7-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="02ff7-107">\*\*\*\* Es necesario que los administradores de cada equipo interno de Lync Server 2013 y cada servidor perimetral llamen a los proveedores de instrumental de administración de Windows (WMI) y tengan acceso al registro.   </span><span class="sxs-lookup"><span data-stu-id="02ff7-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="02ff7-108">**RTCUniversalReadOnlyAdmins**   completos o delegados derechos administrativos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02ff7-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="02ff7-109">**Administrador con permiso de vista de Exchange**   completo o delegado administrador con permiso de vista de Exchange en la organización de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="02ff7-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="02ff7-110">Si su cuenta de usuario no tiene suficientes derechos de usuario, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="02ff7-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="02ff7-111">En un símbolo del sistema, use el comando **runas** para ejecutar la herramienta en una cuenta que tenga derechos de usuario suficientes.</span><span class="sxs-lookup"><span data-stu-id="02ff7-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="02ff7-112">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="02ff7-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="02ff7-113">En la página **conectar a Active Directory** , establezca las credenciales de las cuentas que planea usar para ejecutar Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="02ff7-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="02ff7-114">Haga clic en **Mostrar opciones de inicio de sesión avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="02ff7-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="02ff7-115">Puede especificar tres cuentas: una para conectarse a servicios de dominio de Active Directory, una para conectar con servidores perimetrales de Lync Server 2013 y otra para conectarse a los servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="02ff7-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="02ff7-116">Si no especifica ninguna de estas cuentas, se usa la cuenta de usuario que usó para iniciar sesión y ejecutar el analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="02ff7-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

