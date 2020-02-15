---
title: Implementación de una aplicación de sucursal con funciones de supervivencia o tareas de sitio central de servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4756da7db87504e8b8c700cea1abb171b594543e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas de sitio central de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Complete las tareas de esta sección en el sitio central. Si está implementando un servidor de sucursal con funciones de supervivencia, omita la primera tarea.

<div>


> [!IMPORTANT]
> Antes de realizar las tareas de esta sección, deberán cumplirse las siguientes condiciones: 
> <UL>
> <LI>
> <P>Lync Server debe configurarse en el sitio central.</P>
> <LI>
> <P>Debe agregarse un técnico de instalación de la sucursal al grupo RTCUniversalSBATechnicians.</P></LI></UL>Además, se recomienda que haga lo siguiente:
> <UL>
> <LI>
> <P>Implementar un servidor DHCP en cada una de las sucursales para permitir que los clientes obtengan direcciones IP.</P>
> <LI>
> <P>Como alternativa a la implementación de un servidor DHCP en cada sitio de sucursal, habilite el DHCP de Lync Server en la aplicación de sucursal con funciones de supervivencia o con el servidor de sucursal con funciones de supervivencia mediante el cmdlet <STRONG>set-CsRegistrarConfiguration – EnableDHCPServer $true de</STRONG>Lync Server Management Shell. Para obtener más información, consulte la sección "requisitos de hardware y software" de <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitios de sucursal para Lync Server 2013</A> en la documentación referente a la planeación.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

