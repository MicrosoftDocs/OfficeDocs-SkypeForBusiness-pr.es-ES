---
title: 'Lync Server 2013: comprobar el acceso a través del proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518717"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="95eb3-102">Comprobar el acceso a través del proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95eb3-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95eb3-103">_**Última modificación del tema:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="95eb3-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="95eb3-p101">Realice el siguiente procedimiento para comprobar que los usuarios pueden obtener acceso a la información sobre el proxy inverso. Puede que tenga que completar la configuración del firewall y del Sistema de nombres de dominio (DNS) para que el acceso funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="95eb3-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="95eb3-106">Para comprobar que puede obtener acceso al sitio web a través de Internet</span><span class="sxs-lookup"><span data-stu-id="95eb3-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="95eb3-107">Abra un explorador web y escriba las direcciones URL en la barra **Dirección** que utilizan los clientes para obtener acceso a los archivos de Libreta de direcciones y al sitio web para conferencias, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="95eb3-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="95eb3-108">En servidor de libreta de direcciones, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/abs** donde externalwebfarmFQDN es el FQDN externo de los servicios web externos que hospedan los servicios de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="95eb3-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="95eb3-109">El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios de la carpeta del servidor de la Libreta de direcciones está configurada para la autenticación de Windows de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="95eb3-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="95eb3-110">Para conferencias, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/meet** donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda el contenido de la reunión.</span><span class="sxs-lookup"><span data-stu-id="95eb3-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="95eb3-111">Esta dirección URL debe mostrar la página de solución de problemas para conferencias.</span><span class="sxs-lookup"><span data-stu-id="95eb3-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="95eb3-112">Alternativamente, confirme que su dirección URL sencilla para conferencias funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="95eb3-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="95eb3-113">Una dirección URL sencilla de ejemplo para la combinación de conferencia puede ser https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95eb3-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="95eb3-114">Para la expansión del grupo de distribución, escriba una dirección URL similar a la siguiente: **https://externalwebfarmFQDN/GroupExpansion/service.svc** .</span><span class="sxs-lookup"><span data-stu-id="95eb3-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="95eb3-115">El usuario debe recibir un desafío HTTP, ya que la seguridad de directorios del servicio de expansión de grupos de distribución está configurada de forma predeterminada para la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="95eb3-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="95eb3-116">En el caso de acceso telefónico local, escriba la dirección URL sencilla similar a la siguiente, **https://externalwebfarmFQDN/dialin** donde externalwebfarmFQDN es el FQDN externo de la granja de servidores web que hospeda la página de acceso telefónico local para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="95eb3-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="95eb3-117">Se dirigirá al usuario a la página de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="95eb3-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="95eb3-118">Alternativamente, confirme que el acceso telefónico local de su dirección URL sencilla funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="95eb3-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="95eb3-119">Un ejemplo de dirección URL sencilla para el acceso telefónico es https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95eb3-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="95eb3-120">Para confirmar que la dirección URL de detección automática funciona, escriba https://lyncdiscover .</span><span class="sxs-lookup"><span data-stu-id="95eb3-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="95eb3-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="95eb3-121">externaldomainFQDN.</span></span> <span data-ttu-id="95eb3-122">El explorador debe pedirle que abra un archivo.</span><span class="sxs-lookup"><span data-stu-id="95eb3-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="95eb3-123">Seleccione Bloc de notas para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="95eb3-123">Select Notepad to open it.</span></span> <span data-ttu-id="95eb3-124">Una respuesta típica sería similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="95eb3-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

