---
title: "Lync Server 2013 : Exp. des cas de test de routage des communications vocales"
TOCTitle: Exportar casos de prueba de enrutamiento de voz
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48275167
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportar casos de prueba de enrutamiento de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Los casos de prueba constituyen un modo de comprobar las rutas de voz de la organización: primero se definen aspectos como el número que se va a marcar y el plan de marcado y la directiva de voz que se van a usar, y luego Lync Server comprueba si, dadas dichas condiciones, el número especificado se puede enrutar sin problemas a la red RTC.

Los casos de prueba, que se pueden crear en el Panel de control de Lync Server, se suelen guardar únicamente en el servidor donde el caso se creó y ejecutó inicialmente. Pese a ello, se pueden exportar como archivos XML (con la extensión .vtest) y, luego, importar a otros servidores para que puedan ejecutarse en otros equipos ubicados en distintos puntos de la topología.

## Para exportar un caso de prueba de enrutamiento de voz

1.  En Panel de control de Lync Server, haga clic en **Enrutamiento de voz** y luego en **Probar enrutamiento de voz**.

2.  En la pestaña **Probar enrutamiento de voz**, Seleccione el caso de prueba (o los casos de prueba) que va a exportar. Para seleccionar varios casos de prueba, haga clic en el primer caso que se va a exportar, luego mantenga presionada la tecla Ctrl y seleccione los casos adicionales.

3.  Haga clic en **Acciones** y luego en **Exportar casos de prueba**.

4.  En el cuadro de diálogo **Guardar como**, seleccione una carpeta para almacenar los casos de prueba exportados y escriba un nombre para el archivo XML resultante en el cuadro **Nombre de archivo**. Tenga en cuenta que si va a exportar varios casos de prueba, todos ellos se guardarán en un fichero XML.

5.  Para guardar los casos de prueba, haga clic en **Guardar**.

## Vea también

#### Tareas

[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)

