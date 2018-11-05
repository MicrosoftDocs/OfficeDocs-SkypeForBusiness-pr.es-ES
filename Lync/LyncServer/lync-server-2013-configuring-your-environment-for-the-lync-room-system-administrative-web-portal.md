---
title: "Configuración del entorno para el portal web administrativo del sistema Lync Room"
TOCTitle: Configuración del entorno para el portal web administrativo del sistema Lync Room
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn436325(v=OCS.15)
ms:contentKeyID: 59602833
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del entorno de Lync Server 2013 para el portal web administrativo del sistema Lync Room

 

_**Última modificación del tema:** 2016-12-08_

Para usar el portal web administrativo del sistema Lync Room (LRS), tendrá que instalar o configurar los siguientes requisitos previos.

> [!IMPORTANT]  
> Si el servidor está configurado con la autenticación Kerberos y NTLM y se está ejecutando LRS en un equipo que no está unido al dominio, la autenticación Kerberos generará un error y el usuario no verá el estado de LRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o autenticación NTLM y TLS-DSK (sin Kerberos) o una el equipo LRS al dominio.



1.  Instale las Lync Server 2013 actualizaciones acumulativas: julio de 2013 en la topología de Lync Server.
    
    Para obtener la actualización o ver lo que se ha incluido en ella, vea [Actualizaciones para Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Cree un usuario de Active Directory habilitados para usar SIP.
    
    El portal administrativo de LRS utiliza estas credenciales para consultar información de Lync Server. El nombre de usuario recomendado es LRSApp.

3.  Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.
    
    Cree el grupo con el ámbito del grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para ver la lista de salones y ejecutar algunos comandos, como la recopilación de registros.

4.  Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup.
    
    Cree el grupo con el ámbito del grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para usar toda la funcionalidad del portal administrativo.
    
     
    
    ![Lista de grupos de administración con el rol de grupo de seguridad](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administración con el rol de grupo de seguridad")  
    
     

5.  Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.
    
    ![Página de miembros de la propiedad LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página de miembros de la propiedad LRSSupportAdminGroup")  
    
     

6.  Cree un usuario de Active Directory habilitados para usar SIP. Agregue este usuario a LRSSupportAdminGroup.
    
    ![Página de miembros de la propiedad LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página de miembros de la propiedad LRSSupportAdminGroup")  
    
     

7.  Instale ASP.NET MVC 4 para Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1, disponible en el Centro de descarga de Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).

