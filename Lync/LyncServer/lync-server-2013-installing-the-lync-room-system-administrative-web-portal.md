---
title: 'Lync Server 2013: instalación del portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b475911da0e0508fecb53de533f75e9feb10155
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="640db-102">Instalación del portal web administrativo del sistema Lync Room en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640db-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640db-103">_**Última modificación del tema:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="640db-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="640db-104">Puede descargar el portal web administrativo del sistema Microsoft Lync Room del centro de descarga de Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044)en.</span><span class="sxs-lookup"><span data-stu-id="640db-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="640db-105">Para instalar el portal web administrativo del sistema Lync Room, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="640db-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="640db-106">Configure el puerto de aplicación de confianza mediante la ejecución del siguiente cmdlet en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="640db-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="640db-107">Para instalar el portal de la sala de reuniones, descargue **LyncRoomAdminPortal. exe** y, a continuación, ejecútelo como administrador.</span><span class="sxs-lookup"><span data-stu-id="640db-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="640db-108">Abra el archivo Web. config desde la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="640db-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="640db-109">% Program Files\\% Microsoft Lync Server\\2013 Web\\Components portal\\de\\la sala de reuniones controlador int</span><span class="sxs-lookup"><span data-stu-id="640db-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="640db-110">En el archivo Web. config, cambie PortalUserName por el nombre de usuario creado en el paso 2 en la sección "configuración de requisitos previos para Lync Room System admin portal" (el nombre recomendado en el paso es LRSApp):</span><span class="sxs-lookup"><span data-stu-id="640db-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="640db-111">Dado que el portal de administración LRS es una aplicación de confianza, no es necesario proporcionar la contraseña en la configuración del portal.</span><span class="sxs-lookup"><span data-stu-id="640db-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="640db-112">Si este usuario usa un registrador diferente que el registrador local, debe especificar el registrador para él agregando la siguiente línea en el archivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="640db-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="640db-113">Si el puerto usado es distinto de 5061, agregue la siguiente línea en el archivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="640db-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="640db-114">Comprobación de la instalación del portal web administrativo del sistema Lync Room</span><span class="sxs-lookup"><span data-stu-id="640db-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="640db-115">Para comprobar la instalación del portal web administrativo del sistema Lync Room, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="640db-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="640db-116">En un servidor front-end, vaya a la siguiente dirección URL:</span><span class="sxs-lookup"><span data-stu-id="640db-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="640db-117">https://\<fe-servidor\>/LRS</span><span class="sxs-lookup"><span data-stu-id="640db-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="640db-118">No debería ver ningún error, como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="640db-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="640db-119">![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión del portal de administración del sistema Lync Room")</span><span class="sxs-lookup"><span data-stu-id="640db-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="640db-120">Si no ve ningún error, intente acceder a la siguiente dirección URL desde cualquier otro equipo de la topología:</span><span class="sxs-lookup"><span data-stu-id="640db-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="640db-121">https://\<fe-servidor\>/LRS</span><span class="sxs-lookup"><span data-stu-id="640db-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="640db-122">Para obtener acceso a la página, deberá agregar los registros DNS como se describe en la sección "registros DNS necesarios para el inicio de sesión automático [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056)de cliente" en.</span><span class="sxs-lookup"><span data-stu-id="640db-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

