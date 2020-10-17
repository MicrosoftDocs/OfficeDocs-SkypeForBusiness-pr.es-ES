---
title: Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados
description: Pertenencias a grupos y requisitos de derechos de usuario para analizador de procedimientos recomendados.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564196"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2fff9-103">Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fff9-103">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fff9-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2fff9-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2fff9-p101">Para ejecutar correctamente el Analizador de procedimientos recomendados, la cuenta de usuario que utilice para iniciar sesión debe ser miembro del grupo de administradores en el equipo local. Además, para examinar el entorno, la cuenta de usuario debe ser miembro de los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="2fff9-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="2fff9-107">**Administradores**     de dominio Enumerar información de servicios de dominio de Active Directory y llamar a los proveedores de instrumental de administración de Windows (WMI) en controladores de dominio y servidores de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="2fff9-107">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="2fff9-108">**Administradores**     Necesario en cada equipo interno de Lync Server 2013 y en cada servidor perimetral para llamar a los proveedores de instrumental de administración de Windows (WMI) y obtener acceso al registro.</span><span class="sxs-lookup"><span data-stu-id="2fff9-108">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="2fff9-109">**RTCUniversalReadOnlyAdmins**     Derechos administrativos de solo lectura de Lync Server 2013 de solo lectura o delegado.</span><span class="sxs-lookup"><span data-stu-id="2fff9-109">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="2fff9-110">Administrador con permiso de **vista de Exchange**     Administrador con permiso de vista de Exchange completo o delegado en la organización de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2fff9-110">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="2fff9-111">Si su cuenta de usuario no posee los derechos de usuario suficientes, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="2fff9-111">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="2fff9-112">En el símbolo del sistema, use el comando **runas** para ejecutar la herramienta con una cuenta que no posee derechos de usuario suficientes.</span><span class="sxs-lookup"><span data-stu-id="2fff9-112">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="2fff9-113">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2fff9-113">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="2fff9-114">En la página **Conectar con Active Directory**, escriba las credenciales de las cuentas que planea utilizar para ejecutar el Analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="2fff9-114">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="2fff9-115">Haga clic en **Mostrar opciones de conexión avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="2fff9-115">Click **Show advanced login options**.</span></span> <span data-ttu-id="2fff9-116">Puede escribir tres cuentas: una para conectarse a los servicios de dominio de Active Directory, una para conectarse a los servidores perimetrales de Lync Server 2013 y otra para conectarse a los servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2fff9-116">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="2fff9-117">Si no especifica ninguna de estas cuentas, se emplea la cuenta de usuario utilizada para iniciar sesión y ejecutar el Analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="2fff9-117">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

