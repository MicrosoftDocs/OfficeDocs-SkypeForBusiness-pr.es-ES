---
title: 'Lync Server 2013: ejecución de transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de9e16a7977a077dd40aaae30f39e11f65ca7c23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="3f9da-102">Ejecución de transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f9da-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f9da-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="3f9da-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="3f9da-104">Las transacciones sintéticas se suelen llevar a cabo de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="3f9da-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="3f9da-105">Puede usar los cmdlets CsHealthMonitoringConfiguration para configurar los usuarios de prueba para cada uno de sus grupos de registradores.</span><span class="sxs-lookup"><span data-stu-id="3f9da-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="3f9da-106">Estos usuarios de prueba son un par de usuarios que estaban preconfigurados para su uso con transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="3f9da-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="3f9da-107">(Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Con los usuarios de prueba configurados para un grupo de servidores, puede ejecutar una transacción sintética en ese grupo sin tener que especificar las identidades de (y proporcionar las credenciales para) las cuentas de usuario implicadas en la prueba.</span><span class="sxs-lookup"><span data-stu-id="3f9da-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="3f9da-108">O bien, puede ejecutar una transacción sintética con cuentas de usuario reales.</span><span class="sxs-lookup"><span data-stu-id="3f9da-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="3f9da-109">Por ejemplo, si dos usuarios no pueden intercambiar mensajes instantáneos, podría ejecutar una transacción sintética con estas dos cuentas de usuario (en lugar de un par de cuentas de prueba) y, a continuación, intentar diagnosticar y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="3f9da-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="3f9da-110">Si decide realizar una transacción sintética con cuentas de usuario reales, debe proporcionar los nombres de inicio de sesión y las contraseñas para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="3f9da-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3f9da-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f9da-111">See Also</span></span>


[<span data-ttu-id="3f9da-112">Configuración de usuarios y opciones de configuración de prueba de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f9da-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="3f9da-113">Instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f9da-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

