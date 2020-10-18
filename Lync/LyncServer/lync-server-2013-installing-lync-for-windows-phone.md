---
title: 'Lync Server 2013: instalar Lync para Windows Phone'
description: 'Lync Server 2013: instalar Lync para Windows Phone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573986"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="92ec7-103">Instalar Lync para Windows Phone en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92ec7-103">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92ec7-104">_**Última modificación del tema:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="92ec7-104">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="92ec7-105">Lync 2013 para Windows Phone es una aplicación instalable por el usuario que está disponible en el catálogo de soluciones de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="92ec7-105">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="92ec7-106">Instalar Lync para Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="92ec7-106">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="92ec7-107">Puede indicar a los usuarios que instalen Lync 2013 para Windows Phone en sus dispositivos; para ello, debe dirigirlos al catálogo de soluciones de Windows Phone en <https://go.microsoft.com/fwlink/p/?linkid=231901> .</span><span class="sxs-lookup"><span data-stu-id="92ec7-107">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="92ec7-108">Si usa un registro SRV de DNS para publicar los servicios web Exchange</span><span class="sxs-lookup"><span data-stu-id="92ec7-108">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="92ec7-109">Para habilitar la integración de Exchange en clientes de Lync, algunas organizaciones publican la dirección URL de los servicios web Exchange con un registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="92ec7-109">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="92ec7-110">El documento "Understanding and Troubleshooting Exchange Integration", disponible en el centro de descarga de Microsoft en [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) , describe los escenarios en los que puede ser necesario.</span><span class="sxs-lookup"><span data-stu-id="92ec7-110">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="92ec7-111">Sin embargo, la integración de Exchange para los usuarios de Windows Phone no funcionará en este escenario, porque la plataforma de Windows Phone no admite las búsquedas SRV.</span><span class="sxs-lookup"><span data-stu-id="92ec7-111">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="92ec7-112">Deberá indicar a los usuarios de Windows Phone que especifiquen la dirección URL de los servicios web Exchange en lugar de permitir que el teléfono detecte automáticamente el servidor.</span><span class="sxs-lookup"><span data-stu-id="92ec7-112">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="92ec7-113">Indique a los usuarios que configuren la configuración de Lync en sus teléfonos Windows de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="92ec7-113">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="92ec7-114">En Windows Phone, en la configuración de Lync, seleccione la pantalla de **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="92ec7-114">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="92ec7-115">Mueva **el servidor de detección automática** a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="92ec7-115">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="92ec7-116">Puntee en el campo vacío y escriba el nombre de dominio completo (FQDN) o la dirección URL de los servicios web Exchange.</span><span class="sxs-lookup"><span data-stu-id="92ec7-116">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92ec7-117">Puede especificar el nombre de dominio completo (FQDN) o la dirección URL completa del servidor de servicios web Exchange.</span><span class="sxs-lookup"><span data-stu-id="92ec7-117">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="92ec7-118">Si especifica el FQDN, el protocolo (https://) y la ruta de acceso de los servicios Web de Exchange (/EWS/Exchange.asmx) se agregan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="92ec7-118">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="92ec7-119">Si la ruta de acceso de los servicios Web de Exchange es diferente, puede especificar la dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="92ec7-119">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="92ec7-120">Cierre la pantalla.</span><span class="sxs-lookup"><span data-stu-id="92ec7-120">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="92ec7-121">Comprobar la instalación del cliente móvil</span><span class="sxs-lookup"><span data-stu-id="92ec7-121">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="92ec7-122">Después de configurar el cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Lync 2013 funciona correctamente en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="92ec7-122">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="92ec7-123">**Buscar un contacto en el directorio corporativo**</span><span class="sxs-lookup"><span data-stu-id="92ec7-123">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="92ec7-124">En la lista de contactos, puntee **Buscar** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="92ec7-124">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="92ec7-125">Busque un contacto que existe solamente en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="92ec7-125">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="92ec7-126">Compruebe que el nombre de contacto aparece en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="92ec7-126">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="92ec7-127">**Probar la presencia y la mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="92ec7-127">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="92ec7-128">En la lista de contactos, puntee un contacto.</span><span class="sxs-lookup"><span data-stu-id="92ec7-128">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="92ec7-129">En la tarjeta de contacto, puntee el icono **MI**.</span><span class="sxs-lookup"><span data-stu-id="92ec7-129">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="92ec7-130">Compruebe que aparece una ventana de mensajería instantánea (mi) y que puede escribir y enviar un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="92ec7-130">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="92ec7-131">**Pobrar la conferencia saliente**</span><span class="sxs-lookup"><span data-stu-id="92ec7-131">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="92ec7-132">En Outlook, programe una reunión de Lync.</span><span class="sxs-lookup"><span data-stu-id="92ec7-132">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="92ec7-133">En el dispositivo móvil, abra la invitación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="92ec7-133">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="92ec7-134">Haga clic en el vínculo de la reunión para unirse.</span><span class="sxs-lookup"><span data-stu-id="92ec7-134">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="92ec7-135">Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.</span><span class="sxs-lookup"><span data-stu-id="92ec7-135">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="92ec7-136">**Probar las notificaciones de inserción**</span><span class="sxs-lookup"><span data-stu-id="92ec7-136">**Test push notifications**</span></span>

1.  <span data-ttu-id="92ec7-137">En el dispositivo móvil del usuario A, inicie sesión a Lync con la cuenta del usuario A.</span><span class="sxs-lookup"><span data-stu-id="92ec7-137">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="92ec7-138">Abra otra aplicación en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="92ec7-138">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="92ec7-139">En un cliente distinto, inicie sesión a Lync con la cuenta del usuario B.</span><span class="sxs-lookup"><span data-stu-id="92ec7-139">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="92ec7-140">Envíe un mensaje instantáneo del usuario B al usuario A:</span><span class="sxs-lookup"><span data-stu-id="92ec7-140">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="92ec7-141">Compruebe que aparece una notificación de mensaje instantáneo en el dispositivo móvil del usuario A.</span><span class="sxs-lookup"><span data-stu-id="92ec7-141">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

