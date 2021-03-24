---
title: Estacionamiento de llamadas Crear nuevo o Editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se desaten.
ms.openlocfilehash: 1a85bacf1ebb13afd7302f8e1cf50c112c3139e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095684"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="6295b-103">Estacionamiento de llamadas: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="6295b-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="6295b-104">Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se desaten.</span><span class="sxs-lookup"><span data-stu-id="6295b-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6295b-105">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6295b-105">UI Reference</span></span>

<span data-ttu-id="6295b-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="6295b-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6295b-107">**Nombre** Escriba un nombre descriptivo que identifique el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="6295b-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="6295b-108">Una vez que guarde el intervalo numérico, el nombre no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="6295b-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="6295b-109">**Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="6295b-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="6295b-110">En el segundo campo, escriba el número de finalización del intervalo numérico.</span><span class="sxs-lookup"><span data-stu-id="6295b-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="6295b-111">El número inicial del intervalo debe ser menor o igual al número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6295b-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="6295b-112">El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6295b-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="6295b-p103">El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.</span><span class="sxs-lookup"><span data-stu-id="6295b-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="6295b-115">Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="6295b-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="6295b-116">Valores válidos: debe coincidir con la cadena de expresión regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="6295b-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="6295b-117">Esto significa que el valor debe ser una cadena que comienza con el carácter o # o un número \* del 1 al 9 (el primer carácter no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="6295b-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="6295b-118">Si el primer carácter es o #, el siguiente carácter debe ser un número del 1 al \* 9 (no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="6295b-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="6295b-119">Los caracteres posteriores pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", " \* 92000", " \* 95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="6295b-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="6295b-120">Si el primer carácter no es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de \* 0 a 9 (por ejemplo: 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="6295b-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="6295b-p105">No debe tener más de 50.000 números por grupo de servidores. Cada intervalo numérico normalmente está formado por 100 números o menos, pero puede ser mucho mayor siempre que tenga menos de 10.000 números. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".</span><span class="sxs-lookup"><span data-stu-id="6295b-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="6295b-124">**FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6295b-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="6295b-125">Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo numérico se enrutarán a este servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6295b-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="6295b-126">Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, vea [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="6295b-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="6295b-127">Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span><span class="sxs-lookup"><span data-stu-id="6295b-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>