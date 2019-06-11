---
title: 'Lync Server 2013: requisitos de la aplicación de la tienda Windows de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="8c81e-102">Requisitos de la aplicación de la tienda Windows de Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c81e-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c81e-103">_**Última modificación del tema:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="8c81e-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="8c81e-104">Las organizaciones con una implementación local de Lync Server deben cumplir los siguientes requisitos para admitir la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="8c81e-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c81e-105">Para Lync Server 2010, ejecute la actualización acumulativa para Lync Server 2010: febrero de 2012 (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) o posterior en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="8c81e-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="8c81e-106">Para permitir que los usuarios se unan a reuniones, ejecute la actualización acumulativa para Lync Server 2010:2012 de octubre (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) en los servidores.</span><span class="sxs-lookup"><span data-stu-id="8c81e-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="8c81e-107">Habilite la detección automática, Lync Web App y los servicios de vale Web en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8c81e-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="8c81e-108">Habilitar la autenticación de certificados en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8c81e-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="8c81e-109">(El proceso de registro del usuario en el servidor front-end o en el grupo de servidores front-end se suele denominar registrar). Para obtener más información, consulte [crear opciones de configuración de registrar en Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8c81e-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="8c81e-110">Publique los registros de recursos de alias DNS (CNAME) del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="8c81e-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="8c81e-111">Ya no es necesario asegurarse de que el punto de distribución (CDP) de la lista de revocación de certificados (CRL) para los certificados emitidos para Lync Server apunta a un recurso HTTP en lugar de a un recurso LDAP.</span><span class="sxs-lookup"><span data-stu-id="8c81e-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="8c81e-112">Sin embargo, asegúrese de que los equipos cliente tienen instaladas las actualizaciones más recientes de Windows.</span><span class="sxs-lookup"><span data-stu-id="8c81e-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="8c81e-113">Configure servidores proxy HTTP en la empresa para permitir el tráfico HTTP relacionado con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c81e-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="8c81e-114">Agregue excepciones para la detección automática, Lync Web App y servicios webticket, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8c81e-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="8c81e-115">En los clientes, instale Windows 8,1 y la última versión de la aplicación de la tienda Windows de Lync para corregir un problema de inicio de sesión que generalmente se produce al usar varios dominios (por ejemplo, cuando el URI SIP está **Usera@domainZ.com** , pero el servidor perimetral es **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="8c81e-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="8c81e-116">Si su organización se suscribe a Lync Online u Office 365 y está usando su propio nombre de dominio, debe realizar algunos pasos adicionales para configurar la red para el descubrimiento automático de los servidores de Lync.</span><span class="sxs-lookup"><span data-stu-id="8c81e-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="8c81e-117">Los requisitos de configuración de red son los mismos para la aplicación de la tienda Windows de Lync y Lync en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="8c81e-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="8c81e-118">Siga las instrucciones "configurar su red" en el artículo de Office 365 wiki "configurar dispositivos móviles de Lync", disponible en [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="8c81e-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8c81e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c81e-119">See Also</span></span>


[<span data-ttu-id="8c81e-120">Implementación de la aplicación de la tienda Windows de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c81e-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

