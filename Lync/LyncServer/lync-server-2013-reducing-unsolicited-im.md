---
title: 'Lync Server 2013: reducir la mensajería instantánea no solicitada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="ab67b-102">Reducir la mensajería instantánea no solicitada para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab67b-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab67b-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="ab67b-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="ab67b-104">La aplicación de filtro inteligente de mensajería instantánea ayuda a proteger la implementación de Microsoft Lync Server 2013 frente a los virus más comunes con una degradación mínima para la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="ab67b-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="ab67b-105">El filtro inteligente de mensaje instantáneo ofrece las siguientes prestaciones:</span><span class="sxs-lookup"><span data-stu-id="ab67b-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="ab67b-106">Mejor filtrado de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="ab67b-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="ab67b-107">Mejor filtrado de transferencias de archivos</span><span class="sxs-lookup"><span data-stu-id="ab67b-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="ab67b-p102">Use el filtro inteligente de mensaje instantáneo para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo. Los filtros se configuran especificando los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos y archivos con extensiones específicas.</span><span class="sxs-lookup"><span data-stu-id="ab67b-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="ab67b-110">Antes de implementar la aplicación de filtro inteligente de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado cuando los mensajes se enrutan desde un servidor de 2013 de Lync Server a otro.</span><span class="sxs-lookup"><span data-stu-id="ab67b-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="ab67b-111">Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una o en varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="ab67b-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="ab67b-112">Esta coherencia se aplica a la forma en que los avisos y advertencias personalizados se insertan en los mensajes y se envían a través de los servidores.</span><span class="sxs-lookup"><span data-stu-id="ab67b-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="ab67b-p104">La opción de filtrado recomendada es permitir los mensajes instantáneos con hipervínculos, pero obligar al filtro inteligente de mensaje instantáneo a que deshabilite el vínculo anteponiendo un carácter de subrayado. Si elige esta opción, tendrá además la oportunidad de redactar un aviso que va a aparecer al principio de cada mensaje instantáneo que contenga un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="ab67b-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="ab67b-p105">La segunda opción de filtrado consiste en permitir los mensajes instantáneos con hipervínculos no modificados. Si elige esta opción, tendrá además la oportunidad de redactar una advertencia que se va a insertar en cada mensaje (opción recomendada).</span><span class="sxs-lookup"><span data-stu-id="ab67b-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="ab67b-p106">La tercera opción consiste en bloquear todos los mensajes instantáneos que contengan un hipervínculo. Si elige esta opción, el servidor envía una advertencia al usuario. Debe escribir esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="ab67b-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

