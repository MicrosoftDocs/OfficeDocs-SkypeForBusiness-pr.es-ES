---
title: 'Lync Server 2013: información general sobre la aplicación de anuncio'
description: 'Lync Server 2013: información general sobre la aplicación de anuncio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e9834be5edc67777f258f8d041e134287a891a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577256"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="53c51-103">Información general sobre la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53c51-103">Overview of the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53c51-104">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="53c51-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="53c51-105">Cuando implemente la aplicación de anuncio, deberá configurar una tabla de números sin asignar que determine la acción que se realizará cuando alguien Marque un número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="53c51-105">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="53c51-106">La tabla de números sin asignar contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio administra cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="53c51-106">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="53c51-107">Cuando un autor de llamada marca un número de teléfono que es válido para su organización pero que no está asignado a nadie, Lync Server busca el número en la tabla de enrutamiento de números sin asignar, identifica el intervalo en el que se encuentra el número y enruta la llamada a la aplicación de anuncio especificada para ese intervalo.</span><span class="sxs-lookup"><span data-stu-id="53c51-107">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="53c51-108">La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si lo ha configurado para ello) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, por ejemplo, a un operador.</span><span class="sxs-lookup"><span data-stu-id="53c51-108">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="53c51-109">Puede usar los cmdlets del shell de administración de Lync Server para configurar varios mensajes de audio o para transferir destinos.</span><span class="sxs-lookup"><span data-stu-id="53c51-109">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="53c51-p102">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.</span><span class="sxs-lookup"><span data-stu-id="53c51-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="53c51-115">En Lync Server 2013, la aplicación de anuncio se instala automáticamente con la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="53c51-115">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="53c51-116">Las aplicaciones de anuncios y grupos de respuesta son componentes estándar de una implementación de Enterprise Voice: al implementar la telefonía IP empresarial, ambas aplicaciones se implementan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="53c51-116">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

