---
title: 'Lync Server 2013: Configurar registros de host DNS'
TOCTitle: Configurar registros de host DNS
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48275746
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar registros de host DNS para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Para completar con éxito este procedimiento debe iniciar sesión en el servidor o dominio, como mínimo, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

## Para configurar los registros de host DNS A

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio** , **Herramientas administrativas** y, a continuación, en **DNS** .

2.  En el árbol de consola del dominio, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)** .

4.  Haga clic en **Nombre** y escriba el nombre de host del grupo de servidores (el nombre de dominio se deduce de la zona en la que se define el registro, y no es necesario introducirlo como parte del registro A).

5.  Haga clic en **Dirección IP** y escriba la IP virtual (VIP) del equilibrador de carga de Grupo de servidores front-end.
    
    > [!IMPORTANT]  
    > En las implementaciones que usan un grupo de servidores director, los registros (A) de host de las direcciones URL sencillas deben apuntar al VIP del equilibrador de carga del director.
    
    

    > [!NOTE]
    > Si está implementando solo un servidor Enterprise Edition o un director que esté conectado a la topología sin equilibrador de carga, o si está implementando un servidor Standard Edition, escriba la dirección IP del servidor Enterprise Edition, del servidor Standard Edition o del director. Es necesario usar un equilibrador de carga si implementa más de un servidor Enterprise Edition o un director en un grupo de servidores. Con los servidores Standard Edition, no se usan equilibradores de carga.



6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar** .

7.  Para crear otro registro A, repita los pasos 4 y 5.

8.  Cuando termine de crear todos los registros A que necesite, haga clic en **Listo** .

