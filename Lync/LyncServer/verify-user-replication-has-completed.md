---
title: Verificar que se ha completado la replicación de usuarios
TOCTitle: Verificar que se ha completado la replicación de usuarios
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48274473
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verificar que se ha completado la replicación de usuarios

 

_**Última modificación del tema:** 2012-09-17_

Cuando se ejecuta el cmdlet **Move-CsUser**, es posible que sufra un error debido a la falta de sincronización de la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 por no estar completa la replicación inicial. El tiempo que deba dedicar a completar la sincronización inicial del servicio del replicador de usuarios de Lync Server 2013 dependerá del número de controladores de dominio que haya en el bosque de Active Directory que hospeda el grupo de Lync Server 2013. El proceso de sincronización inicial del servicio Replicador de usuarios de Lync Server 2013 tiene lugar cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Complete los siguientes pasos para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsUser**.

## Para comprobar que la replicación de usuarios ha finalizado

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.

3.  Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.

4.  En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

5.  En el panel **Acciones**, haga clic en **Filtrar registro actual**.

6.  En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.

7.  En **\<All Event IDs\>**, escriba **30024** y, a continuación, haga clic en **Aceptar**.

8.  En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.

