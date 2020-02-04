---
title: 'Lync Server 2013: Vías de migración de servidor compatibles y escenarios de coexistencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Vías de migración de servidor compatibles y escenarios de coexistencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Lync Server 2013 admite la migración de cualquiera de las siguientes opciones:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

No se admite la migración desde un entorno en el que se ejecutan estas dos versiones anteriores. La migración de versiones anteriores, como Microsoft Office Communications Server 2007 o Live Communications Server 2005, no es compatible. Si su implementación anterior incluía una conversación grupal, debe migrarla por separado.

<div>

## <a name="migration-methods"></a>Métodos de migración

Se admite la migración de todas las topologías y roles de servidor de Lync Server. Puede migrar de una topología a una topología diferente, incluidos los servidores Standard Edition a Enterprise Edition.

Lync Server 2013 solo admite el siguiente método de migración:

  - <span></span>  
    **Migración en paralelo.** En la migración en paralelo, Lync Server 2013 se implementa junto con una implementación existente de Microsoft Lync Server 2010 o de Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones a los nuevos servidores y se mueven los usuarios a Lync Server 2013. Este método requiere plataformas de servidor adicionales, como hardware y software, durante la migración, y los nombres de los sistemas y los grupos de servidores son diferentes en la nueva configuración. Si es necesario revertir a la versión anterior, puede desplazar las operaciones a los servidores anteriores.

No se admite la migración entre bosques de los servicios de dominio de Active Directory.

La ruta de migración recomendada es un enfoque por fases. Para obtener más información sobre cómo migrar desde una versión anterior, incluyendo la fase de implementación de componentes adecuada, consulte los temas siguientes en la documentación de la migración:

  - [Migrar Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migrar de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Escenarios de coexistencia

Lync Server 2013 puede coexistir con componentes de una implementación de Lync Server 2010 o de una implementación de Office Communications Server 2007 R2. No se admite la implementación simultánea de Lync Server 2013 tanto con Lync Server 2010 como con Office Communications Server 2007 R2 (implementación simultánea de las tres versiones).

Durante una migración por fases en la que una implementación anterior de Lync Server 2010 o de Office Communications Server 2007 R2 coexiste de forma temporal con la nueva implementación de Lync Server 2013, la compatibilidad con el enrutamiento de versión mixta es limitada. Para obtener más información, consulte la documentación de la migración.

Debe usar equipos distintos y distintos que ejecuten Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para sus instancias de base de datos de Lync Server 2013. No puede usar la misma instancia de SQL Server para una agrupación de front-end de Lync Server 2013 que usa para una agrupación frontal de Lync Server 2010 o de Office Communications Server 2007 R2. Si define y configura Lync Server 2013 en el generador de topologías para una implementación que ya tiene implementado Lync Server 2010 o Office Communications Server 2007 R2, el generador de topología no le permitirá definir una instancia de Lync Server 2013 que ya esté en uso en la topología.

El generador de topología mostrará el siguiente mensaje para informarle de este problema: "el FQDN \[de SQL Server del\] servidor ya contiene una instancia de SQL que hospeda el rol ' almacén de usuario '."

<div>


> [!NOTE]  
> Si piensa implementar roles de servidor que son nuevos en su implementación de Lync Server 2013, primero debe actualizar la implementación existente según se describe en la documentación de la migración y en la documentación de implementación y, a continuación, implementar los nuevos roles de servidor tal como se describe en documentación de planeación y documentación de implementación. Si va a migrar una versión anterior de un chat grupal, hágalo en último lugar después de completar el proceso de migración de todos los demás componentes de Lync Server 2010 o de Office Communications Server 2007 R2.



</div>

Para los requisitos de coexistencia específicos y otros detalles sobre la coexistencia y la migración de los componentes de Lync Server 2010 o de Office Communications Server 2007 R2 y Lync Server 2013, consulte [migración de Lync server 2010 a Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) y [migración de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) en la documentación de la migración. Para obtener más información sobre compatibilidad con versiones mixtas para clientes, consulte [clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

