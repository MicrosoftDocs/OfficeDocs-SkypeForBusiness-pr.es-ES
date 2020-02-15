---
title: 'Lync Server 2013: instalar Lync para Windows Phone'
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
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="e7bb5-102">Instalar Lync para Windows Phone en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7bb5-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7bb5-103">_**Última modificación del tema:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="e7bb5-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="e7bb5-104">Lync 2013 para Windows Phone es una aplicación instalable por el usuario que está disponible en el catálogo de soluciones de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="e7bb5-105">Instalar Lync para Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="e7bb5-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="e7bb5-106">Puede indicar a los usuarios que instalen Lync 2013 para Windows Phone en sus dispositivos; para ello, debe dirigirlos al catálogo <http://go.microsoft.com/fwlink/p/?linkid=231901>de soluciones de Windows Phone en.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="e7bb5-107">Si usa un registro SRV de DNS para publicar los servicios web Exchange</span><span class="sxs-lookup"><span data-stu-id="e7bb5-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="e7bb5-108">Para habilitar la integración de Exchange en clientes de Lync, algunas organizaciones publican la dirección URL de los servicios web Exchange con un registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="e7bb5-109">El documento "Understanding and Troubleshooting Exchange Integration", disponible en el centro de [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)descarga de Microsoft en, describe los escenarios en los que puede ser necesario.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="e7bb5-110">Sin embargo, la integración de Exchange para los usuarios de Windows Phone no funcionará en este escenario, porque la plataforma de Windows Phone no admite las búsquedas SRV.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="e7bb5-111">Deberá indicar a los usuarios de Windows Phone que especifiquen la dirección URL de los servicios web Exchange en lugar de permitir que el teléfono detecte automáticamente el servidor.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="e7bb5-112">Indique a los usuarios que configuren la configuración de Lync en sus teléfonos Windows de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e7bb5-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="e7bb5-113">En Windows Phone, en la configuración de Lync, seleccione la pantalla de **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="e7bb5-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="e7bb5-114">Mueva **el servidor de detección automática** a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="e7bb5-115">Puntee en el campo vacío y escriba el nombre de dominio completo (FQDN) o la dirección URL de los servicios web Exchange.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7bb5-116">Puede especificar el nombre de dominio completo (FQDN) o la dirección URL completa del servidor de servicios web Exchange.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="e7bb5-117">Si especifica el FQDN, el protocolo (https://) y la ruta de acceso de los servicios Web de Exchange (/EWS/Exchange.asmx) se agregan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="e7bb5-118">Si la ruta de acceso de los servicios Web de Exchange es diferente, puede especificar la dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="e7bb5-119">Cierre la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="e7bb5-120">Comprobar la instalación del cliente móvil</span><span class="sxs-lookup"><span data-stu-id="e7bb5-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="e7bb5-121">Después de configurar el cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Lync 2013 funciona correctamente en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="e7bb5-122">**Buscar un contacto en el directorio corporativo**</span><span class="sxs-lookup"><span data-stu-id="e7bb5-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="e7bb5-123">En la lista de contactos, puntee **Buscar** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="e7bb5-124">Busque un contacto que existe solamente en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="e7bb5-125">Compruebe que el nombre de contacto aparece en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="e7bb5-126">**Probar la presencia y la mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="e7bb5-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="e7bb5-127">En la lista de contactos, puntee un contacto.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="e7bb5-128">En la tarjeta de contacto, puntee el icono **MI**.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="e7bb5-129">Compruebe que aparece una ventana de mensajería instantánea (mi) y que puede escribir y enviar un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="e7bb5-130">**Pobrar la conferencia saliente**</span><span class="sxs-lookup"><span data-stu-id="e7bb5-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="e7bb5-131">En Outlook, programe una reunión de Lync.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="e7bb5-132">En el dispositivo móvil, abra la invitación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="e7bb5-133">Haga clic en el vínculo de la reunión para unirse.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="e7bb5-134">Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="e7bb5-135">**Probar las notificaciones de inserción**</span><span class="sxs-lookup"><span data-stu-id="e7bb5-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="e7bb5-136">En el dispositivo móvil del usuario A, inicie sesión a Lync con la cuenta del usuario A.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="e7bb5-137">Abra otra aplicación en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="e7bb5-138">En un cliente distinto, inicie sesión a Lync con la cuenta del usuario B.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="e7bb5-139">Envíe un mensaje instantáneo del usuario B al usuario A:</span><span class="sxs-lookup"><span data-stu-id="e7bb5-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="e7bb5-140">Compruebe que aparece una notificación de mensaje instantáneo en el dispositivo móvil del usuario A.</span><span class="sxs-lookup"><span data-stu-id="e7bb5-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

