---
title: 'Lync Server 2013: crear opciones de configuración de registrador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52826d78b4c528437940f0e44bfac4329bcc7b5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Crear opciones de configuración de registrador en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-17_

Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:

  - **Kerberos**   es el esquema de autenticación basado en contraseña más seguro disponible para los clientes, pero normalmente solo está disponible para los clientes de la empresa, ya que requiere la conexión del cliente a un centro de distribución de claves (controlador de dominio de Kerberos). Esta configuración es adecuada si el servidor autentica solo a los clientes de empresa.

  - **NTLM**   esta es la autenticación basada en contraseña disponible para los clientes que usan un esquema de hash de desafío-respuesta en la contraseña. Esta es la única forma de autenticación disponible para los clientes sin conectividad a un centro de distribución de claves (controlador de dominio de Kerberos), como usuarios remotos. Si un servidor autentica solo a usuarios remotos, debe elegir NTLM.

  - **Autenticación de certificados**   este es el nuevo método de autenticación cuando el servidor necesita obtener certificados de los clientes de Lync Phone Edition, los teléfonos de área común, Lync 2013 y la aplicación de la tienda Windows de Lync. En los clientes de Lync Phone Edition, después de que un usuario inicie sesión y se autentique correctamente proporcionando un número de identificación personal (PIN), Lync Server 2013, a continuación, aprovisiona el URI del SIP en el teléfono y aprovisiona un certificado firmado de Lync Server o un certificado de usuario que identifica a Joe (por ejemplo: SN=joe@contoso.com) al teléfono. Este certificado se usa para la autenticación con el registrador y los Servicios web.

<div>


> [!NOTE]  
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.<BR>Si va a usar los clientes de aplicaciones de la tienda Windows Lync, debe habilitar la autenticación de certificados.



</div>

Siga estos pasos para crear un registrador nuevo.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Para crear nuevas opciones de configuración del registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.

4.  En la página **Registrador**, haga clic en **Nuevo**.

5.  En **Seleccionar un servicio **, haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en **Aceptar **.

6.  En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:
    
      - **Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
      - **Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

