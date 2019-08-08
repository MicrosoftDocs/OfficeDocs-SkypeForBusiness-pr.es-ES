---
title: Configuración de los clientes para la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configuración de los clientes para la migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-21_

Este tema contiene los pasos de implementación de cliente recomendados que debe realizar antes de migrar a Lync Server 2013. Estos cambios de configuración deberían hacerse en Office Communications Server 2007 R2. Es muy importante que realice estos pasos antes de migrar. Para obtener más información, consulte [planificación de clientes y dispositivos en Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Para configurar clientes antes de la migración

1.  Implemente las actualizaciones de servidor, cliente y dispositivo de Office Communications Server 2007 R2 más recientes (hotfixes):
    
      - [Aplicar las actualizaciones de Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descripción del paquete de actualización acumulativa para Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtener actualizaciones de software para dispositivos](http://go.microsoft.com/fwlink/?linkid=335809)

2.  En Office Communications Server 2007 R2, use el filtrado de versiones de cliente para permitir solo a los clientes de Office Communications Server 2007 R2 que tengan instaladas las actualizaciones más recientes para iniciar sesión.

3.  En Office Communications Server 2007 R2, use el filtrado de versiones de cliente para bloquear el inicio de sesión de clientes de Lync Server 2013. Siga los pasos descritos en configurar el filtrado de [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) versión de **cliente** en para agregar los filtros de versión que se muestran en la tabla siguiente. Para cada filtro de versión, asigne el **bloque**de acción.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Cliente</th>
    <th>Encabezado de agente de usuario</th>
    <th>Versión</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*. *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.**.. *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*. *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

