---
title: 'Lync Server 2013: configuración de AD FS 2,0 para admitir la autenticación de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8729ca803f3e3897aa9383f28a486229bf5ce33f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configuración de AD FS 2,0 para admitir la autenticación de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2,0 admita la autenticación mediante tarjetas inteligentes:

  - Autenticación basada en formularios (FBA)

  - Autenticación de cliente de seguridad de capa de transporte

Mediante el uso de la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse con su nombre de usuario/contraseña o con su tarjeta inteligente y su PIN. Este tema se centra en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2,0. Para obtener más información acerca de los tipos de autenticación 2,0 de AD FS, consulte AD FS 2,0: Cómo cambiar el [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)tipo de autenticación local en.

<div>


**Para configurar AD FS 2,0 para admitir la autenticación de cliente**

1.  Inicie sesión en el equipo con AD FS 2,0 con una cuenta de administrador de dominio.

2.  Inicie Windows Explorer.

3.  Ir a C:\\Inetpub\\ADFS\\LS

4.  Realice una copia de seguridad del archivo Web. config existente.

5.  Abra el archivo Web. config existente con el Bloc de notas.

6.  En la barra de menús, seleccione **Editar** y, a continuación, seleccione **Buscar**.

7.  Busque ** \<localAuthenticationTypes\>**.
    
    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8.  Mueva la línea que contiene el tipo de autenticación TLSClient a la parte superior de la lista de la sección.

9.  Guarde y cierre el archivo Web. config.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

