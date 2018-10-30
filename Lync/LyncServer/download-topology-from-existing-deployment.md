---
title: Descargar una topología desde una implementación existente
TOCTitle: Descargar una topología desde una implementación existente
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49889769
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Descargar una topología desde una implementación existente

 

_**Última modificación del tema:** 2012-09-29_

Cuando cree un grupo de servidores de Lync Server 2013, usará el Almacén de administración central asociado con Lync Server 2010. Cuando inicie el Generador de topologías, en el primer uso y en los usos posteriores se le solicitará la ubicación en la que desea que el Generador de topologías cargue el documento de configuración actual. Como ya tiene una topología de Lync Server 2010 definida y ha establecido el Almacén de administración central, elija descargar una topología de una implementación existente. El Generador de topologías leerá la base de datos y recuperará la definición actual.

**Para descargar una topología de una implementación existente**

1.  Abra el **Asistente para la implementación de Lync Server** .

2.  En la página **Lync Server 2013 – Asistente para la implementación** , haga clic en **Instalar las Herramientas administrativas** .

3.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

4.  Seleccione **Descargar topología de la implementación existente**.
    
    ![Configuración del Generador de topologías en el asistente para implementación](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configuración del Generador de topologías en el asistente para implementación")

5.  Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml como valor predeterminado.

6.  Expanda el nodo de Lync Server, tal como mostramos, para revelar los diversos roles de servidor de la implementación.
    
    ![Propiedades generales del rol de servidor del Generador de topologías](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propiedades generales del rol de servidor del Generador de topologías")

