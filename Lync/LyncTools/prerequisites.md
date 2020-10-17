---
title: Requisitos previos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f81299b2efdde3be262439528409d89abf369f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509137"
---
# <a name="prerequisites"></a>Requisitos previos

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Hay varios requisitos de configuración de hardware, software y sistema que necesitará para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Requisitos de hardware del cliente

Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 en su implementación de Lync Server 2013, para cada 4.500 usuarios cuya carga desee simular, necesitará al menos un equipo dedicado que cumpla los siguientes requisitos mínimos de hardware:

  - adaptador de red de 1 Gigabit

  - 8 GB de RAM

  - 2 unidades de procesamiento central (CPU) de doble núcleo

</div>

<div>

## <a name="client-software-requirements"></a>Requisitos de software del cliente

Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 en su implementación de Lync Server 2013, los sistemas operativos compatibles son los siguientes:

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 (edición de 64 bits)

El equipo cliente debe cumplir con los siguientes requisitos de software:

  - Debe tener instalado el motor en tiempo de ejecución de [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) .

  - En Windows Server 2008/Windows Server 2012, la característica experiencia de escritorio debe estar habilitada.

  - Debe tener instalado el [paquete redistribuible de Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64).

  - Una implementación de Lync Server 2013 totalmente configurada.

<div>


> [!IMPORTANT]  
> Las bibliotecas de API administrada de comunicaciones unificadas de Microsoft (UCMA) 4,0 se incluyen en el paquete de instalación, por lo que el UCMA no es necesario y no debe instalarse en los equipos cliente.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuración

Los equipos que ejecutarán la herramienta de esfuerzo y rendimiento de Lync Server 2013 deben configurarse de acuerdo con los siguientes requisitos:

1.  Debe iniciar sesión como miembro del grupo de administradores local o de dominio.

2.  La herramienta de esfuerzo y rendimiento de Lync Server 2013 (LyncPerfTool.exe) no se puede ejecutar en un equipo que también ejecute componentes de Lync Server 2013.

3.  Debe ejecutar la herramienta de creación de usuarios de Lync Server 2013 (UserProvisioningTool.exe) en el servidor front-end o en el servidor Standard Edition donde residirán las cuentas de usuario. Cuando la herramienta se ejecuta varias veces, cada usuario que esté habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.

4.  El tamaño del archivo de paginación debe ser administrado por el sistema o debe ser al menos 1,5 veces la cantidad de RAM del sistema.

</div>

</div>

<span> </span>

</div>

</div>

</div>

