---
title: 'Lync Server 2013: configurar números de teléfono sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd933ac87addf4a2094009e9f437c29437d882a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520237"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="f96ef-102">Configurar números de teléfono sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96ef-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f96ef-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f96ef-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f96ef-104">Lync Server le permite configurar lo que sucede con las llamadas entrantes a números de teléfono que son válidos para su organización, pero que no están asignados a un usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="f96ef-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="f96ef-105">Para definir cómo se tratan dichas llamadas, deberá configurar una tabla de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="f96ef-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="f96ef-106">Puede usar la tabla para redirigir las llamadas a una aplicación de anuncio o a un servidor de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f96ef-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="f96ef-p102">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien, con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="f96ef-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f96ef-113">Antes de configurar la tabla de números sin asignar, debe tener ya uno o más anuncios definidos o un operador automático de mensajería unificada de Exchange configurado.</span><span class="sxs-lookup"><span data-stu-id="f96ef-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="f96ef-114">Para obtener más información sobre cómo crear anuncios, consulte <A href="lync-server-2013-create-an-announcement.md">crear un anuncio en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f96ef-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="f96ef-115">Para ver si ha configurado la configuración de mensajería unificada de Exchange, ejecute el cmdlet <STRONG>Get-CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f96ef-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="f96ef-116">Para obtener información detallada, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="f96ef-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f96ef-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f96ef-117">In This Section</span></span>

  - [<span data-ttu-id="f96ef-118">Crear o modificar un intervalo numérico sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96ef-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="f96ef-119">Eliminar un intervalo numérico sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96ef-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

