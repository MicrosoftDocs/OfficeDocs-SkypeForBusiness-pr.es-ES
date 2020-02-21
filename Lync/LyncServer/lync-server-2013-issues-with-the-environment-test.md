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
ms.openlocfilehash: c96bae1a917efa52dfc25639d7e46fc1b7e2142e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemas con la prueba de entorno en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El analizador de procedimientos recomendados proporciona una manera de comprobar que el entorno de Lync Server 2013 es una configuración admitida. Durante la comprobación de los servicios de dominio de Active Directory, el Analizador de procedimientos recomendados realiza las siguientes operaciones:

  - Verifica la preparación del bosque y el esquema de Servicios de dominio de Active Directory.

  - Identifica el número de sitios y dominios de Servicios de dominio de Active Directory en la implementación.

  - Comprueba el bosque y los niveles de dominio.

  - Comprueba la versión del controlador del dominio.

  - Identifica el contexto de denominación del dominio, la configuración y el esquema.

  - Identifica el número de usuarios habilitados.

  - Comprueba el lugar de almacenamiento de la configuración de los Servicios de dominio de Active Directory.

  - Busca los puntos de conexión de servicio (SCP) para Lync Server.

  - Identifica la versión de la base de datos.

<div>

## <a name="resolving-issues-with-the-environment"></a>Resolución de problemas del entorno

Si durante la prueba del entorno se detectan problemas, probablemente se deban a problemas de configuración de Active Directory o el nivel de software que se ejecuta en determinados servidores. Por ejemplo, si el Analizador de procedimientos recomendados detecta que algún controlador de dominio del entorno ejecuta Windows Server 2000, emitirá una advertencia y será necesario actualizar esos controladores de dominio a una versión compatible de Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

