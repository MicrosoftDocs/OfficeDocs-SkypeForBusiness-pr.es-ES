---
title: 'Lync Server 2013: Comprobar el acceso a través del proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="60170-102">Comprobar el acceso a través del proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60170-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60170-103">_**Última modificación del tema:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="60170-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="60170-104">Use el procedimiento siguiente para comprobar que los usuarios pueden obtener acceso a la información del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="60170-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="60170-105">Es posible que tenga que completar la configuración del firewall y del sistema de nombres de dominio (DNS) antes de que Access funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="60170-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="60170-106">Para comprobar que puede obtener acceso al sitio web a través de Internet</span><span class="sxs-lookup"><span data-stu-id="60170-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="60170-107">Abra un explorador Web, escriba las direcciones URL en la barra de **direcciones** que los clientes usan para acceder a los archivos de la libreta de direcciones y el sitio web para las conferencias de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="60170-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="60170-108">En servidor de la libreta de direcciones, escriba una dirección URL similar **https://externalwebfarmFQDN/abs** a la siguiente: donde externalwebfarmFQDN es el FQDN externo de los servicios web externos que hospedan los servicios de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="60170-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="60170-109">El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la libreta de direcciones está configurada de forma predeterminada en la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="60170-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="60170-110">Para conferencias, escriba una dirección URL similar a la siguiente **https://externalwebfarmFQDN/meet** : donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda el contenido de la reunión.</span><span class="sxs-lookup"><span data-stu-id="60170-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="60170-111">Esta dirección URL debe mostrar la página de solución de problemas para conferencias.</span><span class="sxs-lookup"><span data-stu-id="60170-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="60170-112">También puede confirmar que su dirección URL simple para conferencias funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="60170-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="60170-113">Una dirección URL sencilla de ejemplo para la combinación de conferencia puede serhttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60170-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="60170-114">En expansión de grupos de distribución, escriba una dirección URL similar a **https://externalwebfarmFQDN/GroupExpansion/service.svc**la siguiente:.</span><span class="sxs-lookup"><span data-stu-id="60170-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="60170-115">El usuario debe recibir un desafío HTTP, porque la seguridad de directorio en el servicio de expansión del grupo de distribución está configurada de forma predeterminada en la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="60170-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="60170-116">Para el acceso telefónico, escriba la dirección URL sencilla similar a la **https://externalwebfarmFQDN/dialin** siguiente, donde externalwebfarmFQDN es el nombre completo externo del conjunto de servidores web que hospeda la página de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="60170-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="60170-117">El usuario debe dirigirse a la página de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="60170-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="60170-118">También puede confirmar que su dirección de acceso telefónico simple funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="60170-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="60170-119">Un ejemplo de una dirección URL simple para el acceso telefónico eshttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60170-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="60170-120">Para confirmar que la dirección URL de detección automática funciona, https://lyncdiscoverescriba.</span><span class="sxs-lookup"><span data-stu-id="60170-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="60170-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="60170-121">externaldomainFQDN.</span></span> <span data-ttu-id="60170-122">El explorador debe pedirle que abra un archivo.</span><span class="sxs-lookup"><span data-stu-id="60170-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="60170-123">Seleccione Bloc de notas para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="60170-123">Select Notepad to open it.</span></span> <span data-ttu-id="60170-124">Una respuesta típica sería similar a:</span><span class="sxs-lookup"><span data-stu-id="60170-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

