---
title: Comprobación de la finalización de la replicación de usuarios
TOCTitle: Comprobación de la finalización de la replicación de usuarios
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48274575
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobación de la finalización de la replicación de usuarios

 

_**Última modificación del tema:** 2012-09-28_

Cuando se ejecuta el cmdlet **Move-CsLegacyUser**, es posible que sufra un error debido a la falta de sincronización de la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 por no estar completa la replicación inicial. El tiempo que deba dedicar a completar la sincronización inicial del servicio del replicador de usuarios de Lync Server 2013 dependerá del número de controladores de dominio que haya en el bosque de Active Directory que hospeda el grupo de Lync Server 2013. El proceso de sincronización inicial del servicio Replicador de usuarios de Lync Server 2013 tiene lugar cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Complete los siguientes pasos para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsLegacyUser**.

## Para comprobar que la replicación de usuarios se ha completado

1.  Desde el servidor front-end de Lync Server 2013, haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.

3.  En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

4.  En el panel **Acciones**, haga clic en **Filtrar registro actual**.

5.  En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.

6.  En **\<All Event IDs\>**, escriba **30024** y, a continuación, haga clic en **Aceptar**.

7.  En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.

