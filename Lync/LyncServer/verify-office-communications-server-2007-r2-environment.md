---
title: Comprobar el entorno de Office Communications Server 2007 R2
TOCTitle: Comprobar el entorno de Office Communications Server 2007 R2
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49889762
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar el entorno de Office Communications Server 2007 R2

 

_**Última modificación del tema:** 2012-10-16_

Antes de implementar Lync Server 2013 en un estado de coexistencia con Office Communications Server 2007 R2, compruebe que servicios de Office Communications Server 2007 R2 estén configurados y se hayan iniciado.

**Compruebe que el grupo de servidores se haya iniciado con la herramienta administrativa de Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda sucesivamente el nodo **Bosque**, **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y después expanda el grupo de servidores o el nombre de servidor.

3.  Compruebe que los servicios se ejecuten en el servidor Standard Edition o en el grupo de servidores Enterprise.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")

**Revise los usuarios configurados para Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda sucesivamente el nodo **Bosque**, **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y después expanda el grupo de servidores o el nombre de servidor.

3.  Haga clic en **Usuarios**.

4.  Compruebe la lista de usuarios de Office Communications Server 2007 R2.
    
    ![Lista de usuarios en la herramienta de administración OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Lista de usuarios en la herramienta de administración OCS")

**Compruebe la configuración del socio federado XMPP heredado**

1.  Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\\Services.

2.  Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP para Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP para Office Communications Server")

