---
title: 'Lync Server 2013: problemas con la prueba del entorno'
description: 'Lync Server 2013: problemas con la prueba del entorno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574976"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="4bfc3-103">Problemas con la prueba de entorno en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bfc3-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bfc3-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4bfc3-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4bfc3-105">El analizador de procedimientos recomendados proporciona una manera de comprobar que el entorno de Lync Server 2013 es una configuración admitida.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="4bfc3-106">Durante la comprobación de los servicios de dominio de Active Directory, el Analizador de procedimientos recomendados realiza las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="4bfc3-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="4bfc3-107">Verifica la preparación del bosque y el esquema de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="4bfc3-108">Identifica el número de sitios y dominios de Servicios de dominio de Active Directory en la implementación.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="4bfc3-109">Comprueba el bosque y los niveles de dominio.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="4bfc3-110">Comprueba la versión del controlador del dominio.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="4bfc3-111">Identifica el contexto de denominación del dominio, la configuración y el esquema.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="4bfc3-112">Identifica el número de usuarios habilitados.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="4bfc3-113">Comprueba el lugar de almacenamiento de la configuración de los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="4bfc3-114">Busca los puntos de conexión de servicio (SCP) para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="4bfc3-115">Identifica la versión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="4bfc3-116">Resolución de problemas del entorno</span><span class="sxs-lookup"><span data-stu-id="4bfc3-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="4bfc3-p102">Si durante la prueba del entorno se detectan problemas, probablemente se deban a problemas de configuración de Active Directory o el nivel de software que se ejecuta en determinados servidores. Por ejemplo, si el Analizador de procedimientos recomendados detecta que algún controlador de dominio del entorno ejecuta Windows Server 2000, emitirá una advertencia y será necesario actualizar esos controladores de dominio a una versión compatible de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

