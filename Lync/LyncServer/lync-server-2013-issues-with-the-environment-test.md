---
title: 'Lync Server 2013: problemas con la prueba del entorno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="f391d-102">Problemas con la prueba de entorno en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f391d-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f391d-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f391d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f391d-104">El analizador de procedimientos recomendados proporciona una forma de comprobar que el entorno de Lync Server 2013 es una configuración admitida.</span><span class="sxs-lookup"><span data-stu-id="f391d-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="f391d-105">Como parte de la comprobación de los servicios de dominio de Active Directory, el analizador de procedimientos recomendados hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f391d-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="f391d-106">Comprueba la preparación del bosque y el esquema de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f391d-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="f391d-107">Identifica el número de dominios y sitios de servicios de dominio de Active Directory en la implementación.</span><span class="sxs-lookup"><span data-stu-id="f391d-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="f391d-108">Comprueba los niveles de bosque y dominio.</span><span class="sxs-lookup"><span data-stu-id="f391d-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="f391d-109">Comprueba la versión del controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="f391d-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="f391d-110">Identifica el contexto de nomenclatura del dominio, la configuración y el esquema.</span><span class="sxs-lookup"><span data-stu-id="f391d-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="f391d-111">Identifica el número de usuarios habilitados.</span><span class="sxs-lookup"><span data-stu-id="f391d-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="f391d-112">Comprueba dónde se almacena la configuración de los servicios de dominio de Active Directory global.</span><span class="sxs-lookup"><span data-stu-id="f391d-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="f391d-113">Comprueba los puntos de conexión de servicio (SCP) de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f391d-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="f391d-114">Identifica la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f391d-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="f391d-115">Resolución de problemas con el entorno</span><span class="sxs-lookup"><span data-stu-id="f391d-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="f391d-116">Si la prueba de entorno encontró problemas con su entorno, probablemente se deba a problemas con la configuración de Active Directory o el nivel de software que se ejecuta en servidores específicos.</span><span class="sxs-lookup"><span data-stu-id="f391d-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="f391d-117">Por ejemplo, si el analizador de procedimientos recomendados identifica cualquier controlador de dominio de su entorno que ejecuta Windows Server 2000, emitirá una advertencia y tendrá que actualizar esos controladores de dominio a una versión compatible de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f391d-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

