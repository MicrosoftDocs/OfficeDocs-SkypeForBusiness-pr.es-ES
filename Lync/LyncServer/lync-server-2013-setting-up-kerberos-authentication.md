---
title: 'Lync Server 2013: configuración de la autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4f354d985ed9e0fc85909e232e06e7c34dd593
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509657"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="4e3a3-102">Configuración de la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e3a3-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4e3a3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4e3a3-104">Lync Server 2013 admite la autenticación NTLM y Kerberos para los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="4e3a3-105">Office Communications Server 2007 y Office Communications Server 2007 R2 usaron el valor predeterminado de RTCComponentService y RTCService como las cuentas de usuario para ejecutar los grupos de aplicaciones de servicios Web, lo que permite que se asigne un nombre principal de servicio (SPN) a las cuentas de usuario y actúe como entidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="4e3a3-106">Lync Server usa NetworkService para ejecutar servicios web y NetworkService no puede tener SPN asignados.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="4e3a3-107">Para solucionar el problema de no tener los objetos de Active Directory que contengan los SPN, el panel de control de Lync Server puede usar objetos de cuenta de equipo para este propósito.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="4e3a3-108">Los objetos de cuenta de equipo pueden contener las SPN y no están sujetos a la expiración de las contraseñas, lo que suponía un problema si se usaban cuentas de usuario en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="4e3a3-109">Use los cmdlets de Windows PowerShell para configurar los objetos de equipo para proporcionar la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4e3a3-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e3a3-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4e3a3-110">In This Section</span></span>

  - [<span data-ttu-id="4e3a3-111">Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="4e3a3-112">Crear una cuenta de autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="4e3a3-113">Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="4e3a3-114">Configuración de contraseñas de cuentas de autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="4e3a3-115">En Lync Server 2013 agregar autenticación Kerberos a otros sitios</span><span class="sxs-lookup"><span data-stu-id="4e3a3-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="4e3a3-116">En Lync Server 2013 quitar la autenticación Kerberos de un sitio</span><span class="sxs-lookup"><span data-stu-id="4e3a3-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="4e3a3-117">Probar e informar el estado y la asignación de la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e3a3-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

