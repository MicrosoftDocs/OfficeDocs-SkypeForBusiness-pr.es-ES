---
title: 'Lync Server 2013: configurar el entorno para el portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configuración del entorno de Lync Server 2013 para el portal web administrativo del sistema Lync Room

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-22_

Para usar el portal web administrativo de Lync Room System (LRS), tendrá que instalar o configurar los siguientes requisitos previos.

<div>


> [!IMPORTANT]  
> Si el servidor está configurado con autenticación Kerberos y NTLM, y LRS se está ejecutando en un equipo que no está unido al dominio, se producirá un error en la autenticación Kerberos y el usuario no verá el estado de LRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o la autenticación NTLM y TLS-DSK (sin Kerberos), o bien, una el equipo LRS al dominio.



</div>

1.  Instale las actualizaciones acumulativas de Lync Server 2013:2013 de julio de en la topología de Lync Server.
    
    Para obtener la actualización o ver lo que se incluye con ella, consulte [actualizaciones para Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Cree un usuario de Active Directory habilitado para SIP.
    
    El portal web administrativo LRS usa estas credenciales para consultar información de Lync Server. El nombre de usuario recomendado es LRSApp.

3.  Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.
    
    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. Los usuarios habilitados para SIP que se agreguen a este grupo tendrán autorización para ver la lista de salas y ejecutar determinados comandos, como la recopilación de registros.

4.  Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup.
    
    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. los usuarios habilitados para SIP que se agregan a este grupo tienen autorización para usar todas las funciones del portal de administración.
    
     
    
    ![Lista de grupos de administración con rol de grupo de seguridad](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administración con rol de grupo de seguridad")  
    
     

5.  Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.
    
    ![Página de miembros de propiedades de LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página de miembros de propiedades de LRSSupportAdminGroup")  
    
     

6.  Cree un usuario de Active Directory habilitado para SIP con el nombre LRSSupport. Agregue este usuario a LRSSupportAdminGroup.
    
    ![Página de miembros de propiedades de LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página de miembros de propiedades de LRSSupportAdminGroup")  
    
     

7.  Install ASP.NET MVC 4 for Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1, disponible en el centro de descarga de [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)Microsoft en.

</div>

<span> </span>

</div>

</div>

</div>

