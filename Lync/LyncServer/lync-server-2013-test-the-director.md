---
title: 'Lync Server 2013: Probar el director'
TOCTitle: Probar el director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48276081
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Probar el director en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Llegados a este punto, ya tiene configurado un director o un grupo de servidores de director, pero las entradas SRV de su Sistema de nombres de dominio (DNS) continúan obligando a los clientes a iniciar sesión mediante un grupo de servidores o un servidor Standard Edition. Antes de cambiar el registro para hacer que los clientes de Lync 2013 inicien sesión automáticamente mediante el director, apunte manualmente al director para probar un cliente.

## Para probar la implementación

1.  Inicie sesión en el equipo donde tiene instalado el Panel de control de Lync Server con una cuenta de dominio que forma parte del grupo **CSAdministrator** .

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación, haga clic en **Topología** y en la columna **Estado** compruebe que haya un servidor con una flecha verde (es decir, ![Icono de servidor con flecha verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icono de servidor con flecha verde")) para el director o el grupo de servidores del director.

4.  Conecte dos equipos cliente que tengan instalado el cliente de Lync Server 2013 e inicie sesión con una cuenta de usuario distinta que esté habilitada para Lync Server 2013 en cada equipo.

5.  En uno de los equipos cliente, haga clic en el menú **Opciones** , seleccione el grupo de configuración **Personal** , haga clic en **Avanzada** y, a continuación, en **Configuración manual** . Por último, defina en **Nombre de servidor interno o dirección IP** el nombre de dominio completo (FQDN) del nuevo director o grupo de servidores del director.

6.  Inicie sesión en ambos clientes y compruebe que el cliente que inicie sesión usando el director pueda iniciar sesión correctamente, observe el estado de presencia del otro usuario y si pueden intercambiar mensajes instantáneos.

