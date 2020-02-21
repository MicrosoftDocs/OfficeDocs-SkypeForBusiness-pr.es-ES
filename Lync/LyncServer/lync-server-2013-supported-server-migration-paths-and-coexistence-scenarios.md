---
title: 'Lync Server 2013: rutas de migración de servidor compatibles y escenarios de coexistencia'
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
ms.openlocfilehash: ab7d85bd25c6123b3befd3520289e40c63461970
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Rutas de migración de servidor compatibles y escenarios de coexistencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Lync Server 2013 admite la migración de cualquiera de las siguientes opciones:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

No se admite la migración de un entorno que ejecuta ambas de estas versiones anteriores. No se admite la migración desde versiones anteriores, como Microsoft Office Communications Server 2007 o Live Communications Server 2005. Si la implementación anterior incluía chat en grupo, debe migrarla por separado.

<div>

## <a name="migration-methods"></a>Métodos de migración

Se admite la migración de todas las topologías y roles de servidor de Lync Server. Puede migrar de una topología a otra, incluso desde un servidor Standard Edition a un servidor Enterprise Edition en una configuración consolidada.

Lync Server 2013 solo admite el siguiente método de migración:

  - <span></span>  
    **Migración en paralelo.** En la migración en paralelo, Lync Server 2013 se implementa junto con una implementación existente de Microsoft Lync Server 2010 o de Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones a los nuevos servidores y se mueven los usuarios a Lync Server 2013. Este método requiere plataformas de servidor adicionales, incluido el hardware y el software durante la migración, y los nombres de sistema y de grupo de servidores son distintos en la nueva configuración. Si es necesario revertir a la versión anterior, puede cambiar las operaciones de nuevo a los servidores anteriores.

No se admite la migración entre bosques de servicios de dominio de Active Directory.

La vía de migración recomendada se basa en fases. Para más información sobre la migración desde una versión anterior, incluida la fase correspondiente de la implementación de componentes, consulte los siguientes temas en la documentación sobre migración:

  - [Migración de Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migración de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migración desde Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Escenarios de coexistencia

Lync Server 2013 puede coexistir con componentes de una implementación de Lync Server 2010 o de una implementación de Office Communications Server 2007 R2. No se admite la implementación simultánea de Lync Server 2013 tanto con Lync Server 2010 como con Office Communications Server 2007 R2 (implementación simultánea de las tres versiones).

Durante una migración por fases en la que una implementación anterior de Lync Server 2010 o de Office Communications Server 2007 R2 coexiste temporalmente con la nueva implementación de Lync Server 2013, la compatibilidad con el enrutamiento de versiones mixtas es limitada. Para más información, consulte la documentación sobre migración.

Debe usar equipos independientes y distintos que ejecuten Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para las instancias de base de datos de Lync Server 2013. No se puede usar la misma instancia de SQL Server para un grupo de servidores front-end 2013 de Lync Server que se usa para un grupo de servidores front-end de Lync Server 2010 o de Office Communications Server 2007 R2. Si define y configura Lync Server 2013 en el generador de topologías para una implementación que ya tiene instalado Lync Server 2010 o Office Communications Server 2007 R2, el generador de topologías no le permitirá definir una instancia de un servidor de Lync Server 2013 que ya esté en uso en la topología.

El generador de topologías mostrará el siguiente mensaje para informarle de este problema: "el \[FQDN de SQL Server\] del servidor ya contiene una instancia de SQL que hospeda el rol ' almacén de usuario '."

<div>


> [!NOTE]  
> Si tiene previsto implementar roles de servidor que son nuevos en su implementación de Lync Server 2013, primero debe actualizar la implementación existente tal como se describe en la documentación de la migración y la documentación de implementación y, a continuación, implementar los nuevos roles de servidor tal y como se describe en documentación de planeación y documentación sobre la implementación. Si va a migrar una versión anterior de conversación en grupo, migre la última después de completar el proceso de migración de todos los demás componentes de Lync Server 2010 o de Office Communications Server 2007 R2.



</div>

Para los requisitos de coexistencia específicos y otros detalles sobre la coexistencia y la migración de los componentes de Lync Server 2010 o de Office Communications Server 2007 R2 y Lync Server 2013, consulte [migración de Lync server 2010 a Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) y [migración de Office Communications Server 2007 R2 a Lync Server](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 2013 en la documentación de la migración. Para obtener más información sobre la compatibilidad con versiones mixtas para clientes, consulte [clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

