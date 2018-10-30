---
title: 'Lync Server 2013: Instalar componentes del servidor Lync Server'
TOCTitle: Instalar componentes del servidor Lync Server
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48274563
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar componentes del servidor en Lync Server 2013

 

_**Última modificación del tema:** 2014-05-05_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario del dominio que sea administrador local y miembro del grupo RTCUniversalReadOnlyAdmins en Active Directory.

El Asistente para la implementación de Lync Server sirve para instalar los componentes necesarios para cada rol de servidor Lync y para activar el servidor. Este artículo le guía por los pasos necesarios para implementar un Servidor Standard Edition o un Servidor front-end en su infraestructura Lync.

## Para instalar los componentes de Lync Server

1.  Si la Asistente para la implementación de Lync Server no se está ejecutando, iníciela en el servidor en el que desea instalar Lync.

2.  Haga clic en **Instalar o actualizar el sistema Lync Server**.

3.  En el Asistente para la implementación, confirme que **Paso 1. Instalar almacén de configuración local** tiene una marca de verificación verde, lo cual indica que este servidor tiene una copia local del almacén instalada correctamente. Si no tiene la marca, tiene que instalar el almacén de configuración local en el servidor. Siga los pasos que aparecen en [Instalar el almacén de configuración local en Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) y luego vuelva aquí.

4.  Cuando esté preparado para instalar los componentes de Lync Server 2013 en el servidor, haga clic en **Ejecutar** junto a **Paso 2: Instalar o desinstalar componentes de Lync Server**.

5.  En la página **Instalar componentes de Lync Server**, haga clic en **Siguiente** para instalar los componentes según se indica en la topología publicada.

6.  La página **Ejecución de comandos** mostrará un resumen de los comandos, así como información sobre la instalación a medida que se realiza. Cuando finalice, puede usar la lista para seleccionar un registro que quiera ver y, a continuación, hacer clic en **Ver registro**.

7.  Cuando finalice la instalación de los componentes de Lync Server 2013 y haya revisado los registros necesarios, haga clic en **Finalizar** para completar este paso de la instalación.
    

    > [!NOTE]
    > Si se le pide que reinicie el servidor (lo que podría suceder si es necesario instalar la la experiencia de escritorio de Windows), hágalo. Cuando el equipo vuelva a estar operativo, tendrá que volver a seguir estos pasos desde el paso tres indicado anteriormente (básicamente es volver a ejecutar el paso&nbsp;2 en el Asistente para la implementación).


