---
title: Requisitos previos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394f73c83f1981e4c4ee1528c1623f6424d2a85a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Requisitos previos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Existen diversos requisitos de hardware, software y configuración del sistema que necesitará para ejecutar la herramienta Lync Server 2013 stress and performance.

<div>

## <a name="client-hardware-requirements"></a>Requisitos de hardware del cliente

Para ejecutar la herramienta Lync Server 2013 de estrés y rendimiento en la implementación de Lync Server 2013, por cada 4.500 usuarios cuya carga desee simular, necesitará al menos un equipo dedicado que cumpla los siguientes requisitos mínimos de hardware:

  - Adaptador de red de 1 gigabit

  - 8 GB de RAM

  - 2 unidades de procesamiento central (CPU) de doble núcleo

</div>

<div>

## <a name="client-software-requirements"></a>Requisitos de software de cliente

Para ejecutar la herramienta Lync Server 2013 stress and performance en la implementación de Lync Server 2013, los sistemas operativos compatibles son:

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 (edición de 64 bits)

El equipo cliente debe cumplir con los siguientes requisitos de software:

  - Debe tener instalado el motor en tiempo de ejecución de [Microsoft .NET Framework 4,5](http://go.microsoft.com/fwlink/?linkid=143212) .

  - En Windows Server 2008/Windows Server 2012, la característica de experiencia de escritorio debe estar habilitada.

  - Debe tener instalado el [paquete redistribuible de Microsoft Visual C++ 2012](http://go.microsoft.com/fwlink/?linkid=143216) (x64).

  - Una implementación de Lync Server 2013 totalmente configurada.

<div>


> [!IMPORTANT]  
> Las bibliotecas de la API administrada de comunicaciones unificadas de Microsoft (UCMA) 4,0 se incluyen en el paquete de instalación, de modo que UCMA no es necesario y no debe instalarse en los equipos cliente.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuración

Los equipos que ejecutarán la herramienta de estrés y rendimiento de Lync Server 2013 deben estar configurados de acuerdo con los siguientes requisitos:

1.  Debe haber iniciado sesión como miembro del grupo de administradores locales o de dominio.

2.  La herramienta de estrés y rendimiento de Lync Server 2013 (LyncPerfTool. exe) no se puede ejecutar en un equipo que también ejecute componentes de Lync Server 2013.

3.  Debe ejecutar la herramienta de creación de usuarios de Lync Server 2013 (UserProvisioningTool. exe) en el servidor front-end o en el servidor Standard Edition donde residirán las cuentas de usuario. Cuando la herramienta se ejecuta varias veces, cada usuario habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.

4.  El tamaño del archivo de paginación debe ser administrado por el sistema o debe ser al menos 1,5 veces la cantidad de RAM del sistema.

</div>

</div>

<span> </span>

</div>

</div>

</div>

