---
title: 'Lync Server 2013: requisitos de DNS para servidores Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903243e846fee2a0b874a50fb529b533c1658fc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="11233-102">Requisitos de DNS para servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11233-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11233-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="11233-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="11233-104">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="11233-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="11233-105">Registros DNS para servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="11233-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="11233-106">En la tabla siguiente se especifican los requisitos de DNS para la implementación de servidor de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="11233-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="11233-107">Requisitos de DNS para un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="11233-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11233-108">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="11233-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="11233-109">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="11233-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11233-110">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="11233-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="11233-111">Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="11233-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11233-112">Inicio de sesión automático de clientes</span><span class="sxs-lookup"><span data-stu-id="11233-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="11233-113">Para cada dominio SIP compatible, un registro SRV para _sipinternaltls. _tcp. &lt;dominio&gt; a través del puerto 5061 que se asigna al FQDN del servidor Standard Edition que autentica y redirige las solicitudes de inicio de sesión de los clientes.</span><span class="sxs-lookup"><span data-stu-id="11233-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="11233-114">Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11233-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11233-115">Detección del servicio web de actualización de dispositivos mediante dispositivos de comunicaciones unificadas (UC)</span><span class="sxs-lookup"><span data-stu-id="11233-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="11233-116">Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve en la dirección IP del servidor Standard Edition que hospeda el servicio Web de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="11233-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="11233-117">En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero nunca ningún usuario se haya registrado en él, el registro A permite al dispositivo detectar el servidor que hospeda el Servicio web de actualización de dispositivos y obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="11233-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="11233-118">En caso contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="11233-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11233-119">Un proxy inverso que admita tráfico HTTP</span><span class="sxs-lookup"><span data-stu-id="11233-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="11233-120">Un registro A externo que resuelva el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="11233-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="11233-121">Los clientes y los dispositivos de comunicaciones unificadas usan este registro para conectarse al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="11233-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="11233-122">Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="11233-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

