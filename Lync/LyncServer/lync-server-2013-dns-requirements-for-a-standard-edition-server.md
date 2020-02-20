---
title: 'Lync Server 2013: requisitos de DNS para un servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cdd7a32519fe510819f82619c9086b22b820a52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f8526-102">Requisitos de DNS para un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8526-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8526-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f8526-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f8526-104">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f8526-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="f8526-105">Registros DNS para servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f8526-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="f8526-106">En la tabla siguiente se especifican los requisitos de DNS para la implementación de servidor de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f8526-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8526-107">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="f8526-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="f8526-108">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="f8526-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8526-109">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f8526-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="f8526-110">Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f8526-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8526-111">Inicio de sesión automático de clientes</span><span class="sxs-lookup"><span data-stu-id="f8526-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="f8526-112">Para cada dominio SIP compatible, un registro SRV para _sipinternaltls. _tcp. &lt;dominio&gt; a través del puerto 5061 que se asigna al FQDN del servidor Standard Edition que autentica y redirige las solicitudes de inicio de sesión de los clientes.</span><span class="sxs-lookup"><span data-stu-id="f8526-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="f8526-113">Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f8526-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8526-114">Detección del servicio web de actualización de dispositivos mediante dispositivos de comunicaciones unificadas (UC)</span><span class="sxs-lookup"><span data-stu-id="f8526-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="f8526-115">Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve en la dirección IP del servidor Standard Edition que hospeda el servicio Web de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f8526-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="f8526-116">En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero nunca ningún usuario se haya registrado en él, el registro A permite al dispositivo detectar el servidor que hospeda el Servicio web de actualización de dispositivos y obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f8526-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="f8526-117">En otro caso, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="f8526-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="f8526-118">Para obtener más información, vea <a href="lync-server-2013-device-update-web-service.md">servicio Web de actualización de dispositivos en Lync Server 2013</a> en la documentación referente a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="f8526-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8526-119">Un proxy inverso para admitir el tráfico HTTP</span><span class="sxs-lookup"><span data-stu-id="f8526-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="f8526-120">Un registro A externo que resuelva el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f8526-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="f8526-121">Los clientes y los dispositivos de comunicaciones unificadas usan este registro para conectarse al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f8526-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="f8526-122">Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="f8526-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8526-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8526-123">See Also</span></span>


[<span data-ttu-id="f8526-124">Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8526-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="f8526-125">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8526-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="f8526-126">Servicio Web de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8526-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

