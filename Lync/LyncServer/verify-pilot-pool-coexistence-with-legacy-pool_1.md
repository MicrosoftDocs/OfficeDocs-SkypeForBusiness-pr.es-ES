---
title: Comprobar coexistencia de grupo piloto con grupo heredado
TOCTitle: Comprobar coexistencia de grupo piloto con grupo heredado
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48275360
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar coexistencia de grupo piloto con grupo heredado

 

_**Última modificación del tema:** 2012-09-28_

## Comprobar el grupo en la herramienta administrativa de Office Communications Server 2007 R2

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda el nodo **Bosque**, expanda el nodo **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y, a continuación, el grupo o el nombre de servidor.

3.  Asegúrese de que los servicios de Office Communications Server 2007 R2 se ejecutan en el grupo.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")  

## Comprobar el grupo piloto en el Panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro de la función CsAdministrator, inicie sesión en el servidor front-end de Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **Topología**.

4.  Compruebe que los servidores que ha implementado están presentes en el grupo piloto.
    
    ![Página Topología del Panel de control de Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página Topología del Panel de control de Lync Server")  

## Comprobar que se han iniciado los servicios de Lync Server 2013

1.  En el servidor front-end de Lync Server 2013, abra el subprograma **Servicios** desde el grupo **Herramientas administrativas**.

2.  Compruebe que los servicios enumerados coinciden con la lista de la siguiente ilustración.
    
    ![Página de servicios con los servicios de Lync iniciados](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de servicios con los servicios de Lync iniciados")

