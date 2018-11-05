---
title: Cambiar URL simples tras la migración
TOCTitle: Cambiar URL simples tras la migración
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49889530
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambiar URL simples tras la migración

 

_**Última modificación del tema:** 2012-09-22_

Lync Server admite tres tipos de dirección URL simples:

  - **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.

  - **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.

  - **Administración** permite un acceso rápido al Panel de control de Lync Server. La dirección URL simple de administración es de uso interno para la organización.

Tras la migración a Lync Server 2013, deberá tener presentes cómo el cambio afecta los certificados y registros DNS de las direcciones URL simples. Si el director heredado de Lync Server 2010 permanece en uso en la topología, no es necesario hacer cambios en las direcciones URL simples. Si el director de Lync Server 2010 se quita de la topología tras la migración, los registros DNS de las direcciones URL simples se deben actualizar para que hagan referencia a uno de los grupos de servidores Lync Server 2013. Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.

## Cambiar las direcciones URL simples tras la migración

**Para actualizar las direcciones URL simples de reunión**

1.  En el Generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server** y luego haga clic en **Editar propiedades** .

2.  Seleccione **Direcciones URL simples** en el panel izquierdo y luego, en **Direcciones URL de reunión:** , seleccione la dirección URL de reunión y haga clic en **Editar URL** .

3.  Actualice la dirección URL con el valor que desee y, a continuación, haga clic en **Aceptar** para guardar la dirección URL modificada.

**Para actualizar las direcciones URL simples de administración**

1.  En el Generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server** y luego haga clic en **Editar propiedades** .

2.  Seleccione **Direcciones URL simples** en el panel izquierdo y luego, en **Dirección URL de acceso administrativo** , escriba la dirección URL simple que desea establecer para el acceso administrativo al Panel de control de Lync Server 2013 y haga clic en **Aceptar** .
    
    > [!TIP]  
    > Le recomendamos que use la dirección URL más sencilla que sea posible para la dirección URL de administración. La opción más sencilla es <strong>https://admin</strong> <em>&lt;domain&gt;</em> .
    


## Vea también

#### Conceptos

[Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

