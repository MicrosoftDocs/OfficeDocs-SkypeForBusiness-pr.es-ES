---
title: "Cambiar rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013"
TOCTitle: "Mod. des it. de comm. voc. pour l’ut. du nveau serv. de médiation LS 2013"
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48276330
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambiar rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013

 

_**Última modificación del tema:** 2012-09-28_

Con este procedimiento se cambian las rutas de voz a fin de utilizar el servidor de mediación de Lync Server 2013 en vez del servidor de mediación heredado de Office Communications Server 2007 R2.

## Para cambiar las rutas de voz para usar el nuevo servidor de mediación

1.  Panel de control de Lync Server 2013

2.  En el panel izquierdo, seleccione **Enrutamiento de voz** y luego **Ruta** .

3.  Haga clic en **Nueva** para crear una nueva ruta de voz.

4.  Rellene los siguientes campos:
    
      - **Nombre** : escriba un nombre descriptivo de la ruta de voz. En este documento usaremos **W14PSTNRoute** .
    
      - **Descripción** : escriba una breve descripción de la ruta de voz.

5.  Omita todas las secciones restantes hasta llegar a **Puertas de enlace asociadas** . Haga clic en **Agregar** . Seleccione la nueva puerta de enlace predeterminada y haga clic en **Aceptar** .

6.  En **Usos de la RTC asociados** , haga clic en **Seleccionar** .

7.  En la página **Seleccionar registro de uso de RTC** , seleccione un nombre de registro y haga clic en **Aceptar** .

8.  En la página **Nueva ruta de voz** , haga clic en **Aceptar** para crear la ruta de voz.

9.  En la página **Enrutamiento de voz** , seleccione **Ruta** .

10. Mueva la ruta que acaba de crear al principio de la lista y seleccione **Confirmar** .

