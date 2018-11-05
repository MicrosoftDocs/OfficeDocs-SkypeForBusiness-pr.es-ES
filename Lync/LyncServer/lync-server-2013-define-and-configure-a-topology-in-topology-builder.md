---
title: "Lync Server 2013 : Déf. et conf. d’une top. dans le gén. de top."
TOCTitle: Definir y configurar una topología en Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48276108
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir y configurar una topología en Topology Builder para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

La ejecución de Generador de topologías para definir una nueva topología o para modificar una topología existente no requiere la pertenencia a un grupo de dominios privilegiado ni a un grupo de administrador local. Generador de topologías guía al usuario a través de los pasos necesarios para definir la topología para un grupo de servidores front-end de Enterprise Edition o un fea-frontend-server-role Standard Edition, según sus requisitos de configuración.

Debe usar Generador de topologías para completar y publicar la topología para poder instalar Lync Server 2013 en servidores. En el siguiente procedimiento se indican los pasos necesarios para definir una nueva topología.

## Para definir una topología

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Generador de topologías, seleccione **Nueva topología** . Se le pedirá que elija una ubicación y un nombre de archivo para guardar la topología. Asigne un nombre descriptivo al archivo de topología y acepte la extensión predeterminada de .tbxml. Haga clic en **Aceptar** .

3.  Vaya a la ubicación donde desea guardar el nuevo archivo XML de topología, especifique un nombre para el archivo y haga clic en **Guardar** .

4.  En la página **Definir el dominio principal** , escriba el nombre del dominio SIP principal de la organización y, a continuación, haga clic en **Siguiente** .

5.  En la página **Especificar dominios admitidos adicionales** , especifique el nombre de los dominios adicionales, si los hay, y haga clic en **Siguiente** .

6.  En la página **Definir el primer sitio** , escriba un nombre y una descripción para el primer sitio y haga clic en **Siguiente** .

7.  En la página **Especificar detalles del sitio** , escriba la información de ubicación del sitio y, a continuación, haga clic en **Siguiente** .

8.  En la página **Nueva topología definida correctamente**, compruebe que la casilla **Abrir el Asistente para nuevo servidor front-end cuando se cierre este asistente** esté activada y haga clic **Finalizar**.

Una vez definida y guardada la topología, use el Asistente para nuevo servidor front-end para definir un grupo de servidores front-end o un Servidor Standard Edition para su sitio. Para más información, consulte [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

