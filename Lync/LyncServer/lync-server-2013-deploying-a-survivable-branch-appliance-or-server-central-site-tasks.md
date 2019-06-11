---
title: Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Complete las tareas de esta sección en el sitio central. Si va a implementar un servidor de sucursal con la supervivencia, omita la primera tarea.

<div>


> [!IMPORTANT]
> Antes de realizar las tareas de esta sección, deben cumplirse las condiciones siguientes: 
> <UL>
> <LI>
> <P>Lync Server debe estar configurado en el sitio central.</P>
> <LI>
> <P>Un técnico de instalación del sitio de la sucursal debe agregarse al grupo RTCUniversalSBATechnicians.</P></LI></UL>Además, le recomendamos que haga lo siguiente:
> <UL>
> <LI>
> <P>Implemente un servidor DHCP en cada sitio de sucursal para que los clientes puedan obtener direcciones IP.</P>
> <LI>
> <P>Como alternativa a la implementación de un servidor DHCP en cada sitio de sucursal, habilite el servicio DHCP de Lync Server en el equipo de la sucursal o el servidor de sucursal con la configuración de Lync Server Management, cmdlet <STRONG>-CsRegistrarConfiguration – EnableDHCPServer $true </STRONG>. Para obtener más información, consulte la sección "requisitos de hardware y software" de <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitios de sucursales para Lync Server 2013</A> en la documentación de planeación.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

