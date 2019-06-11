---
title: 'Lync Server 2013: configuración de AD FS 2,0 para admitir la autenticación de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configuración de AD FS 2,0 para admitir la autenticación de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:

  - Autenticación basada en formularios (FBA)

  - Autenticación de cliente de seguridad de capa de transporte

Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN. Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0. Para obtener más información sobre los tipos de autenticación 2,0 de AD FS, consulte AD FS 2,0: Cómo cambiar el tipo [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)de autenticación local en.

<div>


**Para configurar AD FS 2.0 para admitir la autenticación de cliente**

1.  Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.

2.  Inicie Windows Explorer.

3.  Ir a C:\\Inetpub\\ADFS\\LS

4.  Haga una copia de seguridad del archivo web.config existente.

5.  Abra el archivo web.config existente con el Bloc de notas.

6.  Desde la barra de menús, seleccione **Editar** y, luego, seleccione **Buscar**.

7.  Busque ** \<localAuthenticationTypes\>**.
    
    Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.

8.  Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.

9.  Guarde y cierre el archivo web.config.

10. Inicie un símbolo del sistema con privilegios elevados.

11. Reinicie IIS ejecutando el siguiente comando:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

