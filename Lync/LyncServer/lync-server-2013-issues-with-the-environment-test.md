---
title: 'Lync Server 2013: problemas con la prueba del entorno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemas con la prueba de entorno en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El analizador de procedimientos recomendados proporciona una forma de comprobar que el entorno de Lync Server 2013 es una configuración admitida. Como parte de la comprobación de los servicios de dominio de Active Directory, el analizador de procedimientos recomendados hace lo siguiente:

  - Comprueba la preparación del bosque y el esquema de los servicios de dominio de Active Directory.

  - Identifica el número de dominios y sitios de servicios de dominio de Active Directory en la implementación.

  - Comprueba los niveles de bosque y dominio.

  - Comprueba la versión del controlador de dominio.

  - Identifica el contexto de nomenclatura del dominio, la configuración y el esquema.

  - Identifica el número de usuarios habilitados.

  - Comprueba dónde se almacena la configuración de los servicios de dominio de Active Directory global.

  - Comprueba los puntos de conexión de servicio (SCP) de Lync Server.

  - Identifica la versión de la base de datos.

<div>

## <a name="resolving-issues-with-the-environment"></a>Resolución de problemas con el entorno

Si la prueba de entorno encontró problemas con su entorno, probablemente se deba a problemas con la configuración de Active Directory o el nivel de software que se ejecuta en servidores específicos. Por ejemplo, si el analizador de procedimientos recomendados identifica cualquier controlador de dominio de su entorno que ejecuta Windows Server 2000, emitirá una advertencia y tendrá que actualizar esos controladores de dominio a una versión compatible de Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

