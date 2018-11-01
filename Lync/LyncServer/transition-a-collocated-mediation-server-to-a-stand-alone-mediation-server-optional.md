---
title: "Transición servidor mediación combinado a servidor de mediación independiente (opc.)"
TOCTitle: "Transition d’un serv. de méd. colocalisé vers un serv. de méd. aut. (facult.)"
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48275784
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)

 

_**Última modificación del tema:** 2012-10-19_

Utilice el procedimiento siguiente para realizar la transición del servidor de mediación, combinado en el servidor Standard Edition o grupo Front-End, a un servidor de mediación independiente para una implementación de sitio único.

## Para realizar la transición de un servidor de mediación combinado a un servidor de mediación independiente

1.  Abrir una topología existente desde el Generador de topologías

2.  En el panel izquierdo, vaya a **Grups de mediación** .

3.  Haga clic con el botón secundario en **Grupos de mediación** y seleccione **Nuevo servidor de mediación** .

4.  En la página **Definir nuevo grupo de servidores de mediación** , proporcione el nombre completo del nuevo grupo de servidor de mediación. Además, seleccione si este grupo va a ser un grupo de servidor único o de varios servidores y, a continuación, haga clic en **Siguiente** .

5.  Seleccione el siguiente grupo de salto del servidor de usuario al que el nuevo servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **Siguiente** .

6.  Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **Siguiente** .

7.  En la página **Definir nuevo grupo de servidores de mediación** , asocie la puerta de enlace RTC anterior con el servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en **Agregar** .

8.  Haga clic en **Finalizar** para cerrar el asistente **Definir nuevo grupo de servidores de mediación** .

9.  De **Generador de topología de** , seleccione el nodo superior **Lync Server 2013**.

10. En el panel **Acciones** , seleccione **Publicar topología** y complete el asistente.

11. Siga los pasos de [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) para la instalación de los archivos para servidor de mediación en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.

12. Después de instalar los archivos en el servidor de mediación, vuelva al generador de topologías y en el panel izquierdo, desplácese al grupo.

13. Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades** .

14. En **Servidor de mediación** , desactive la casilla **Servidor de mediación combinado habilitado** y, a continuación, haga clic en **Aceptar** .

15. De **Generador de topología de** , seleccione el nodo superior **Lync Server 2013**.

16. En el menú **Acción** , haga clic en **Publicar topología** y complete el asistente.

