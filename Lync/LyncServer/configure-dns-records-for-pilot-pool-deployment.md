---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
TOCTitle: Configurar registros DNS para una implementación de grupo de servidores piloto
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49889796
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar registros DNS para una implementación de grupo de servidores piloto

 

_**Última modificación del tema:** 2012-09-29_

Antes de implementar el grupo de servidores piloto de Lync Server 2013, debe actualizar las entradas DNS Host A para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

**Para configurar los registros de host DNS A**

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio** , **Herramientas administrativas** y, a continuación, en **DNS** .

2.  En el árbol de consola del dominio, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)** .

4.  Haga clic en **Nombre** y escriba el nombre de host del grupo de servidores Lync Server 2013 (el nombre de dominio se deduce de la zona en la que se define el registro y no es necesario introducirlo como parte del registro A).

5.  Haga clic en **Dirección IP** , escriba la dirección IP de Grupo de servidores front-end.

6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar** .

7.  Cuando haya terminado, haga clic en **Listo** .

