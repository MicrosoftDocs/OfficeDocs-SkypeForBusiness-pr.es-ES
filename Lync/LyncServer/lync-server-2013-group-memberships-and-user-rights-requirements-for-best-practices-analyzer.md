---
title: Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

Para ejecutar correctamente el Analizador de procedimientos recomendados, la cuenta de usuario que utilice para iniciar sesión debe ser miembro del grupo de administradores en el equipo local. Además, para examinar el entorno, la cuenta de usuario debe ser miembro de los siguientes grupos:

  - **Administradores de dominio**   para enumerar la información de servicios de dominio de Active Directory y llamar a los proveedores de instrumental de administración de Windows (WMI) en controladores de dominio y servidores de catálogo global.

  - **Administradores**   necesarios en cada equipo interno de Lync Server 2013 y en cada servidor perimetral para llamar a los proveedores de instrumental de administración de Windows (WMI) y obtener acceso al registro.

  - **RTCUniversalReadOnlyAdmins**   los derechos administrativos de Lync Server 2013 de solo lectura o delegado.

  - ****   Administrador con permiso de vista de Exchange el administrador con permiso de vista completo o delegado de Exchange en la organización de Microsoft Exchange.

Si su cuenta de usuario no posee los derechos de usuario suficientes, tiene dos opciones:

  - En el símbolo del sistema, use el comando **runas** para ejecutar la herramienta con una cuenta que no posee derechos de usuario suficientes. La sintaxis es la siguiente:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - En la página **Conectar con Active Directory**, escriba las credenciales de las cuentas que planea utilizar para ejecutar el Analizador de procedimientos recomendados. Haga clic en **Mostrar opciones de conexión avanzadas**. Puede escribir tres cuentas: una para conectarse a los servicios de dominio de Active Directory, una para conectarse a los servidores perimetrales de Lync Server 2013 y otra para conectarse a los servidores de Exchange. Si no especifica ninguna de estas cuentas, se emplea la cuenta de usuario utilizada para iniciar sesión y ejecutar el Analizador de procedimientos recomendados.

</div>

<span> </span>

</div>

</div>

</div>

