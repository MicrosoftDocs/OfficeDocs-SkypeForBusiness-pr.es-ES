---
title: 'Lync Server 2013: Comprobar el diseño de la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Comprobar el diseño de la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-02_

El generador de topología verifica automáticamente la topología. Cualquier error de topología se identifica como un error de validación, indicado por el icono de error de validación junto al rol de servidor. También es importante comprobar que la topología representa correctamente la topología de la implementación.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Para comprobar la topología antes de la publicación

1.  Compruebe que todas las URL sencillas están configuradas correctamente.

2.  Confirme que el servidor basado en SQL Server está en línea y disponible para el equipo donde el Generador de topologías está instalado, incluidas todas las reglas de firewall necesarias.

3.  Confirme que el recurso compartido de archivos está disponible y que tiene los permisos definidos correctamente.

4.  Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.

5.  Compruebe que los servidores existen en los servicios de dominio de Active Directory. Esto ocurrirá automáticamente si ha unido los servidores al dominio.

Tras comprobar la topología y constatar que no hay errores de validación, estará listo para publicar la topología. Si hay errores de validación, debe corregirlos antes de poder publicar la topología. Para obtener más información sobre cómo publicar su topología, vea [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

