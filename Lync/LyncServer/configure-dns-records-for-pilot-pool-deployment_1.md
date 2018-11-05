---
title: Configurar registros DNS para implementaciones de grupos de servidores piloto
TOCTitle: Configurar registros DNS para implementaciones de grupos de servidores piloto
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49889202
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar registros DNS para implementaciones de grupos de servidores piloto

 

_**Última modificación del tema:** 2012-09-24_

Antes de implementar el grupo piloto de Lync Server 2013, es necesario actualizar las entradas de host A de DNS de dicho grupo piloto. Para realizar este procedimiento correctamente, debe iniciar sesión en el servidor o dominio como miembro del grupo Admins. del dominio o del grupo DnsAdmins como mínimo.

**Para configurar los registros de host DNS A**

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, en **DNS**.

2.  En el árbol de consola del dominio, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón derecho en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)**.

4.  Haga clic en **Nombre** y escriba el nombre de host del grupo de servidores (el nombre de dominio se deduce de la zona en la que se define el registro, y no es necesario introducirlo como parte del registro A).

5.  Haga clic en **Dirección IP**, escriba la dirección IP de Grupo de servidores front-end.

6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

7.  Cuando haya terminado, haga clic en **Listo**.

