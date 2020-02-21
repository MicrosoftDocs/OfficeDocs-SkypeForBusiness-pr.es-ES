---
title: 'Lync Server 2013: comprobar el diseño de la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452bd18d19fa61a0479ee8040361290b0b99d702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Comprobar el diseño de la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-02_

El generador de topologías comprueba automáticamente la topología. Cualquier error de topología se identifica como un error de validación, que se indica mediante el icono de error de validación junto al rol de servidor. Es importante comprobar también que la topología representa correctamente la topología de su implementación.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Para comprobar la topología antes de su publicación

1.  Compruebe que todas las URL sencillas están configuradas correctamente.

2.  Confirme que el servidor basado en SQL Server está en línea y disponible para el equipo en el que está instalado el generador de topologías, incluidas las reglas de Firewall necesarias.

3.  Confirme que el recurso compartido de archivos esté disponible y que los permisos correctos estén definidos.

4.  Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.

5.  Compruebe que los servidores existen en los servicios de dominio de Active Directory. Esto se producirá automáticamente si ha incorporado los servidores al dominio.

Una vez que haya verificado la topología y comprobado que no existen errores de validación, estará listo para publicar la topología. Si hay errores de validación, deberá corregirlos para poder publicar la topología. Para obtener más información sobre la publicación de la topología, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

